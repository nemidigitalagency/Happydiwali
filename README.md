# UtsavCards — free edition

All card features are free. No payment or contribution flow is active. Deploy the files as a Cloudflare Worker with static assets using `npx wrangler deploy`. Google Fonts, Tailwind CSS CDN and html2canvas require network access. Payment provider secrets are no longer used and can be removed from the Worker in Cloudflare.

Card text and names are compressed into the URL, not encrypted; anyone with the link can read them. All cards use the same hosted illustration; personal uploads are no longer supported. Links may still exceed messaging or hosting limits for exceptionally long or unusual text. Do not include sensitive information. D1 is not connected.

The policy documents are drafts and are not published. Before public launch, audit the actual providers, cookies, logs and privacy practices and obtain legal review. Test creation, recipient sharing, sound, mobile layout and PNG export on the intended devices and browsers.
