# Acharya Boys PG Website — Responsive Fix Pack

## What is included
- Restored full original purple theme stylesheet (instead of the incomplete responsive-only CSS paste).
- A single responsive QA patch for mobile, tablet and desktop layouts.
- Restored complete homepage markup, including the missing Rooms & Pricing and Why Choose Us sections.
- Removed the public “What Customers Say” section and its navbar link, as requested.
- Homepage hero uses `images/hero.png` when you add it; the bundled `images/exterior-night.jpg` is a fallback.
- Admin dashboard UI is restricted to the supplied Firebase UID.
- `firestore.rules` is included to protect Firestore data while allowing visitors to submit enquiries.

## Run locally
1. Extract this ZIP.
2. Open the `pg-website-main` folder in VS Code (the folder that contains `index.html`).
3. Start Live Server by right-clicking `index.html` → Open with Live Server.
4. Public page: `http://127.0.0.1:5500/index.html` (port may differ).
5. Admin page: `http://127.0.0.1:5500/admin/index.html` (same origin/port).

Do not open the HTML directly from inside the ZIP or from a `file://` URL.

## Hero image
Place your own building image at `images/hero.png` to use it as the homepage hero. If it is absent, the CSS falls back to the bundled `images/exterior-night.jpg`.

## Firebase / Firestore security
The existing `firebase-config.js` is preserved and remains connected to the original Firebase project (`my-business-website-82b7b`). The admin UI checks the configured admin UID in `admin/admin.js`.

To fix Firestore “Permission denied” errors:
1. Open Firebase Console → Firestore Database → Rules for your original project.
2. Review the existing rules before replacing them. If this is the intended database for this site, copy the contents of `firestore.rules` into the Rules editor.
3. Click Publish.
4. Test the public enquiry form and admin dashboard.

The rules permit visitors to create enquiry documents with the fields currently sent by `dynamic.js`, permit public reads of services and the main settings document, and restrict reading/managing enquiries and writing site data to the admin UID. Keep the UID consistent with your actual admin user's Firebase UID.

## Before showing the client
- Replace any placeholder rent, deposit, phone, WhatsApp, address, availability and facility information with owner-confirmed details.
- Confirm that the room photos accurately represent the room types shown.
- Test the website on a real phone, not only browser responsive mode.
- Do not publish unconfirmed claims or testimonials.

## Notes
- The public testimonials section has been removed. The admin panel still contains its testimonial management tab for future use.
- This package has been structurally checked and JavaScript syntax checked; browser/device testing still needs to be performed in your environment.
