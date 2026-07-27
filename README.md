# giftsonx-legal

Static legal pages for GiftsonX apps, served by GitHub Pages at
**https://legal.giftsonx.com/**.

| Page | URL |
|---|---|
| Fit Assist — Privacy Policy | https://legal.giftsonx.com/fitassist/privacy/ |
| Fit Assist — Terms of Use | https://legal.giftsonx.com/fitassist/terms/ |
| Fit Assist — Data & account deletion | https://legal.giftsonx.com/fitassist/delete/ |

The privacy and deletion URLs are referenced from the Google Play Store listing
(Data safety + App content → Data deletion) and from the app itself via
`EXPO_PUBLIC_PRIVACY_URL` / `EXPO_PUBLIC_TERMS_URL` in `client/eas.json`.

## Source of truth

These files are authored in the app repo at `fitness/web/legal/fitassist/` and
copied here. Edit them there first, then copy across and push, so the two do not
drift. Bump the `Version:` date in the page header on any material change — the
in-app disclaimer flow references that version.

## Hosting

- GitHub Pages, `main` branch, root directory.
- `CNAME` pins the custom domain; DNS is a `CNAME` record at the registrar
  (`legal` → `johnabish.github.io`).
- `.nojekyll` disables Jekyll processing — these are plain static files.
