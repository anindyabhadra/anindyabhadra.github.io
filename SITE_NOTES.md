# Anindya Bhadra's site (al-folio)

## Publish on GitHub Pages
0. Copy `Code_Bhadra_Carroll_2015.zip` and `Code_Feldman_Bhadra_Kirshner_2014.zip` from your old `www/software/` folder into `assets/software/` (left out of this download for size).
1. Create a public GitHub repo named `anindyabhadra.github.io`.
2. Push the contents of this folder to its `main` branch.
3. The **Deploy site** action builds the site and pushes it to a `gh-pages` branch (first run takes about 5 minutes).
4. In the repo, go to Settings → Pages and set the source to the `gh-pages` branch.

To host at a different address, change `url` (and `baseurl`, if it is a subpath) in `_config.yml`.
Old links such as `stat.purdue.edu/~bhadra/papers/...` stop working if the Purdue pages are removed, so consider leaving the old files there or replacing `index.html` with a link to the new site.
To host on the Purdue server instead, build locally (`bundle install && bundle exec jekyll build`, with `baseurl: /~bhadra`) and upload `_site/`.

## Everyday edits
- **New paper:** add an entry to `_bibliography/papers.bib`. Set `period` (Preprints, 2025–present, …) and `category` (Methodology / Applied).
  Author markers: `†` graduate student, `‡` postdoc, `*` equal contribution, written after the last name (e.g. `Gao†, Z.`).
  Add `selected = {true}` to feature it on the home page. Buttons come from `doi`, `arxiv`, `code`, `html`, `pdf`, `blog`; `award` and `award_name` add a highlight button.
- **News:** add a file to `_news/` (copy an existing one; only month and year are shown).
- **Photo:** `assets/img/prof_pic.jpg` (square crop of `ab_4.jpg`).
- **Files:** CV and paper PDFs in `assets/pdf/`, talk slides in `assets/pdf/presentations/`, code zips in `assets/software/`.
- **Pages:** `_pages/about.md`, `research.md`, `talks.md`, `teaching.md`, `software.md`.

## Local overrides of theme files
- `_sass/_themes.scss`: colors (higher contrast, slate-teal accent), Newsreader + Source Sans 3 fonts, square photo, publication headings.
- `_includes/news.liquid`: news dates shown as month and year only.

After upgrading the al-folio gems, run `bundle exec al-folio upgrade overrides audit` to check these against the new gem versions.

## Not copied from the old www folder
- `docs/` (password-protected with `.htaccess`; a public GitHub repo cannot protect it).
- `teaching/` course folders (not linked from any page; include homework solutions).
- `Postdoc_Bhadra_2025.pdf`, `Biometrics_Bhadra_Mallick.pdf`, `presentations.html~` and the unlinked slide PDFs.
