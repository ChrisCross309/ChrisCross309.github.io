# Christopher A. Hall — Interactive BI Resume

**Live site:** https://chriscross309.github.io

An interactive resume built like a Power BI report — four pages, cross-filtering by role, and a measured-impact view where every figure comes from my own delivery record.

---

## Files

| File | What it is |
|---|---|
| `index.html` | The entire site. Self-contained — all CSS, JavaScript, and the resume PDF live inside this one file. No build step, no dependencies. |
| `resume.pdf` | The same resume as a direct link, for applications that ask for a URL. |
| `og.png` | The 1200×630 preview card LinkedIn, Slack, and iMessage show when the link is shared. |

---

## Deploying

1. **New repository**, named exactly `ChrisCross309.github.io`. Visibility **Public**. Do not initialize with a README — there is one here.
2. **Add file → Upload files.** Drag in all four files. Commit to `main`.
3. **Settings → Pages.** A repo with this exact name usually enables Pages on its own. If not: Source *Deploy from a branch*, branch `main`, folder `/ (root)`, Save.
4. Wait one to two minutes, then open **https://chriscross309.github.io**

To update later, upload a new `index.html` over the old one. The URL never changes.

While in the repo, click the gear beside **About** and paste the site URL into the Website field.

---

## The link preview

`index.html` carries Open Graph tags, so a shared link renders as a card showing `og.png` with the headline **"Interactive BI Resume — Christopher A. Hall"** rather than a bare URL. This works on LinkedIn, Slack, Teams, iMessage, and most email clients.

To change the headline, edit the `og:title` and `twitter:title` meta tags near the top of `index.html`.

If LinkedIn shows a stale or blank preview, run the URL through **linkedin.com/post-inspector** — LinkedIn caches Open Graph data aggressively and the inspector forces a re-fetch.

---

## Before you upload

GitHub Pages is free only from a **public** repository. Everything here is visible to anyone.

That is fine for these files. `index.html` is built from the PII-stripped resume and carries only the LinkedIn URL — no email address, no phone number, no home city. Verified.

**Never add these to this repo:**

- `Christopher_Hall_Senior_BI_Developer_VISUAL.pdf` — phone number and home address
- `Christopher_Hall_BI_Developer_ATS.docx` — same
- `source/visual.html` — same

Those stay on the F drive and go to people directly.

---

## Linking it on LinkedIn

- **Featured section** — add as a link. The card pulls `og.png` and the Open Graph title, so it reads as a proper headline rather than a URL. This is the placement that matters.
- **Contact Info → Websites** — add with the label "Portfolio."
- **Not the About section** — LinkedIn renders URLs there as plain unclickable text.

---

## What visitors see

The rendered site, not GitHub. No code, no repo interface, no account required. Everything runs client-side:

- Four report pages and the left navigation
- The role slicer and its cross-filtering
- The Download Resume button, which assembles the PDF in the visitor's browser

Verified over HTTP before shipping: the download delivers a byte-identical 163,630-byte PDF, the slicer filters correctly, `og.png` and `resume.pdf` both serve, no console errors.

Fonts come from Google Fonts. If that request fails, the page falls back to Arial Narrow and system sans — still legible, different typeface.

---

## Planned

- A section highlighting personal / vibe-coded projects.
- A link through to [ChrisCross309/bi-portfolio](https://github.com/ChrisCross309/bi-portfolio) — public-data ingestion through DuckDB and dbt into Power BI, across three regulated domains.
