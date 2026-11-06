# UtsavCards

All card experiences are free: book opening, fireworks, sound, sharing and HD image export. The sender may optionally contribute ₹10 to Nemi Digital Agency. Contributions are not required to create, open, share or download a card and should not be presented as charitable donations or as a purchase. Test mode never moves real money.

## Optional support setup
The Cloudflare Worker uses the existing Razorpay integration and encrypted `RAZORPAY_KEY_ID`, `RAZORPAY_KEY_SECRET`, and `SIGNING_SECRET` bindings. `PRICE_PAISE` is 1000. Configure Razorpay QR Codes separately with Razorpay; QR availability and Test Mode support vary. The standard Razorpay checkout is offered as an alternative. A support payment is not required for any card functionality. The browser polls Razorpay through the Worker for the single-use fixed-amount QR, and confirms captured amount before displaying thanks. Do not use live keys until provider eligibility, legal policy, failure and refund handling are reviewed and verified.

## Important limitations
No D1 integration or durable payment records have been implemented yet. There is no webhook, support-payment recovery across browsers, refund management, abuse prevention, or full end-to-end payment testing. The Razorpay dashboard can be used to investigate transactions, but a production launch needs robust handling and professional legal/financial review. Never guarantee a nonnegative merchant balance or freedom from legal issues. Do not claim a tax benefit or charity status.

Card data and optional photo are encoded in the URL, not encrypted or stored in a card database. Anyone with the link can read them. Links can exceed browser/messaging limits and may appear in logs or history. Users should not include sensitive information. Google Fonts, Tailwind CDN, html2canvas and Razorpay Checkout require internet access.
