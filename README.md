# Christopher A. Hall: Interactive BI Resume

**Live site:** https://chriscross309.github.io

An interactive resume built like a Power BI report: five pages, cross-filtering by role, a
measured-impact view where every figure comes from my own delivery record or from Rocket's own
investor disclosure, and three analytics projects built on public data.

---

## Files

Four files, and all four belong in the repository root.

| File | What it is |
|---|---|
| `index.html` | The entire site. Self-contained: all CSS, JavaScript, and the resume PDF live inside this one file. No build step, no dependencies. |
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
   (Ctrl+F5; a normal refresh will serve the cached old page).

If a change doesn't appear, it is almost always browser cache rather than a failed deploy. Check in a
private window before assuming something broke.

`index.html` and `resume.pdf` travel together: the PDF is embedded inside the HTML as base64 behind the
Download Resume button, so uploading one without the other means the button serves a different document
than the direct link does.

### After changing `og.png` or the Open Graph tags

LinkedIn caches preview cards aggressively and will keep showing the old one. Force a re-fetch through
**linkedin.com/post-inspector** and paste in the site URL.

---

## What this version has

- **Deep plum accent** (`#4A1F52`) throughout, replacing the original vermillion. Ties to the
  Alzheimer's Association palette behind the volunteer work.
- **A first-visit intro screen.** Shows once per visitor, then remembers: returning visitors land
  straight on Overview. Re-openable any time via **View intro** in the left rail.
- **A curated Overview.** A first-person profile with a call to action, and nine KPI tiles ordered so
  that the first two rows each span all three employers. Two figures are Rocket's own public numbers,
  cited to the Q4 2022 earnings call, so a recruiter can verify them without asking.
- **A career timeline that leads with the analytics career** without hiding what came before it. The
  pre-analytics claims-adjuster span is a dashed, unfilled bar tagged *prior to analytics*, and the header
  reads both totals: 10.3 years, 6.8 in analytics. An education timeline sits under it on the same axis,
  with each degree marked at its graduation year.
- **One skillset table.** Five capability groups, each with a rating and the employers it was used at.
  An arrow opens a group to show each capability and what I did with it. One dot is proficient, two
  advanced, three expert. Picking a role in the slicer holds the table to the capabilities used there.
- **Short, direct copy.** Paragraphs keep to 15 words a sentence and 3 sentences a paragraph, and
  every title and label carries a capital on every word.
- **A calmer dark theme.** Body text sits at about 11:1 rather than 14:1, which keeps it above WCAG AAA
  while taking the glare off. Every pair was re-checked against AA.
- **A full mobile layout.** One width-driven breakpoint, so rotating a phone just re-runs it. The
  timelines stack into rows with year lines running through them, the flow diagrams run top to bottom
  with arrows between steps, and Work / Volunteer becomes a segmented control on the Experience page
  instead of a nested rail item.
- **Light and dark themes**, following the visitor's system setting.
- **A Performance Marketing Reporting Suite card on Impact.** Four Rocket Mortgage reports in campaign
  order, from sizing an audience to tuning the targeting models.
- **A Projects page.** Three analytics projects built on public data: flood insurance, consumer
  lending, and health and aging. The page opens on why public regulated data, one card per project, and
  how the shared backend was built. A Data Sources card cites all 13 public datasets, each linked to its
  publisher's own page. A card opens that project's full analysis and a conclusion that says
  whether the question was answered, and a Back button returns to the cards. Each section reads as prose
  and then its visuals, and every bar carries the number it stands for.
  Every figure is generated from the writeup's figures and checked against them before upload. Link
  straight to a project with
  `#projects/flood-insurance`, `#projects/consumer-lending` or `#projects/health-and-aging`.

---

## Before you upload

GitHub Pages is free only from a **public** repository. Everything here is visible to anyone.

That is fine for these files. `index.html` is built from the PII-stripped resume and carries only the
LinkedIn URL: no email address, no phone number, no home city. This is verified automatically on every
build, including by decoding the PDF embedded behind the Download Resume button and extracting its text.

**Never add these to this repo:**

- `Christopher_Hall_Senior_BI_Developer_VISUAL.pdf`: phone number and home address
- `Christopher_Hall_BI_Developer_ATS.docx`: same
- `source/visual.html`: same

Those stay on the F drive and go to people directly.

The same check covers confidentiality, not just PII. Rocket Rewards figures on this site are limited to
what Rocket Companies disclosed publicly; internal cohort numbers are deliberately absent and should stay
that way. The reasoning is in the Claude project's decisions log.

The Performance Marketing Reporting Suite card follows the same rule. Its campaign test is described without a
number, and it does not name the prescreen vendor.

---

## Linking it on LinkedIn

- **Featured section**: add as a link. The card pulls `og.png` and the Open Graph title, so it reads
  as a proper headline rather than a URL. This is the placement that matters.
- **Contact Info → Websites**: add with the label "Portfolio."
- **Not the About section**: LinkedIn renders URLs there as plain unclickable text.

---

## What visitors see

The rendered site, not GitHub. No code, no repo interface, no account required. Everything runs
client-side:

- Five report pages and the left navigation
- The role slicer and its cross-filtering, across the four resume pages. On Skillset it filters the
  capability rows to the ones used in that role
- The Projects page, where the project cards are the filter, with deep links such as `#projects/flood-insurance`
- The Download Resume button, which serves `resume.pdf` from this repo

Fonts come from Google Fonts. If that request fails, the page falls back to Arial Narrow and system
sans: still legible, different typeface.

---

## Planned

- A section highlighting personal / vibe-coded projects.
