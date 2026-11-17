# No line - legal and support site

Static GitHub Pages site for the "No line" app (`com.noline.app`): `index.html`, `privacy.html`, `terms.html`, `support.html`. No build step, no external scripts.

Before publishing, replace the placeholders in all HTML files:
- `{{CONTACT_EMAIL}}` - support/privacy contact email
- `{{GOVERNING_LAW}}` - jurisdiction in terms.html

`privacy.html` section 2 (dashed box) is where to describe crash reporting or analytics if added later; update the effective date too.

`rules/v1.json` is a copy of the app's `blocking_rules.json`, reserved for future remote rules hosting.

Not legal advice; have the texts reviewed before relying on them.
