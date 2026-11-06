# UtsavCards

Static Diwali cards with an optional Cloudflare Worker for PayPal Sandbox checkout. Run through Cloudflare Workers for `/api/*` routes; GitHub Pages cannot run the payment API. Tailwind, Google Fonts, html2canvas and PayPal JS use external CDNs.

## Deploy sandbox
1. Connect this GitHub repo using Cloudflare Workers Builds. Use `npx wrangler deploy` as the deploy command, with repository root as root directory. The `wrangler.jsonc` deploys static assets and API together. Watch the build output and enable the workers.dev route.
2. In Cloudflare Worker → Settings → Variables and Secrets, add three encrypted secrets: `PAYPAL_CLIENT_ID`, `PAYPAL_CLIENT_SECRET` (from the PayPal Sandbox app), and `SIGNING_SECRET` (at least 32 random characters, e.g. output of `openssl rand -hex 32`). Redeploy or create a new version as prompted. Never commit these credentials.
3. In PayPal Developer, create a Sandbox business account connected to your app and a separate Sandbox personal buyer account. Open the Worker URL, create a premium card, and pay with the sandbox buyer. Sandbox price is **USD 0.12**, not ₹10, and no real money changes hands. Verify the unlocked link in a private browser and test failures and free cards.
4. Never go live without confirming PayPal support for your business, INR and desired price. Only after testing, set `PAYPAL_MODE` to `live` and a supported currency and price, replace PayPal credentials with live app credentials, and redeploy. USD 0.12 is a test amount, not a conversion or an INR payment.

## Security and limitations
A completed PayPal capture generates an HMAC-signed entitlement bound to the exact encoded card. The browser asks the Worker to verify it before normal premium interaction; the paid link can be shared. Since cards and visual effects are client-side, technically skilled users can modify the frontend and bypass presentation controls. Do not treat it as strong content protection. Changing the signing secret invalidates previously paid links. No database means no order lookup or automated recovery if a paid link is lost. Add durable storage, customer support/refund processes, rate limiting, monitoring, and production payment testing before selling.

Card data and optional photo are embedded in the URL, not encrypted or stored in a database; anyone with the link can read them. URLs may be logged. Photo links may exceed browser, messaging, Cloudflare or PayPal limits; remove the photo if sharing fails. Avoid sensitive information. All payments are per-card; verified proof is shareable with the card. PayPal refunds do not automatically revoke an entitlement.
