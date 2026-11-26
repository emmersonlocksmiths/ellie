# Ellie Custom Gifts – shop

Customer shop: `index.html`  ·  Admin: `admin.html`  ·  Shared code and settings: `shared.js`

## Going live (one time)

1. **Firebase project** – console.firebase.google.com › Add project.
2. **Database** – Databases & Storage › Firestore › Create database (production mode, location `australia-southeast1` Sydney).
3. **Rules** – Firestore › Rules: paste everything from `firestore.rules`, change `YOUR-ADMIN-EMAIL@example.com` to your admin email, Publish.
4. **Admin login** – Security › Authentication › Sign-in method › enable Email/Password, then Users › Add user (your email + a strong password).
5. **Connect the shop** – Project settings (gear icon) › Your apps › Web `</>` › copy the `firebaseConfig` block into `shared.js` where it says `const FIREBASE_CONFIG = null;`.
6. **Hosting** – push this folder to the GitHub repository, then Settings › Pages › Deploy from a branch › `main` / root. The shop appears at `https://<username>.github.io/<repo>/`.
7. **Allow the admin login on that address** – Firebase › Authentication › Settings › Authorised domains › add `<username>.github.io`.
8. **First admin login** – open `…/admin.html` and log in. The starting catalogue (products, prices, colours, designs) is copied into Firebase automatically.
9. **Settings in admin** – add your contact email, and your Web3Forms access key (free at web3forms.com) so each new order is emailed to you.
10. **Test** – place a test order on the shop, check it appears in admin and in your email, then delete it.

## Notes
- With `FIREBASE_CONFIG = null` the site runs in demo mode (saved in the browser only) – handy for testing.
- Prices on an order are worked out in the customer's browser: check the total in admin before sending the invoice.
- Gallery photos live in `gallery/`; the list is `GALLERY` in `shared.js`.
