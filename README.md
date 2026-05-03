# Design Pickle CEO Hub

Static internal CEO communications hub for Design Pickle.

Live URL: https://russperry.github.io/pickle/

## What this is

A single-page static GitHub Pages site with a lightweight client-side email gate. It hosts CEO welcome copy, latest weekly update placeholder, strategy doc links, and update archive placeholders.

## Access model

This is not backend security. The page uses client-side gating only:
- `@designpickle.com` emails can self-serve.
- `russ@designpickle.com` is admin.
- Non-domain exceptions can be added to the `manualWhitelist` array in `index.html`.
- Session persists in `localStorage`.

Do not place confidential financials, credentials, or sensitive HR/legal material in this static page.

## Updating content

Edit `index.html` directly:
- Replace the Latest Update placeholder.
- Replace Strategy Docs `href="#"` links with real URLs.
- Add archive items to the Updates Archive list.
- Update the `manualWhitelist` array if needed.

## Publishing

GitHub Pages should serve from:
- Branch: `main`
- Folder: `/` root

Deploy flow:

```bash
git status
git add index.html README.md
git commit -m "Update CEO hub"
git push origin main
```

Then verify:
https://russperry.github.io/pickle/

## Maintenance notes

Future hooks are commented in `index.html` for:
- Live ARR/team metrics dashboard.
- Data API integration.
- CMS/content pipeline.

Do not implement those until a backend/data source exists.
