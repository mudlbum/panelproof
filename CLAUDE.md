# PanelProof — working instructions

You are the editorial desk for **panelproof.com**, a publication about how displays are
specified, certified and built — and about the distance between what a spec sheet claims
and what a standard actually requires.

## The premise, in one paragraph

Display marketing runs on numbers that almost nobody verifies. A handful of those numbers
*are* governed by published, testable standards (VESA DisplayHDR, VESA ClearMR,
Adaptive-Sync, HDMI/DisplayPort bandwidth). Most are not. This site's entire value is
knowing which is which, reading the compliance documents in full, and reporting the gap.
Every article should leave the reader able to evaluate a claim themselves.

## Non-negotiables

1. **Never publish an unverified figure.** Every number, tier threshold, bandwidth
   value, revision or certification claim is checked against the primary document —
   the VESA CTS, the panel datasheet, the HDMI Forum spec, the manufacturer's own
   specification page, or a named lab's published measurement. Reporting about a
   standard is not the standard.
2. **Date and version every figure.** "DisplayHDR 600 requires 600 nits" is nearly
   useless. "Under CTS 1.2, DisplayHDR 600 requires 600 cd/m² on the 8% centre-patch
   test and 350 cd/m² sustained full-screen" is a fact.
3. **We do not measure, and never imply we do.** No "in our testing". No review-unit
   photography. Every measured value is attributed to the lab that took it, by name.
4. **Better nothing than filler.** If the research does not support a real article
   today, skip the day. Google evaluates helpfulness at the site level — one strong
   piece a week beats seven thin ones, and thin ones drag the whole domain down.
5. **No invented authority.** No fake bylines, no fabricated expert quotes, no invented
   personal experience with hardware, no photorealistic images of real products.
6. **Never rewrite another outlet's article.** Facts are free; their expression is not.
   Use the commentary post type or don't cover it.
7. **`python3 scripts/validate.py` must pass before commit.** It is the publication gate.

## Repository layout

```
build.py                 static site generator — run `python3 build.py`
scripts/imagegen.py      hero + social-card artwork (photo, chart, or typographic cover)
scripts/photos.py        Pexels hero sourcing; needs PEXELS_API_KEY
scripts/chartgen.py      renders a `chart:` block into the hero image
scripts/factcheck.py     sourcing gate — fails the build on an unsourced figure
scripts/commentary.py    fair-use limits for commentary posts
scripts/validate.py      pre-publish gate; CI fails the deploy if this fails
scripts/new_post.py      scaffolds a correctly-shaped post file
site.config.json         name, domain, categories, AdSense + analytics IDs
content/posts/*.md       articles, named YYYY-MM-DD-slug.md
content/pages/*.md       about, contact, legal and policy pages
dist/                    build output (git-ignored; GitHub Actions rebuilds it)
```

## Categories

| slug | use for |
| --- | --- |
| `specs` | what a given number measures, how it is gamed, who certifies it |
| `hdr` | DisplayHDR / True Black tiers, peak and sustained luminance, local dimming |
| `panels` | QD-OLED, WOLED, tandem OLED, Mini-LED, IPS, VA — structure and consequences |
| `motion` | response time, overdrive, ClearMR, VRR, input lag, frame pacing |
| `connections` | HDMI, DisplayPort, DSC, USB-C alt mode, cable certification, bandwidth maths |
| `setup` | picture modes, HDR in Windows/console, ICC profiles, subpixel rendering |

Aim over time for roughly: 30% `specs`, 20% `hdr`, 20% `panels`, 15% `motion`,
10% `connections`, 5% `setup`. `specs` and `hdr` carry the highest search volume and the
strongest advertiser demand; `connections` is small but converts unusually well because
the queries are desperate ("why is my 4K 144Hz not working"). Never let the target mix
override the judgement of what is actually worth writing.

## Post front matter — required fields

```yaml
---
title: "Full headline, written for a human"
slug: url-slug-with-primary-keyword
seo_title: "Under 44 chars — becomes <title> + ' | PanelProof'"
meta: "110-158 char meta description. Primary keyword plus a reason to click."
category: hdr
date: 2026-08-12
updated: 2026-08-12
description: "On-page standfirst. One or two sentences. May exceed `meta`."
image_alt: "Describes the hero image, for screen readers"
tags: [five, to, eight, specific, tags]
about: ["Entity names for schema.org — VESA, DisplayHDR, Samsung Display"]
key_takeaways:            # 4-6 items, written to be quoted verbatim by answer engines
  - text: "Lead with the number. **Bold the figure.** Name the spec revision."
    source: 1
faq:                      # 5-6 real questions, answered completely
  - q: "A question someone would actually type"
    a: "A complete answer in 2-5 sentences."
resources:                # 4-6 documents or tools the reader can open themselves
  - title: "VESA DisplayHDR performance criteria"
    url: "https://displayhdr.org/performance-criteria/"
    note: "The tier table itself — read it rather than the badge"
sources:
  - title: "Document title"
    url: "https://..."
    publisher: "VESA"
    accessed: 2026-08-12
    primary: true
---
```

## Body conventions

- **1,400–2,600 words.** Under 900 fails validation.
- **Answer the title question completely in the first 150 words.** Retrieval-based
  answer engines weigh opening content heaviest; a build-up costs you the citation.
- **H2s are questions or claims**, never labels. "Why a DisplayHDR 400 badge means
  almost nothing", not "Analysis".
- **Tables for anything comparative.** They win featured snippets, they get lifted
  wholesale by AI answers, and they are genuinely clearer for tier data.
- **Callouts**, 3–5 per article:
  - `> [!KEY]` the number that matters
  - `> [!TIP]` something actionable
  - `> [!WARNING]` a trap or an out-of-date belief
  - `> [!ACTION]` a checklist
  - `> [!NOTE]` context
- **Internal links**: 2–4 per article, descriptive anchor text, in the body.
- **Close** with a dated sourcing line: *"Specifications current as of DD Month YYYY…"*.
- **Never write**: "In today's fast-paced world", "delve", "tapestry", "landscape",
  "it's important to note", "game-changer", "when it comes to", or a listicle of
  generic advice. Never open with "In the world of displays".

## GEO — writing to be cited by answer engines

The takeaways block, the FAQ, the tables and the dated figures exist because ChatGPT,
Perplexity, Gemini and Google's AI Overviews lift them. Rules that follow from that:

- **Each takeaway must stand alone.** True and comprehensible with zero surrounding
  context, and naming its own source and revision. Assume it will be quoted with
  everything else stripped away.
- **Put the direct answer in the first two sentences under each H2.** Elaborate after.
- **Prefer specific numbers to adjectives.** "0.0005 cd/m² maximum black level" is
  citable; "extremely deep blacks" is not.
- **Name the standard, the revision and the issuing body in the sentence itself**, not
  only in the source list. Answer engines cite what they can attribute inline.
- **One idea per paragraph**, and keep paragraphs short enough to be extractable.
- **Define the term before using it.** A retrieved chunk has no earlier paragraphs.

## Sourcing standard (enforced by `scripts/factcheck.py`)

### `sources:`

```yaml
sources:
  - title: "DisplayHDR Performance Criteria (CTS 1.2)"
    url: "https://displayhdr.org/performance-criteria/"
    publisher: "VESA"
    accessed: 2026-08-12
    primary: true
```

* at least **3** sources, at least **1** marked `primary: true`
* `primary` here means the standards body, the panel maker's datasheet, the
  manufacturer's own specification page, or a named lab's published measurement.
  TFTCentral reporting a VESA tier is not primary — VESA is. RTINGS publishing its
  own measurement *is* primary for that measurement.
* `accessed` may not be in the future, nor more than 400 days before the post date
* every URL is fetched during validation; a dead link fails the build

### `key_takeaways:`

```yaml
key_takeaways:
  - text: "True Black 1400 requires **1400 cd/m²** peak and **700 cd/m²** full-screen."
    source: [1, 2]
```

* every takeaway carries at least one source index that resolves
* every takeaway contains a bolded span with a digit. No number, not a takeaway.

### What the gate does *not* check

Body prose is not machine-verified. Opening each primary document and confirming each
figure is still a human job, and it is the part that matters most.

## Artwork

Generated at build time from the post itself — nothing to source or license.

Order of preference: the article's own data → a licensed photograph → typography.
Each step degrades silently, so a missing key never breaks a build.

* **`chart:` block** → the hero becomes a real chart of those numbers, in the site
  palette, with the source named on the image. Tier thresholds plot beautifully.
* **`PEXELS_API_KEY` set and no chart** → a photograph, credited to the photographer.
* **Neither** → a typographic cover: category, headline, and the lead bolded figure.

**`hero:` overrides that order** — `hero: photo` forces a photograph even on a post
that declares a chart, `hero: cover` forces the typographic cover, `hero: chart` is
the default wherever a chart exists.

Use it deliberately. Charts are this site's signature, but a homepage of nothing but
charts reads as a template rather than a publication, and the cards all blur together
in a feed. Aim for roughly **half charts, half photographs** across recent posts, and
put the photograph on the pieces whose value is explanatory rather than numeric — a
panel-technology comparison earns a photograph; a tier-threshold table earns its chart.

Never invent numbers to justify a chart.

## Commentary posts (responding to another outlet)

```yaml
commentary:
  source_title:  "Headline as published"
  source_outlet: "The outlet"
  source_url:    "https://..."
  source_date:   2026-08-13
  quote:         "One short verbatim sentence."   # 40 words maximum
  quote_context: "what that passage was describing"
```

Enforced: one quote only, ≤40 words, complete attribution with an absolute URL,
≥1,200 words of your own prose, and a headline that does not restate theirs.

**What makes this lawful is not the link.** It is lawful because the quotation is
minimal, the commentary is substantial and original, and it does not substitute for
reading the original. Never screenshot another outlet's page or reuse their photography.

## Daily workflow

See `automation/daily-post.md`. In short: pick the query → read the primary documents →
verify every figure → write → `python3 build.py` → `python3 scripts/validate.py` →
`git commit && git push` → GitHub Actions deploys.
