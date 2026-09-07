# Christopher A. Hall — Interactive BI Resume

**Live site:** https://chriscross309.github.io

An interactive resume built like a Power BI report — four pages, cross-filtering by role, and a
measured-impact view where every figure comes from my own delivery record.

---

## Files

Four files, and all four belong in the repository root.

| File | What it is |
|---|---|
| `index.html` | The entire site. Self-contained — all CSS, JavaScript, and the resume PDF live inside this one file. No build step, no dependencies. |
| `resume.pdf` | The same resume as a direct link, for applications that ask for a URL. |
| `og.png` | The 1200×630 preview card LinkedIn, Slack, and iMessage show when the link is shared. |
| `README.md` | This file. |

---

## Updating the live site

The repository already exists and Pages is already enabled, so updating is just replacing files:

1. Open **https://github.com/ChrisCross309/ChrisCross309.github.io**
2. **Add file → Upload files.**
3. Drag in the files that changed from `F:\projects\resume-site\deploy\`. Same filenames overwrite the old versions.
4. **Commit changes** to `main`.
5. Give it one to two minutes, then hard-refresh **https://chriscross309.github.io**
   (Ctrl+F5 — a normal refresh will serve the cached old page).

If a change doesn't appear, it is almost always browser cache rather than a failed deploy. Check in a
private window before assuming something broke.

### After changing `og.png` or the Open Graph tags

LinkedIn caches preview cards aggressively and will keep showing the old one. Force a re-fetch through
**linkedin.com/post-inspector** and paste in the site URL.

---

## What this version has

- **Deep plum accent** (`#4A1F52`) throughout, replacing the original vermillion. Ties to the
  Alzheimer's Association palette behind the volunteer work.
- **A first-visit intro screen.** Shows once per visitor, then remembers — returning visitors land
  straight on Overview. Re-openable any time via **View intro** in the left rail.
- **A full mobile layout.** One width-driven breakpoint, so rotating a phone just re-runs it. The
  career timeline stacks into rows, the flow diagrams run top to bottom, and Work / Volunteer becomes
  a segmented control on the Experience page instead of a nested rail item.
- **Light and dark themes**, following the visitor's system setting.

---

## Before you upload

GitHub Pages is free only from a **public** repository. Everything here is visible to anyone.

That is fine for these files. `index.html` is built from the PII-stripped resume and carries only the
LinkedIn URL — no email address, no phone number, no home city. This is verified automatically on every
build, including by decoding the PDF embedded behind the Download Resume button and extracting its text.

**Never add these to this repo:**

- `Christopher_Hall_Senior_BI_Developer_VISUAL.pdf` — phone number and home address
- `Christopher_Hall_BI_Developer_ATS.docx` — same
- `source/visual.html` — same

Those stay on the F drive and go to people directly.

---

## Linking it on LinkedIn

- **Featured section** — add as a link. The card pulls `og.png` and the Open Graph title, so it reads
  as a proper headline rather than a URL. This is the placement that matters.
- **Contact Info → Websites** — add with the label "Portfolio."
- **Not the About section** — LinkedIn renders URLs there as plain unclickable text.

---

## What visitors see

The rendered site, not GitHub. No code, no repo interface, no account required. Everything runs
client-side:

- Four report pages and the left navigation
- The role slicer and its cross-filtering
- The Download Resume button, which assembles the PDF in the visitor's browser

Fonts come from Google Fonts. If that request fails, the page falls back to Arial Narrow and system
sans — still legible, different typeface.

---

## Planned

- A section highlighting personal / vibe-coded projects.
- A link through to [ChrisCross309/bi-portfolio](https://github.com/ChrisCross309/bi-portfolio) —
  public-data ingestion through DuckDB and dbt into Power BI, across three regulated domains.
