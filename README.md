# PanelProof

A static publication about how displays are specified, certified and built — and about
the distance between what a spec sheet claims and what a standard actually requires.

**Live site:** https://panelproof.com

## What this is

A dependency-light static site generator (`build.py`, ~1,000 lines of Python) plus a
markdown content tree, deployed to GitHub Pages by Actions on every push to `main`.

Design priorities, in order:

1. **Publishable quality** — real policy pages, transparent authorship and AI
   disclosure, cited primary sources, no thin pages.
2. **SEO** — semantic HTML, one H1 per page, canonical URLs, a full JSON-LD graph,
   sitemap, RSS, breadcrumbs, internal linking, image alt text.
3. **GEO** — key-takeaway blocks with per-figure citations, FAQ blocks, explicit dates
   and revisions, source lists, `llms.txt`.
4. **Core Web Vitals** — no JS framework, no web-font requests, inlined critical CSS,
   explicit image dimensions, lazy loading below the fold.

## Quick start

```bash
pip install -r requirements.txt
python3 build.py            # build into dist/
python3 build.py --serve    # build, then serve on :8000
python3 scripts/validate.py # publication gate — must exit 0 before commit
```

Write a new post:

```bash
python3 scripts/new_post.py "Your headline here" --category hdr
```

Offline build (skips link checking and photo fetching):

```bash
PP_OFFLINE=1 python3 build.py && PP_OFFLINE=1 python3 scripts/validate.py
```

## The publication gate

`scripts/validate.py` fails the build — and therefore the deploy — on any of:

- a key takeaway asserting a figure with no source index
- a source missing title, URL, publisher or access date
- fewer than 3 sources, or no source marked `primary`
- a dead source URL
- a broken internal link or image
- more than one `<h1>`, a `<title>` over 62 chars, a meta description outside 110–165
- an `<img>` with no alt text
- malformed JSON-LD
- a missing legal or policy page
- placeholder text escaping into production

This is intentionally difficult to satisfy. Fix the article, never the gate.

## Layout

```
build.py                 static site generator
scripts/                 imagegen, photos, chartgen, factcheck, commentary, validate, new_post
site.config.json         name, domain, categories, AdSense + analytics IDs
content/posts/*.md       articles, named YYYY-MM-DD-slug.md
content/pages/*.md       about, contact, legal and policy pages
static/                  style.css, script.js, consent.js — copied verbatim into dist/
assets/fonts/            fonts used by the image generator only, never served to browsers
dist/                    build output, git-ignored
```

`CLAUDE.md` holds the editorial standard. `automation/daily-post.md` holds the routine.
`SETUP.md` covers deployment, secrets, analytics and AdSense.

## Licence

Code: MIT. Editorial content: all rights reserved.
