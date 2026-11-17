# No line - legal and support site

Static GitHub Pages site for the "No line" app (`com.noline.app`): `index.html`, `privacy.html`, `terms.html`, `support.html`. No build step, no external scripts.

Before publishing, replace the placeholders in all HTML files:
- `{{CONTACT_EMAIL}}` - support/privacy contact email
- `{{GOVERNING_LAW}}` - jurisdiction in terms.html

`privacy.html` section 2 (dashed box) is where to describe crash reporting or analytics if added later; update the effective date too.

`rules/v1.json` is the live remote rules file the app fetches (`https://zufar-zfr.github.io/noline-site/rules/v1.json`). It must stay identical in shape to the app's `assets/rules/blocking_rules.json`.

## How to push a rules fix

1. Edit `rules/v1.json` (CSS selectors, text labels, numbers only - never code).
2. Bump `rulesVersion` by 1 and set `updatedAt`.
3. Validate: `python -m json.tool rules/v1.json` (must parse), keep `schemaVersion` at 1, and ideally paste it over the app's `assets/rules/blocking_rules.json` and run `flutter test` (the app's validator rejects bad files and keeps the old rules).
4. `git add rules README.md && git commit && git push`. Pages updates in a minute or two; installs pick it up on their next app start.

Breaking format change: never change v1's shape. Publish `rules/v2.json` with `schemaVersion: 2` only after an app release that understands it and points at v2.json.

Not legal advice; have the texts reviewed before relying on them.
