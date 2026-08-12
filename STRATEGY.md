# PanelProof — SEO and GEO strategy

Written 12 August 2026. Everything here reflects the search landscape as it stands after
Google's March and May 2026 core updates and the associated spam updates. Revisit it if
another core update lands.

---

## 1. The premise this whole site rests on

Search rewards content that could not have been produced by someone who did not do the
work. In this category almost everything published *could* have been — spec sheets get
restated, review numbers get recycled, and "best monitor 2026" lists get assembled from
retailer copy.

The work nobody is doing is reading the compliance test specifications and reconciling
them against manufacturer claims. That is defensible for three reasons:

- **It requires reading documents most writers will not open.** VESA's CTS is dry, long,
  and free. The barrier is willingness, not access — which means the moat is real but
  only as long as we keep doing it.
- **It cannot be produced by summarising other articles.** Which is exactly the pattern
  Google's March 2026 spam update expanded enforcement against.
- **It produces citable atoms.** "DisplayHDR True Black 1400 requires 700 cd/m² sustained
  full-screen" is the kind of sentence an answer engine lifts whole.

If we ever find ourselves writing something that could have been written without opening
a primary document, that is the signal we have drifted.

---

## 2. What changed in 2026, and what it means for us

**Helpful Content is now a site-level judgement inside the core algorithm.** A minority of
thin pages can drag down pages that are strong. Consequence: publishing nothing on a given
day is cheaper than publishing filler. This is why `automation/daily-post.md` opens with
permission to skip the day.

**The March 2026 core update introduced holistic Core Web Vitals scoring** — LCP, INP and
CLS aggregated into a composite rather than evaluated as independent pass/fail signals.
Consequence: we cannot pass on two and fail on one. The generator's constraints (no JS
framework, no web-font requests, inlined critical CSS, explicit image dimensions, no
client-side data fetch) exist for this. Do not add a third-party script casually; every
one of them is a claim on the composite.

**The March 2026 spam update expanded enforcement against scaled content abuse, expired
domain abuse and site reputation abuse.** Consequences: never mass-generate near-duplicate
pages targeting keyword variations; never buy an expired domain for its history; never
host our content on someone else's authoritative domain to borrow it.

**Google does not penalise AI-assisted content as such** — it penalises content where AI
substituted for expertise rather than accelerating it. Consequence: the human verification
step in `automation/daily-post.md` Step 2 is not ceremony, it is the entire difference
between the two outcomes. Our AI disclosure on `/editorial-policy/` is an asset, not a
liability.

---

## 3. Site architecture: pillars and spokes

Six categories, each eventually anchored by one comprehensive pillar page with spokes
linking up to it. Categories with no articles stay invisible — `build.py` enforces this,
because an empty category page is a thin page.

| Category | Pillar (the definitive page) | Spoke examples |
| --- | --- | --- |
| `hdr` | What each DisplayHDR tier requires ✅ | Is DisplayHDR 400 worth it · local dimming zones vs peak brightness · HDR washed out in Windows |
| `motion` | Why 1ms isn't 1ms ✅ | ClearMR tiers explained · overdrive settings · does refresh rate help below frame rate · VRR flicker |
| `panels` | QD-OLED vs WOLED ✅ | tandem OLED · Mini-LED zone counts · IPS black glow · the panel lottery |
| `specs` | What every monitor spec actually measures | contrast: native vs dynamic · 10-bit vs 8-bit+FRC · colour gamut coverage vs volume |
| `connections` | What your cable and port can actually carry | 4K 144Hz over HDMI 2.1 · DSC explained · USB-C alt mode bandwidth · cable certification |
| `setup` | Getting the display you paid for | HDR in Windows · console picture modes · ICC profiles · ClearType on OLED |

**Internal linking rules**, which matter more than most people credit:

1. Every spoke links up to its pillar with descriptive anchor text.
2. Every pillar links down to at least three spokes as they publish.
3. Cross-category links where the reasoning genuinely connects — the HDR pillar links to
   the motion pillar because both are about unstated measurement conditions.
4. **When a new post publishes, go back and add links to it from older posts.** New pages
   arrive orphaned; an orphaned page is crawled late and ranks slowly. This is step 5 of
   the daily routine and it is the step most often skipped.

**Never publish two articles targeting the same query.** Update the existing one. Two
pages competing for one query is self-inflicted, and the weaker one holds back the stronger.

---

## 4. GEO: getting cited by answer engines

The Princeton work that formalised the term found targeted optimisation can raise source
visibility in generative responses meaningfully. The mechanics that matter here:

**Answer completely in the first 150 words.** Retrieval-based engines (Perplexity, AI
Overviews) weight opening content heaviest. A build-up costs the citation. Every article
here states its answer before it explains it.

**Write takeaways as standalone atoms.** Each key takeaway will be quoted with all
surrounding context stripped. It must therefore be true, comprehensible and attributed on
its own — which is why `factcheck.py` refuses a takeaway without a bolded figure and a
source index. That gate exists for GEO reasons as much as editorial ones.

**Name the standard, the body and the revision inside the sentence.** "Under VESA
DisplayHDR CTS 1.2" is attributable inline; "according to the specification" is not.
Answer engines cite what they can attribute without leaving the sentence.

**Prefer numbers to adjectives.** "0.0005 cd/m² maximum black level" is citable.
"Exceptional blacks" is unquotable filler.

**Tables get lifted whole.** Comparative data belongs in a table, always. The tier table
in the DisplayHDR article is the single most citable object on this site.

**One idea per paragraph, short paragraphs.** A retrieved chunk has no preceding context,
so define terms before using them and keep each chunk self-sufficient.

**Keep AI crawlers allowed.** `robots.txt` explicitly welcomes GPTBot, OAI-SearchBot,
ClaudeBot, PerplexityBot, Google-Extended, Applebot-Extended and others. Blocking them
protects nothing here and removes us from the indexes we want to be cited in.

**Maintain `llms.txt`.** Generated automatically — a clean machine-readable map of the
site with a description per article.

---

## 5. Query targets for the first 90 days

Ordered by demand × how badly currently served. These are queries, not topics.

**Month 1 — establish the pillars (target: 12 articles)**

1. Is DisplayHDR 400 worth it *(the CTS 1.2 nuance nobody has updated for)*
2. What is DisplayHDR True Black 1400 *(new July 2026 — low competition window, act fast)*
3. What does ClearMR mean on a monitor
4. QD-OLED vs WOLED for text / for a bright room
5. Why does HDR look washed out in Windows
6. Why won't my monitor do 4K 144Hz over HDMI
7. What is DSC and does it hurt image quality
8. Native vs dynamic contrast ratio
9. What is the panel lottery
10. Is OLED burn-in still a problem in 2026
11. Do more local dimming zones matter than peak brightness
12. 10-bit vs 8-bit + FRC — do you have real 10-bit

**Month 2 — spoke depth and the two remaining pillars.** Open `specs` and `connections`
with their pillar articles, then fill toward them. `connections` queries convert unusually
well because the searcher has a broken setup in front of them.

**Month 3 — refresh and consolidate.** Update month-1 articles with anything the standards
bodies changed, add the internal links that were missed, and merge any two pages that have
drifted toward the same query.

**Cadence.** Three to four articles a week beats seven. The site-level helpfulness
judgement makes consistency-plus-quality strictly better than volume.

---

## 6. Technical SEO — already built, keep it that way

Handled by `build.py` and enforced by `scripts/validate.py`:

- one `<h1>` per page · `<title>` ≤ 62 chars · meta description 110–165
- canonical URLs on every page · breadcrumbs · semantic HTML
- JSON-LD graph: Organization, WebSite, BreadcrumbList, BlogPosting, FAQPage
- `sitemap.xml`, `rss.xml`, `llms.txt`, `robots.txt`
- alt text on every image, explicit dimensions, lazy loading below the fold
- no JS framework, no web-font requests, inlined critical CSS

Things that would quietly damage this: adding a web font, adding a third-party embed above
the fold, adding an image without dimensions, or letting an ad unit shift layout. The
validator catches some of it. It cannot catch a slow third-party script.

---

## 7. Monetisation sequencing

Do not apply to AdSense before roughly 20–30 substantial articles, three to six weeks of
history, and organic arrivals from search. `adsense.enabled` stays `false` until then —
while false, no ad code is emitted, which is the correct state during review.

The common rejections for a site like this are thin content, missing policy pages and
duplicated content. The publication gate addresses the first, `validate.py` enforces the
second, and the editorial policy exists to prevent the third.

**RPM expectations.** Display and consumer-electronics content sits mid-table: advertiser
demand is real but well below finance or legal. The upside here is affiliate — display
purchases are high-consideration, high-ticket and heavily researched, and a reader who
arrives on "is DisplayHDR 400 worth it" is inside a buying decision. Any affiliate link
must be disclosed on the page, per `/disclaimer/`.

---

## 8. What would break this

- **Publishing to keep a streak.** The single most likely failure. A run of filler damages
  the whole domain under site-level evaluation.
- **Drifting into rankings and best-of lists.** High volume, but it puts us in the
  spec-sheet-restating category we exist to be an alternative to, and we cannot defend the
  ordering without measurements we do not take.
- **Implying testing we did not do.** Reputationally fatal in this niche specifically,
  because the labs whose numbers we cite are read by the same audience.
- **Letting page weight creep.** Composite Core Web Vitals scoring means a single
  regression now costs more than it used to.
- **Forgetting to date figures.** A specification claim without its revision ages into
  misinformation without anybody editing it.
