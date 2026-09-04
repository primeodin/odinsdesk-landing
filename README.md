# Odin's Desk landing

Static conversion page for the Odin's Desk founding pilot (~20 units).

## Brand

- Public name: **Odin's Desk**
- Product: home-desk AI cube with screen; text + talk; powered by Fabric
- Buyer-owned accounts / API keys only (no shared ChatGPT/Grok logins)
- Do not use PrimeNode, IKEA, or Kallax in customer-facing copy

## Local preview

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8080
```

## Deposit CTA (current)

The **Reserve with $50 deposit** form collects name + email and opens a `mailto:waitlist@odinsdesk.com` draft. This page does **not** process payments.

## Wiring Stripe Checkout later

1. Create a Stripe Checkout Session (or Payment Link) for a **$50** deposit product.
2. Replace the deposit form submit handler in `index.html` with a redirect to that Checkout URL (or a small serverless endpoint that creates the session).
3. On `checkout.session.completed`, record the buyer email/name and mark deposit paid.
4. Keep refund policy language in sync: refundable if we don't ship or buyer cancels before production lock.
5. Leave the estimated pilot range (`$499–$799`) clearly marked as an estimate until BOM lock.

Optional: Formspree / Buttondown / Resend for waitlist capture if you outgrow mailto.

## Files

- `index.html` — main conversion page
- `pricing.html` — pricing details
- `styles.css` — shared styles
- `assets/hero-desk.jpg` — web hero image
- `assets/hero-desk.png` — original hero source
