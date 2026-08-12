---
title: "Why your monitor's 1ms response time isn't 1ms"
slug: monitor-response-time-1ms-explained
seo_title: "Why 1ms Response Time Isn't 1ms"
meta: "A 144Hz monitor holds each frame for 6.94ms. So where does 1ms come from? The arithmetic, the cherry-picked transition, and the metric VESA built to replace it."
category: motion
date: 2026-08-12
updated: 2026-08-12
description: "The 1ms on the box is either the single fastest grey-to-grey transition the panel produced with overdrive at maximum, or an MPRT figure achieved by switching the backlight off between frames. Neither describes what you will see."
image_alt: "Bar chart comparing minimum frame duration at common refresh rates against the 1ms figure quoted on monitor boxes"
tags: [response time, GtG, MPRT, overdrive, ClearMR, motion blur, VESA, monitor specs]
about: ["VESA", "ClearMR", "Motion Picture Response Time", "BenQ"]
chart:
  type: bar
  title: "How long one frame is actually on screen, by refresh rate"
  y_label: "Frame duration"
  y_suffix: " ms"
  source: "1 ÷ refresh rate. Compare against the 1ms figure printed on the box."
  series:
    - label: "Frame duration (ms)"
      points:
        - ["60Hz", 16.67]
        - ["144Hz", 6.94]
        - ["240Hz", 4.17]
        - ["360Hz", 2.78]
        - ["480Hz", 2.08]
        - ["\"1ms\" claim", 1.0]
key_takeaways:
  - text: "At 144Hz each frame occupies the screen for **6.94 ms**. A pixel cannot stay visible for less than the frame duration unless the backlight is switched off mid-frame — so **1 ms MPRT at 144Hz is arithmetically impossible** without strobing."
    source: 3
  - text: "BenQ states this in its own documentation: a 144Hz monitor has a **minimum MPRT of 6.9 ms**, and lower figures are reached through black frame insertion and similar techniques."
    source: 3
  - text: "Even at **480Hz**, one frame lasts **2.08 ms** — still more than double the advertised figure."
    source: 3
  - text: "VESA published the ClearMR specification in **August 2022** to replace MPRT, stating that a solely time-based metric \"cannot account for\" overshoot, undershoot and other blur-mitigation techniques."
    source: [1, 2]
  - text: "ClearMR is tested with backlight strobing disabled and overshoot capped — removing the exact technique that produces a **1 ms** MPRT claim from the certified result."
    source: 2
  - text: "ClearMR spans **11 original tiers from 3000 to 13000**, extended to **21000** for 480Hz-class displays; ClearMR 7000 means **65–75×** more clear pixels than blurry ones."
    source: 2
faq:
  - q: "So is 1ms GtG a lie?"
    a: "Not a lie — an unrepresentative selection. GtG measures how long a pixel takes to shift from one grey level to another, and a panel has hundreds of possible transitions with very different speeds. The published figure is generally the fastest one, measured with overdrive at its most aggressive setting. It is a real measurement of a real transition; it is simply not the transition you spend most of your time looking at."
  - q: "What is MPRT and why is it different?"
    a: "Moving Picture Response Time measures how long a pixel remains visible on screen, which is what actually produces perceived motion blur when your eye tracks a moving object. Because it is bounded by frame duration, it cannot go below 1/refresh rate by physics alone. Manufacturers get under that bound by turning the backlight off for part of each frame — black frame insertion or strobing — which genuinely reduces blur but costs brightness and can introduce flicker."
  - q: "Does overdrive fix slow response?"
    a: "It trades one artefact for another. Overdrive overvolts the pixel to force a faster transition; push it too hard and the pixel overshoots its target value, producing a bright trail behind moving objects — inverse ghosting. This is why the 'fastest' overdrive setting on most monitors looks worse than the middle one, and why VESA explicitly limits overshoot and undershoot during ClearMR testing."
  - q: "What should I look at instead?"
    a: "A ClearMR tier if the display has one, because the test conditions are published and strobing is disabled. Failing that, an independent lab's full response-time table — RTINGS and TFTCentral publish heatmaps of all transitions rather than the single fastest one, which tells you what the panel does in the dark transitions where LCDs typically struggle most."
  - q: "Is response time even the thing that matters for motion clarity?"
    a: "Only partly. On a sample-and-hold display — which nearly all monitors are — perceived blur is dominated by how long each frame is held static while your eye continues moving. That is why a 240Hz panel with mediocre pixel response often looks clearer in motion than a 144Hz panel with excellent response. Refresh rate and frame rate do more work than the response-time figure does."
  - q: "Does a higher ClearMR tier always mean a better monitor?"
    a: "It means less motion blur under VESA's test conditions, which is one attribute among many. ClearMR is currently certified in SDR mode, says nothing about colour accuracy, contrast, HDR behaviour or input lag, and — like any certification — is voluntary, so an excellent display may carry no tier at all."
resources:
  - title: "VESA ClearMR programme"
    url: "https://www.clearmr.org/"
    note: "What CMR measures and why VESA considers MPRT inadequate."
  - title: "ClearMR certified products"
    url: "https://www.clearmr.org/certified-products/"
    note: "Check whether a model is certified, and at which tier."
  - title: "ClearMR performance criteria"
    url: "https://www.clearmr.org/performance-criteria"
    note: "The tier boundaries in CMR terms."
  - title: "BenQ — How is monitor response time measured?"
    url: "https://www.benq.com/en-us/knowledge-center/knowledge/gaming-monitor-response-time.html"
    note: "A manufacturer setting out the GtG/MPRT distinction, including the frame-duration limit."
  - title: "Blur Busters motion tests"
    url: "https://testufo.com/"
    note: "Run the UFO test on your own display and see the trailing yourself."
sources:
  - title: "VESA ClearMR — the true quality metric for motion clarity"
    url: "https://www.clearmr.org/"
    publisher: "VESA"
    accessed: 2026-08-12
    primary: true
  - title: "VESA Brings Clarity to Motion Blur in Digital Displays with New Compliance Test Specification and Logo Program"
    url: "https://vesa.org/featured-articles/vesa-brings-clarity-to-motion-blur-in-digital-displays-with-new-compliance-test-specification-and-logo-program/"
    publisher: "VESA"
    accessed: 2026-08-12
    primary: true
  - title: "How is Monitor Response Time Measured?"
    url: "https://www.benq.com/en-us/knowledge-center/knowledge/gaming-monitor-response-time.html"
    publisher: "BenQ"
    accessed: 2026-08-12
    primary: true
  - title: "VESA Adds New Performance Levels to ClearMR and DisplayHDR True Black Standards"
    url: "https://vesa.org/featured-articles/vesa-adds-new-performance-levels-to-clearmr-and-displayhdr-true-black-standards-to-support-display-technology-advances-for-gamers-and-content-creators/"
    publisher: "VESA"
    accessed: 2026-08-12
    primary: true
  - title: "VESA Introduce new ClearMR and DisplayHDR Tiers to Accommodate the Latest Displays"
    url: "https://tftcentral.co.uk/news/vesa-introduce-new-clearmr-and-displayhdr-tiers-to-accommodate-the-latest-displays"
    publisher: "TFTCentral"
    accessed: 2026-08-12
---

The "1ms" on a monitor box is one of two things. Either it is the single fastest grey-to-grey transition the panel produced, measured with overdrive at its most aggressive setting — a real number describing a transition you rarely see. Or it is a Moving Picture Response Time figure, reached by switching the backlight off for part of every frame.

Neither describes what your eyes do with moving content. And the second one is easy to disprove with arithmetic you can do in your head.

## Start with the arithmetic, because it settles the argument

A display at 144Hz draws a new frame every 1/144th of a second. That is **6.94 milliseconds**. Each frame sits on the screen for that long.

A pixel cannot be visible for less time than the frame is displayed — not unless something switches it off partway through. So a genuine MPRT of 1ms at 144Hz is not merely optimistic; it is impossible without intervention.

| Refresh rate | Frame duration | Minimum honest MPRT |
| --- | --- | --- |
| 60Hz | 16.67 ms | 16.67 ms |
| 144Hz | 6.94 ms | 6.94 ms |
| 240Hz | 4.17 ms | 4.17 ms |
| 360Hz | 2.78 ms | 2.78 ms |
| 480Hz | 2.08 ms | 2.08 ms |

Even at 480Hz — the current high end — a frame lasts 2.08 ms, still more than twice the advertised figure.

The interesting part is that manufacturers are not hiding this. BenQ's own knowledge base states plainly that a 144Hz monitor has a minimum MPRT of 6.9 ms, then asks how the same monitor can advertise 1 ms, and answers its own question: black frame insertion, clear motion modes, motion enhancement, frame rate control.

> [!KEY]
> A 1 ms MPRT claim on a 144Hz display is a statement that the backlight is being switched off between frames. That is a real technique with real benefits — and real costs in brightness and flicker — but it is not a description of the panel's speed.

## The GtG number is a best case, not a typical case

Grey-to-grey is the more defensible of the two metrics. It measures how long a liquid crystal takes to rotate from one grey level to another, and it is largely independent of refresh rate.

The problem is selection. A panel has a large matrix of possible transitions, and they are not equally fast. Transitions between dark greys are typically the slowest on LCD, which is exactly where trailing is most visible in dark game scenes. The published figure is generally the fastest transition in that matrix, measured with overdrive turned up.

There is a second, subtler issue: the measurement window. Response time is commonly measured across the 10–90% portion of the transition, which excludes the slow beginning and the slow settling tail — the parts where a visible trail actually lives.

None of this is fabricated. It is a real measurement, reported without its conditions. Which is the recurring theme of every display specification: the number is usually true and almost never sufficient.

> [!WARNING]
> Two monitors both claiming "1ms GtG" can differ by a factor of several in average response across all transitions. The spec sheet cannot distinguish them. A full transition heatmap from an independent lab can.

## Overdrive: the fix that creates the artefact

Overdrive briefly overvolts a pixel to force it toward its target faster. Set conservatively it genuinely improves response. Set aggressively — which is how the marketing figure is obtained — the pixel overshoots the target value before settling back.

The visible result is *inverse ghosting*: a bright halo trailing behind moving objects, which most people find more objectionable than the slight smear it replaced. This is why the highest overdrive setting on most monitors is not the one to use, and why the setting is usually buried in the OSD under a name like "AMA", "Response Time" or "Overdrive" with values that mean nothing to anyone.

This artefact is precisely what makes a pure time-based metric misleading. A display can post an excellent response time while producing an image that looks worse.

## What VESA built instead, and why it is harder to game

VESA introduced the ClearMR Compliance Test Specification in August 2022 with an unusually direct rationale. Its statement of the problem:

> Current methods, such as MPRT, fail to reflect the true nature of blur because a solely time-based metric cannot account for a number of image enhancement and blur mitigation techniques, such as excessive overshoot and undershoot.

ClearMR measures Clear Motion Ratio: the ratio of clear pixels to blurry pixels when a test pattern moves across the screen, captured with a high-speed camera and verified with a colorimeter. Higher is better.

Three details in the test protocol matter more than the metric itself:

1. **Backlight strobing is disabled during testing.** The single technique that produces "1 ms MPRT" is switched off, so it cannot inflate the result.
2. **Overshoot and undershoot are limited.** A display cannot buy a higher tier by cranking overdrive into inverse ghosting.
3. **Testing is in the default power-up configuration**, at native resolution and maximum frame rate, after warm-up, at ambient room temperature. Not in a hidden mode nobody uses.

The tiers ran from ClearMR 3000 to ClearMR 13000, and VESA added 15000, 18000 and 21000 to accommodate 480Hz-and-above displays. ClearMR 7000 corresponds to a CMR range of 65–75× more clear pixels than blurry ones; ClearMR 21000 to roughly 195×.

> [!TIP]
> ClearMR currently certifies in SDR mode. If you care mainly about HDR gaming, the tier is still informative about panel and overdrive behaviour, but it was not measured in the mode you will use.

## The thing the whole discussion tends to miss

Nearly every monitor is a sample-and-hold display: each frame is held static until the next one replaces it. Your eye, meanwhile, tracks moving objects continuously. The resulting mismatch — eye moving, image static — produces blur that has nothing to do with pixel response speed.

This is why a 240Hz panel with unremarkable pixel response frequently looks clearer in motion than a 144Hz panel with excellent response. Halving the frame duration halves that component of blur directly. It is also why frame rate matters: a 240Hz monitor fed 80 frames per second is displaying each frame for 12.5 ms of eye-tracked motion, whichever number is printed on the bezel.

Backlight strobing attacks exactly this problem, which is why it works — it shortens the time each frame is visible. The cost is brightness, typically flicker at the strobe frequency, and usually incompatibility with variable refresh rate.

> [!ACTION]
> A practical order of operations when comparing displays for motion:
> 1. Check refresh rate, and be honest about the frame rate you will actually run.
> 2. Look for a ClearMR tier — published conditions, strobing disabled.
> 3. If there is no tier, find a full response-time heatmap from an independent lab, not the single headline figure.
> 4. Treat the box's "1ms" as marketing until one of the above corroborates it.
> 5. Run [TestUFO](https://testufo.com/) on the unit you receive, at your overdrive settings.

## What to take from this

The response-time specification is not fraudulent, and the engineers producing these numbers are measuring real things. What is missing is the condition attached to each measurement — the transition selected, the overdrive setting, whether the backlight was strobing.

VESA's response to that was to build a metric where the conditions are published and the shortcuts are prohibited during testing. It is not a complete description of a display, and a tier is still a floor rather than a score. But it is the only motion number on a spec sheet that anybody independent had to sign off on, and that makes it worth more than the four characters printed in the largest font.

For how the same problem plays out in brightness claims, see our breakdown of [what each DisplayHDR tier actually requires](/hdr/displayhdr-tiers-explained/).

*Specifications current as of 12 August 2026. Frame-duration figures are arithmetic from the stated refresh rates. ClearMR tier definitions are VESA's; PanelProof does not measure displays and has not tested any product referenced here.*
