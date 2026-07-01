# Topsy Wordy support site

Public-facing static site for the Topsy Wordy iPhone app. Hosts the landing page, support FAQ, Privacy Notice, Terms of Use, and Acknowledgements. Served via GitHub Pages. Mirrors the HowManyAnagrams and In the Retelling support sites in structure.

## What is hosted

- `index.html` - landing page, brief description, links to the other pages.
- `support.html` - support FAQ with a `mailto:` contact line.
- `privacy.html` - Privacy Notice. Must stay in sync with the app's bundled `assets/legal/privacy.md`, with one deliberate exception: the contact sentence here carries the live email address, while the bundled copy points to the support page instead.
- `terms.html` - Terms of Use. Must stay in sync with the app's bundled `assets/legal/terms.md`, with the same deliberate contact-sentence exception.
- `acknowledgements.html` - the ESDB attribution notice, mirroring the app's bundled `assets/legal/acknowledgements.md`.
- `styles.css` - single stylesheet using the app's brand tokens. Light and dark mode via `prefers-color-scheme`.
- `fonts/` - self-hosted Newsreader and Inter, both under the SIL Open Font License 1.1 (`fonts/OFL.txt`).
- `favicon.svg` - a small persimmon square echoing the app's tile mark.
- No JavaScript, no third-party requests, no fonts loaded from a CDN, no analytics.

## Support contact

The contact email for support and privacy questions is `enquiries@consideredideas.com`, shared with the other Considered Ideas apps. The address lives only on the public websites and consideredideas.com; the app deliberately bundles no email address, and its legal documents point to this support page instead, so the address can change without an app release.

## URLs

The intended custom domain is `topsywordy.com`:

- Landing: `https://topsywordy.com`
- Support: `https://topsywordy.com/support.html`
- Privacy: `https://topsywordy.com/privacy.html`
- Terms: `https://topsywordy.com/terms.html`
- Acknowledgements: `https://topsywordy.com/acknowledgements.html`

The Support URL and Privacy URL above are what the App Store Connect listing should reference. The Marketing URL field can use the landing URL once the site is live.

## Enabling GitHub Pages

1. Create a public GitHub repository for this folder and push it. GitHub Pages on a free account requires a public repo.
2. In the repo on GitHub: Settings, then Pages.
3. Source: "Deploy from a branch".
4. Branch: `main`, Folder: `/ (root)`.
5. Save, then wait one to two minutes for the first publish.

## Custom domain

Map `topsywordy.com` via Settings, then Pages, then Custom domain. The `CNAME` file in this repo carries the domain. At the registrar, point the apex at GitHub's `A` records and add a `CNAME` for `www`. If `topsywordy.co.uk` is also registered, forward it to the `.com` at registrar level, mirroring the other apps.

## Updating the legal text

The Privacy Notice, Terms of Use, and Acknowledgements are duplicated between the app repo's bundled markdown (`assets/legal/`) and this site's HTML. When either set is updated, the other must follow. The only sanctioned difference is the contact sentence: the hosted pages carry the live email, while the bundled markdown carries no email and points to the support page. Stamp the same "Last updated" date in both when legal text changes.

There is no automated sync between the app repo and this site. For v1 the manual cross-check is enough.
