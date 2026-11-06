# UtsavCards

A static, three-page Diwali card experience. Deploy all files together to a static host (such as GitHub Pages, Netlify, or Cloudflare Pages), then open `index.html` over HTTPS. No backend or database is used. Tailwind CDN, Google Fonts, and html2canvas require network access.

Card data, including the optional photo, is encoded in the URL. This is not encryption: anyone with the link can read it, and URLs can appear in browser history, server logs, and referrer data. Photos are compressed locally, but links containing photos can still exceed browser, server, or messaging-app URL limits. Remove the photo if sharing fails. Do not use for sensitive information.

Premium is a mock unlock: no payment is made or verified. A real ₹10 product requires a secure payment provider and server-side verification/entitlement; do not treat URL parameters as proof of payment. Wishes are predefined, editable messages, not AI-generated.
