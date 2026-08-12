# Setup

Everything needed to take this from a clone to a live, monetisable site.

## 1. Repository and deployment

1. Create a **public** GitHub repository and push this tree to `main`.
2. **Settings → Pages → Source: GitHub Actions.**
3. Push. The workflow builds, validates and deploys.

The workflow needs `contents: write` (already set) so it can commit fetched hero photos
back to the repo. Without that, the runner re-queries Pexels every build and hero images
drift between builds — which also breaks social preview caches and invalidates the
photographer credit that the licence requires.

## 2. Custom domain

1. Register the domain.
2. At your DNS provider, for the apex record, add four `A` records to
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`,
   and a `CNAME` for `www` pointing at `<username>.github.io`.
3. **Settings → Pages → Custom domain**, enter it, and tick **Enforce HTTPS** once the
   certificate is issued (can take up to an hour).
4. Set `domain` in `site.config.json` to the same URL, with `https://` and no trailing
   slash. Canonical URLs, the sitemap, RSS and JSON-LD all derive from it.

## 3. Hero photographs (optional but recommended)

1. Get a free API key at <https://www.pexels.com/api/>.
2. **Settings → Secrets and variables → Actions → New repository secret.**
   Name it exactly `PEXELS_API_KEY`.
3. Do **not** put the key in any file in the repo. The repo is public.

Without the key, articles fall back to a chart hero (if the post declares a `chart:`
block) or a typographic cover. Both are fine; photographs simply perform better socially.

## 4. Search Console and analytics

1. Verify the domain at <https://search.google.com/search-console>, then submit
   `https://yourdomain.com/sitemap.xml`.
2. Create a GA4 property, and put the measurement ID (`G-XXXXXXXXXX`) in
   `analytics.ga4_id` in `site.config.json`. Leave it empty and no analytics code is
   emitted at all — no script, no cookie banner obligation from us.
3. Consent Mode v2 and the cookie banner are already wired in `static/consent.js`.
   Analytics and ad storage default to denied until the visitor consents.

## 5. AdSense

Do not apply on day one. Apply when the site has, roughly:

- 20–30 substantial articles, all passing the gate
- three to six weeks of history and an established publishing cadence
- organic traffic arriving from search, not only from you refreshing it
- every policy page present and accurate

Then: create the AdSense account, add the site, and set `adsense.enabled` to `true` with
your real `publisher_id` in `site.config.json`. While `enabled` is `false` no ad code is
emitted, which is the correct state during review.

The most common rejection reasons for a site like this are thin content, missing policy
pages, and scaled/duplicated content. The publication gate is designed to prevent the
first, `validate.py` enforces the second, and the editorial policy exists to prevent the
third — so the main way to fail is to publish quickly and carelessly.

## 6. Email

`editor@panelproof.com` should actually receive mail before you apply to AdSense — a
contact address that bounces is a real rejection reason. Any forwarding service is fine;
most registrars include one.

## 7. Scheduled publishing

`automation/daily-post.md` is the routine a scheduled Cowork task follows. Two practical
notes:

- Run the task manually once before relying on the schedule. Scheduled runs inherit tool
  approvals granted during a manual run; without that, an unattended run can stall
  waiting for a permission prompt.
- The task needs its working folder connected when it fires.

## 8. Renaming the site

Change `site_name`, `brand`, `domain`, `publisher`, `homepage` and `author` in
`site.config.json`. Everything else — titles, footer, JSON-LD, `llms.txt`, RSS — derives
from those. Then grep for the old name in `content/pages/` and `scripts/` for the
watermark strings.
