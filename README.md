# Green Tech Empire — GitHub Pages edition

This is a plain HTML/CSS/JavaScript website for the repository site:

https://benjaminbright392-cloud.github.io/GTD/

## IMPORTANT: upload the contents, not the ZIP or its containing folder

After extracting this ZIP, the files should be arranged exactly like this in the **root of the `GTD` repository**:

```text
GTD/
├── index.html
├── admin.html
├── style.css
├── main.js
├── auth.js
├── orders.js
├── config.js
├── .nojekyll
├── README.md
└── assets/
    └── (25 product photos)
```

Do not put the files inside another folder. Do not upload only `README.md`. `index.html` must be visible on the repository's main Code page.

## Replace the broken repository contents

1. Download and extract this ZIP on your computer.
2. Open https://github.com/benjaminbright392-cloud/GTD.
3. Remove/replace the old files that are inconsistent with this layout. In particular, the old repository had product images at the root and no `index.html`; this ZIP puts images inside `assets/` and includes the homepage.
4. Upload **all extracted files and the complete `assets` folder** to the `main` branch root, then commit the changes.
5. Open **Settings → Pages**.
6. Under **Build and deployment**, choose **Deploy from a branch**, select branch `main`, folder `/(root)`, then click **Save**.
7. Wait for the Pages deployment, then open https://benjaminbright392-cloud.github.io/GTD/ and hard-refresh with `Ctrl + F5`.

This package uses relative paths (`./style.css`, `./main.js`, `./assets/...`) so CSS, JavaScript and photos resolve under the `/GTD/` project path.

## Before accepting orders

- Product prices are intentionally unset (`price: null`) in `main.js`. Set actual prices before taking orders.
- Email verification and order storage require a Firebase project. Replace the placeholder values in `config.js`, enable Email/Password Authentication, set the authorized domain to `benjaminbright392-cloud.github.io`, and configure Firestore security rules. Browsing the catalogue should work without Firebase configuration.
- Set `ADMIN_EMAIL` in `config.js` to the shop owner's email and use matching Firestore rules. Do not put private service-account keys in frontend code.
- The optional shop tip is ₦10. A customer-side reference/hash is not proof of payment; the shop must confirm transfers independently.

## Local preview

Run a local HTTP server in this folder (JavaScript modules may not work from a `file://` URL):

```bash
python3 -m http.server 8000
```

Open http://localhost:8000.
