# CLAUDE.md — kovar-site

Static HTML marketing + legal site for Kovar (Kids Bowel Care). Deployed via GitHub Pages. No build step.

## Related repos (sibling absolute paths)

- **iOS app** (Swift, XcodeGen): `/Users/adrianmcgee/Developer/GutsyKids` (Kovar.xcodeproj)

The App Store listing links to pages here (privacy, support). If you change a path or filename, update App Store Connect (`build/asc.py` in the app repo patches `appInfoLocalizations.privacyPolicyUrl` and `appStoreVersionLocalizations.supportUrl`).

## Contents

- `index.html` — landing page.
- `privacy/index.html` — privacy policy (referenced from App Store listing). Stance: **Data Not Collected** — all data lives in the user's own iCloud/CloudKit private DB; developer receives nothing.
- `support/index.html` — support landing page (`mailto:` + FAQ).

## Edits

Edit HTML directly — no framework, no build. Commit + push to `main`; GitHub Pages publishes within ~1 minute.

## URLs (GitHub Pages project site)

- Privacy: `https://adrianmcgee.github.io/kovar-site/privacy/`
- Support: `https://adrianmcgee.github.io/kovar-site/support/`

## Cross-repo gotchas

- App Store metadata references the privacy + support URLs verbatim. Don't rename `privacy/` or `support/` without updating App Store Connect.
- Privacy policy must stay truthful: if the app ever adds analytics/crash/ads SDKs, update the policy AND the App Store privacy nutrition label (UI-only) before shipping.
