# BAMP — By Any Means Possible real-store starter

This is a deployable Node/Express storefront with:
- 12 BAMP products across Core, Essentials, Headwear, Bags and Limited collections
- product detail windows and size selection
- shopping bag with local persistence
- South African Rand pricing and R90 shipping under R1,500
- customer checkout window
- Payfast hosted checkout integration
- Payfast ITN endpoint that verifies the signature, order amount and Payfast server confirmation
- order records stored in `orders.json`
- Payfast Sandbox/live switch via environment variables

## Run locally
1. Install Node.js 18+.
2. Copy `.env.example` to `.env`.
3. Add Payfast Sandbox credentials.
4. Run `npm install`.
5. Run `npm start`.
6. Open `http://localhost:3000`.

Payfast's ITN needs a publicly reachable notify URL, so a local-only server cannot receive live ITNs. Use Payfast Sandbox with a public HTTPS deployment for end-to-end testing.

## Go live
- Create/verify the merchant account and use the live merchant ID, merchant key and passphrase.
- Set `PAYFAST_MODE=live`.
- Set `PUBLIC_BASE_URL` to your real HTTPS domain.
- Deploy the Node server.
- Keep credentials only in environment variables.
- Test an end-to-end order before launch.

The checkout uses Payfast's hosted payment page, so sensitive payment details are handled by the payment provider rather than stored by this site.
