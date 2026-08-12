---
title: "What each DisplayHDR tier actually requires, in cd/m²"
slug: displayhdr-tiers-explained
seo_title: "DisplayHDR Tiers Explained (CTS 1.2)"
meta: "DisplayHDR 400, 600, 1000, True Black 400 and the new True Black 1400 — the exact luminance, black level and contrast each tier requires under VESA CTS 1.2."
category: hdr
date: 2026-08-12
updated: 2026-08-12
description: "Every DisplayHDR badge certifies a specific set of measured thresholds, and they differ by more than the number suggests. Here is the full CTS 1.2 requirement table in plain language, including the True Black 1400 tier VESA added in July 2026."
image_alt: "Grouped bar chart comparing peak and sustained full-screen luminance requirements across DisplayHDR tiers"
tags: [DisplayHDR, VESA, HDR, True Black, local dimming, peak luminance, CTS 1.2, monitor specs]
about: ["VESA", "DisplayHDR", "DisplayHDR True Black", "High Dynamic Range"]
chart:
  type: grouped_bar
  title: "What each tier must actually hit (VESA DisplayHDR CTS 1.2)"
  y_label: "Luminance (nits)"
  source: "VESA DisplayHDR Performance Criteria, CTS 1.2, July 2026"
  series:
    - label: "Peak (8% centre patch)"
      points:
        - ["HDR 400", 400]
        - ["HDR 600", 600]
        - ["HDR 1000", 1000]
        - ["TB 400", 400]
        - ["TB 1000", 1000]
        - ["TB 1400", 1400]
    - label: "Sustained full-screen"
      points:
        - ["HDR 400", 320]
        - ["HDR 600", 350]
        - ["HDR 1000", 600]
        - ["TB 400", 250]
        - ["TB 1000", 500]
        - ["TB 1400", 700]
key_takeaways:
  - text: "DisplayHDR tier numbers refer to peak luminance on an **8% centre patch** — not to full-screen brightness. A DisplayHDR 1000 display need only sustain **600 cd/m²** full-screen under CTS 1.2."
    source: 1
  - text: "The True Black tiers permit a maximum black level of **0.0005 cd/m²** at every tier — **800 times** darker than DisplayHDR 400's permitted 0.4 cd/m²."
    source: 1
  - text: "DisplayHDR 1000 and 1400 require **2D local dimming**: the static contrast minimum is **30,000:1** and **50,000:1** respectively, which an edge-lit panel cannot reach."
    source: 1
  - text: "VESA added **DisplayHDR True Black 1400** on **8 July 2026**, requiring **1400 cd/m²** peak and **700 cd/m²** full-screen — the first tier to demand sustained brightness at that level from an emissive panel."
    source: 2
  - text: "Every tier requires **99%** BT.709 coverage; DCI-P3 coverage is **90%** at tier 400 and **95%** at 500 and above."
    source: 1
  - text: "True Black displays must rise from black to peak in **2 frames**; the LCD-oriented DisplayHDR tiers allow **8 frames**."
    source: 1
faq:
  - q: "Is DisplayHDR 400 worthless?"
    a: "It was close to it under CTS 1.1, and that reputation has outlived the facts. CTS 1.2 introduced a static contrast requirement of 1,300:1 for 1D-backlit displays at tier 400, which VESA states requires either a substantial increase in native panel contrast or the addition of 1D local dimming. It is still the weakest tier by a wide margin — 400 cd/m² peak and a permitted 0.4 cd/m² black level is not a dramatic HDR experience — but a display certified under CTS 1.2 is meaningfully better than one certified under CTS 1.1 carrying the same badge. Check which revision it was certified under."
  - q: "Why is a True Black 400 display dimmer than a DisplayHDR 400 display?"
    a: "Because they are optimising different things. DisplayHDR 400 requires 400 cd/m² in the full-screen flash test; True Black 400 requires only 250 cd/m². But True Black 400 caps black level at 0.0005 cd/m², where DisplayHDR 400 permits 0.4 cd/m². The True Black display is dimmer overall and vastly better in the dark — which is the OLED trade-off expressed as a specification."
  - q: "What does the tier number literally measure?"
    a: "Minimum luminance on an 8% centre patch displayed against a 2% average-picture-level background. That is a small bright element on a mostly dark screen — a highlight, not a scene. It is a reasonable proxy for HDR highlight performance and a poor proxy for how bright the display looks when you open a white document."
  - q: "Can a monitor be genuinely good at HDR without any DisplayHDR certification?"
    a: "Yes. Certification is voluntary and costs money, so some capable displays never submit. The reverse is also true: a badge sets a floor and guarantees nothing above it. Two displays with the same tier can differ enormously in tone mapping, dimming algorithm behaviour and colour accuracy — none of which the tier number captures beyond its minimums."
  - q: "Does DisplayHDR certification cover HDR10, Dolby Vision or HDR10+?"
    a: "All DisplayHDR tiers require support for HDR10, which is the baseline industry format. The certification says nothing about Dolby Vision or HDR10+ support — those are separate licensed formats with their own requirements, and a DisplayHDR-certified display may support neither."
  - q: "What changed in CTS 1.2 compared with CTS 1.1?"
    a: "CTS 1.2, released 7 May 2024, added static contrast ratio requirements measured on a single image, colour accuracy testing across 96 X-Rite ColorChecker patches at three luminance levels, an HDR-versus-SDR black level test, a black crush test, and a subtitle flicker test. It also raised colour gamut requirements and tightened white point tolerances. Displays certified under the older revision were never held to any of it."
resources:
  - title: "VESA DisplayHDR performance criteria table"
    url: "https://displayhdr.org/performance-criteria/"
    note: "The requirement table itself. Read this rather than the badge."
  - title: "DisplayHDR certified products database"
    url: "https://displayhdr.org/certified-products/"
    note: "Check whether a specific model is actually certified, and at which tier."
  - title: "DisplayHDR CTS summary table (PDF, July 2026)"
    url: "https://displayhdr.org/wp-content/uploads/2026/07/DisplayHDR_Chart_2026-July_Full_Table.pdf"
    note: "The same table as a one-page PDF, including the True Black 1400 column."
  - title: "VESA DisplayHDR programme overview"
    url: "https://vesa.org/about-displayhdr/"
    note: "Programme scope, and links to the downloadable CTS documents."
  - title: "VESA DisplayHDR FAQ"
    url: "https://displayhdr.org/faq/"
    note: "VESA's own answers on test conditions and what certification does not cover."
sources:
  - title: "DisplayHDR Performance Criteria — CTS 1.2 summary specification table"
    url: "https://displayhdr.org/performance-criteria/"
    publisher: "VESA"
    accessed: 2026-08-12
    primary: true
  - title: "VESA Introduces DisplayHDR True Black 1400 to Certify Next-Generation OLED Displays"
    url: "https://vesa.org/homepage-article/vesa-introduces-displayhdr-true-black-1400-to-certify-next-generation-oled-displays-for-professional-hdr-content-creation/"
    publisher: "VESA, 8 July 2026"
    accessed: 2026-08-12
    primary: true
  - title: "VESA DisplayHDR programme overview and certified products"
    url: "https://displayhdr.org/"
    publisher: "VESA"
    accessed: 2026-08-12
    primary: true
  - title: "VESA Introduce DisplayHDR True Black 1400 Certification for Future OLED Displays"
    url: "https://tftcentral.co.uk/news/vesa-introduce-displayhdr-true-black-1400-certification-for-future-oled-displays"
    publisher: "TFTCentral, July 2026"
    accessed: 2026-08-12
---

A DisplayHDR badge certifies that a display met a defined set of measured minimums under defined test conditions. It is one of the very few numbers on a monitor box that means something specific, because VESA publishes the compliance test specification and anyone can read it.

The tier number itself is peak luminance in cd/m² on an **8% centre patch against a 2% average-picture-level background** — a small bright highlight on a mostly dark screen. It is not full-screen brightness, and the gap between those two figures is where most of the confusion lives. Under CTS 1.2, a DisplayHDR 1000 display is required to sustain only **600 cd/m²** across the full screen, and a True Black 1000 display only **500 cd/m²**.

Below is the whole requirement set in plain language, current to the specification table VESA republished on 8 July 2026 to add the True Black 1400 tier.

> [!KEY]
> The tier number is a *highlight* measurement on 8% of the screen. Sustained full-screen luminance is a separate, always-lower requirement — 320 cd/m² at DisplayHDR 400, 900 cd/m² at DisplayHDR 1400.

## The two families are not one ladder

DisplayHDR splits into two programmes that are frequently listed together and should not be compared as a single ranking.

**DisplayHDR 400 / 500 / 600 / 1000 / 1400** targets backlit displays — LCDs, with or without local dimming. Black level is limited by how well a backlight can be turned off behind a liquid-crystal layer that leaks light.

**DisplayHDR True Black 400 / 500 / 600 / 1000 / 1400** targets emissive displays, which in practice means OLED. Every True Black tier caps black at **0.0005 cd/m²** regardless of tier, because an emissive pixel is simply switched off.

So the tiers are not interchangeable. True Black 400 is dimmer than DisplayHDR 400 on full-screen content and roughly 800 times darker in black level. Which is better depends entirely on your room and your content, and no ranking captures that.

## The full requirement table

| Requirement (CTS 1.2) | HDR 400 | HDR 600 | HDR 1000 | HDR 1400 | TB 400 | TB 1000 | TB 1400 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Peak, 8% centre patch (cd/m²) | 400 | 600 | 1000 | 1400 | 400 | 1000 | 1400 |
| Full-screen flash (cd/m²) | 400 | 600 | 1000 | 1400 | 250 | 500 | 700 |
| Full-screen sustained (cd/m²) | 320 | 350 | 600 | 900 | 250 | 500 | 700 |
| Max black level (cd/m²) | 0.4 | 0.1 | 0.05 | 0.02 | 0.0005 | 0.0005 | 0.0005 |
| Static contrast minimum | 1,300:1 | 8,000:1 | 30,000:1 | 50,000:1 | n/a | n/a | n/a |
| BT.709 coverage | 99% | 99% | 99% | 99% | 99% | 99% | 99% |
| DCI-P3 coverage | 90% | 95% | 95% | 95% | 90% | 95% | 95% |
| Rise black→peak (frames) | 8 | 8 | 8 | 8 | 2 | 2 | 2 |
| 10-bit signal input | yes | yes | yes | yes | yes | yes | yes |

Three rows in that table do more work than the headline number.

## Why the static contrast row decides the panel

CTS 1.2 introduced a static contrast requirement measured on a *single* image, as distinct from the active-dimming test that compares two different images. The thresholds are chosen deliberately:

- **DisplayHDR 500 and 600** require 1D local dimming or better (7,000:1 and 8,000:1 on a 1D backlight).
- **DisplayHDR 1000 and 1400** require 2D local dimming or better (30,000:1 and 50,000:1).

That single row rules out entire product architectures. An edge-lit monitor cannot reach 30,000:1 static contrast, so it cannot be DisplayHDR 1000 under CTS 1.2 no matter how bright its backlight is. If you want to know whether a display has real local dimming without trusting the marketing, the tier tells you.

VESA also notes that the new contrast requirement at tier 400 demands either a substantial increase in native panel contrast versus CTS 1.1, or the addition of 1D local dimming. This is the single most important thing to know about DisplayHDR 400 in 2026, and it contradicts a great deal of advice still circulating.

> [!WARNING]
> "DisplayHDR 400 is meaningless" was accurate under CTS 1.1 and is out of date under CTS 1.2. The badge looks identical. Check which revision the certification was issued under before applying either judgement.

## The rise-time row separates OLED from LCD in a way brightness does not

DisplayHDR tiers allow up to **8 frames** to rise from black to maximum luminance. True Black tiers allow **2**.

This is the specification acknowledging something structural: a backlight with local dimming has to physically ramp zones, and the algorithm has to decide how fast to do it without producing visible blooming or flicker. An emissive panel does not have that problem. In content with rapid luminance changes — explosions, cuts from dark to bright, scrolling white text on black — that difference is directly visible, and it is not captured anywhere in the tier number.

## What True Black 1400 changed, and why now

VESA announced DisplayHDR True Black 1400 on 8 July 2026. It requires **1400 cd/m² peak**, black level at or below **0.0005 cd/m²**, and — the genuinely new part — **700 cd/m² sustained full-screen**.

Sustained full-screen brightness has historically been where OLED gives ground. Holding 700 cd/m² across the entire panel while keeping black at 0.0005 cd/m² is a substantially harder problem than hitting 1400 cd/m² on a small highlight. VESA attributes the tier's feasibility to tandem OLED architectures — stacking emissive layers to raise luminance without proportionally raising per-layer current.

Roland Wooster, who chairs the VESA task group responsible for True Black, framed the addition as certification keeping pace with panel capability rather than anticipating it. The first certified product VESA named was a laptop, the Lenovo Yoga Pro 16.

> [!NOTE]
> That the flagship emissive tier debuted on a notebook rather than a desktop monitor is a reasonable signal about where tandem OLED is currently shipping in volume. It is not a claim about what desktop panels will do — that will show up in the certified-products database when it does.

## What the badge does not tell you

The certification is a floor. Nothing in it constrains:

- **Tone mapping.** How the display handles content mastered brighter than it can show is entirely the manufacturer's choice, and it is the single largest determinant of whether HDR content looks right.
- **Dimming algorithm behaviour.** Zone count, response speed, blooming and how aggressively the algorithm crushes near-black are untested beyond the minimums.
- **Whether HDR is usable at your brightness setting.** Many displays only meet their certified figures in a specific picture mode that is uncomfortable in a dim room.
- **Uniformity, viewing angle, or panel variation** between units of the same model.

Two displays with the same badge can be very different products. The badge tells you what the manufacturer had to prove, not what they chose to do beyond it.

> [!ACTION]
> Before buying on the strength of an HDR badge:
> 1. Confirm the model appears in the [certified products database](https://displayhdr.org/certified-products/) — the badge on a retail page is not verification.
> 2. Note the CTS revision it was certified under.
> 3. Read the *sustained full-screen* figure for that tier, not the tier number, if you work on bright content.
> 4. Check an independent measurement of real-world peak and of dimming behaviour — see our note on [what response and motion specs leave out](/motion/monitor-response-time-1ms-explained/).

## How to read a spec sheet after this

When a listing says "HDR 1000", three questions settle most of it. Is the model in VESA's certified database, or is that just a marketing number the manufacturer wrote? Which CTS revision? And is the figure you care about the 8% highlight or the sustained full-screen number — because for a colour-graded workflow or a bright room, the second one is the one you will live with.

The tiers are among the more honest specifications in this industry, precisely because the test conditions are public and the thresholds are testable. They are worth learning properly rather than treating as a single score.

*Specifications current as of 12 August 2026, per the VESA DisplayHDR CTS 1.2 summary table republished 8 July 2026. VESA revises this specification periodically; check the linked criteria page for the current revision. PanelProof does not measure displays — the figures here are the certification requirements, not measurements of any product.*
