# giftsonx-legal

Static legal pages for GiftsonX apps, served by GitHub Pages at
**https://legal.giftsonx.com/**.

| Page | URL |
|---|---|
| Fit Assist — Privacy Policy | https://legal.giftsonx.com/fitassist/privacy/ |
| Fit Assist — Terms of Use | https://legal.giftsonx.com/fitassist/terms/ |
| Fit Assist — Data & account deletion | https://legal.giftsonx.com/fitassist/delete/ |
| BMI - FitAssist — Privacy Policy | https://legal.giftsonx.com/bmi-fitassist/privacy/ |

The Fit Assist privacy and deletion URLs are referenced from its Google Play
listing (Data safety + App content → Data deletion) and from the app itself via
`EXPO_PUBLIC_PRIVACY_URL` / `EXPO_PUBLIC_TERMS_URL` in `client/eas.json`. The
BMI - FitAssist privacy URL is referenced from that app's Play listing.

**Serve legal URLs from this domain, never from a `github.io` URL.** A
`username.github.io/repo` URL breaks whenever the account is renamed or the repo
is transferred, and GitHub issues no redirect — which strands a URL already
registered with Google Play. The domain is ours; the namespace is not.

## Source of truth

Fit Assist pages are authored in the app repo at `fitness/web/legal/fitassist/`
and copied here. Edit them there first, then copy across and push, so the two do
not drift. Bump the `Version:` date in the page header on any material change —
the in-app disclaimer flow references that version.

The BMI - FitAssist page has no upstream; this repo is its only home. It was
migrated verbatim (byte-identical) from `JohnAbish/bmi-fitassist-privacy` so the
policy text did not change when its URL did.

## Hosting

> **This repo must stay PUBLIC.** GitHub Pages is disabled on private repos for
> free accounts, so flipping it private takes every URL above to 404 with no
> warning. This is not theoretical: the 2026-07-27 transfer from `JohnAbish` to
> `john-abish` silently flipped visibility to private and the site went down
> until it was set public and Pages re-enabled. Nothing here is secret — the
> whole point is that Google and users can read it.

- GitHub Pages, `main` branch, root directory.
- `CNAME` pins the custom domain; DNS is a `CNAME` record at the registrar
  (`legal` → `johnabish.github.io`).
- `.nojekyll` disables Jekyll processing — these are plain static files.
