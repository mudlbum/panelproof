---
title: "Editorial & AI policy"
slug: editorial-policy
seo_title: "Editorial & AI Policy"
meta: "How PanelProof researches, sources, fact-checks and publishes display analysis — including exactly what our AI tooling is and is not permitted to do."
description: "The standards PanelProof holds itself to: sourcing, accuracy, independence, AI disclosure and the automated gate that blocks unsourced figures from publication."
updated: 2026-08-12
---

This page is the standard we hold ourselves to. If an article falls short of it, that is a bug — [tell us](/contact/).

## 1. What counts as a source

A **primary source** for display claims is one of:

- a standards-body compliance document — VESA DisplayHDR CTS, VESA ClearMR CTS, VESA Adaptive-Sync, HDMI Forum specifications, ITU-R recommendations;
- a panel manufacturer's datasheet or published panel specification;
- a display manufacturer's own specification page or technical documentation, quoted as a claim rather than as verified fact;
- a named independent laboratory's published measurement, attributed to that laboratory.

Press releases and news coverage are how we *find* things. They do not establish them. If a figure appears here, it was read off the primary document, not off an article about the document.

## 2. Every figure carries a date and a revision

Standards change. DisplayHDR CTS 1.2 tightened requirements that CTS 1.1 did not have, and a monitor certified under the older revision is not held to the newer numbers. A specification without its revision and date is not a fact — it is trivia with a number in it.

So: every quantitative claim on this site states the specification revision it comes from, or the date the measurement was published, or both.

## 3. We do not measure, and we never imply we do

PanelProof operates no measurement lab. Every measured value here is attributed to whoever took it, with a link and an identification of the methodology where the source describes one.

We will not present a third party's measurement as our own testing, use phrasing like "in our testing" for work we did not do, or illustrate an article with imagery implying we had a review unit.

## 4. Automated publication gate

Editorial standards that live only in a document get skipped under deadline pressure. Ours is enforced in code.

`scripts/factcheck.py` runs before every deploy and **fails the build** if:

- any key takeaway asserts a figure without an index into the article's source list;
- any source is missing a title, URL, publisher or the date it was accessed;
- fewer than three sources are cited, or none is marked primary;
- a source URL no longer resolves;
- a source was accessed too long before the article's publication date to be reliable.

An article that violates any of these cannot reach the site. This is deliberately inconvenient.

## 5. Use of AI

We use AI research and drafting tools, and we would rather tell you than have you guess.

**Permitted:** searching and summarising standards documents; producing first drafts from verified research notes; suggesting structure; copy-editing; generating the abstract cover artwork on articles without a photograph.

**Not permitted:** asserting a figure that no cited document supports. The tooling does not invent expert quotes, does not write personal anecdotes, does not generate photorealistic imagery of products or people, and does not write a word about a product's measured behaviour that is not traceable to a cited measurement.

### How articles reach the site

Be clear about this, because most sites are not. Articles here are researched, drafted **and published automatically**, once they pass the gate described in section 4. A human does not read every article before it goes live.

What stands in for that is machine enforcement, and it is stricter than it sounds: an article cannot publish if any stated figure lacks a resolving source index, if fewer than three sources are cited, if none is a primary document, if any source URL is dead, or if the piece is too short or missing its FAQ, takeaways or policy links. Those are hard failures, not warnings — the deploy stops.

What machine enforcement cannot check is judgement: whether a figure was read in the right context, whether a specification was current, whether the framing is fair. That is reviewed **after** publication, on an ongoing basis, and anything wrong is corrected in public and dated on the [corrections page](/corrections/).

If you would rather read publications that hold everything for human review before release, that is a reasonable preference and this is not one of them.

We also decline the highest-volume tactic in this category outright: we do not rewrite other outlets' articles. Paraphrasing someone else's reporting is a derivative work whether or not you link to them, and it is exactly the pattern search engines classify as scaled content abuse. Where another publication's work matters, we quote a short passage with attribution and then add something they did not say.

## 6. Independence

No sponsored posts. No paid placement. No coverage in exchange for hardware. Advertisers and affiliate programmes have no visibility into the editorial calendar and no opportunity to review anything before publication.

Where an article discusses a product we could earn affiliate commission on, that is disclosed on the page itself, not only in the footer.

## 7. Corrections

We correct in public and we date the correction. Substantive changes are logged on the [corrections page](/corrections/) and noted at the foot of the article. We do not silently edit a figure and move on. See the [corrections policy](/corrections/) for the full procedure and what qualifies.

## 8. What we will not publish

- Rankings assembled from specification sheets without measurement backing.
- "Best of" lists whose ordering we cannot defend from cited data.
- Buying advice about a product nobody has measured, presented as if somebody had.
- Anything whose central claim rests on a source we cannot name.

## 9. Scope and limits

We write about how displays are specified, certified and built. We are not a repair service, we cannot diagnose your particular unit, and panel behaviour varies between production runs of the same model — the well-known "panel lottery" is real, and no article can tell you what arrived in your box.

Questions and challenges: [editor@panelproof.com](mailto:editor@panelproof.com).
