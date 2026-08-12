# Daily post — the routine

Run by the scheduled Cowork task. Follow it in order. **Step 2 is the one that matters**;
everything else is mechanics.

---

## Step 0 — decide whether there is an article today

There is an article today if at least one of these is true:

- a standards body published or revised something (VESA, HDMI Forum, DisplayPort);
- a new panel generation or specification entered the public record via a datasheet,
  a certification listing or a manufacturer specification page;
- an independent lab published a measurement that contradicts a widely repeated claim;
- there is an evergreen query in the backlog that no one has answered honestly, and the
  primary documents to answer it exist and are readable today.

There is **no** article today if the only available angle requires restating someone
else's reporting, or asserting a measurement nobody published. Skip the day. Google
evaluates helpfulness at site level; a thin post costs more than a missing one.

---

## Step 1 — pick the query, not the topic

Write to a question a person types, not a subject area. "Is DisplayHDR 400 worth it"
is a query. "HDR standards overview" is a subject area, and subject areas rank nowhere.

Check `content/posts/` first. If a post already covers the query, **update it** — new
revision, new tier, corrected figure — rather than publishing a near-duplicate. Two
articles competing for one query is self-inflicted keyword cannibalisation, and the
weaker one drags the stronger one down.

---

## Step 2 — read the primary documents and verify every figure

Non-negotiable, and not delegable to a search summary.

For each figure that will appear in the article:

1. Open the actual document — the VESA CTS page or PDF, the panel datasheet, the
   manufacturer specification page, the lab's measurement page.
2. Read the figure **and its measurement condition**. A luminance number without its
   test patch and duration is not a fact. "600 nits" is meaningless until you know
   whether it is an 8% centre patch, a full-screen flash, or sustained full-screen —
   the three differ by a factor of two under the same certification tier.
3. Record the specification **revision** (CTS 1.1 and CTS 1.2 have different
   requirements at the same tier name) and the date you read it.
4. If a figure cannot be traced to a document, it does not go in the article. Do not
   soften it into a vaguer claim — delete it.

**Never present someone else's measurement as ours.** Attribute by name in the sentence.

---

## Step 3 — write

Follow `CLAUDE.md` conventions: 1,400–2,600 words, answer the title question completely
in the first 150 words, question-form H2s, tables for comparative data, 3–5 callouts,
2–4 internal links, dated sourcing line at the close.

Front matter must carry `key_takeaways` with per-item source indices, `faq`, `resources`
and `sources`. Scaffold with:

```
python3 scripts/new_post.py "Headline" --category hdr
```

Write the takeaways last, and write them as if each will be quoted alone with everything
else stripped away — because that is exactly what an answer engine does with them.

---

## Step 4 — build, validate, publish

```
python3 build.py
python3 scripts/validate.py     # publication gate; must exit 0
git add -A && git commit -m "post: <slug>" && git push
```

GitHub Actions rebuilds, revalidates and deploys. If `validate.py` fails, fix the
article — never the gate.

---

## Step 5 — after publishing

- Confirm the live URL renders and the hero image loaded.
- Add the internal links **from** older relevant posts **to** the new one. New articles
  arrive orphaned, and an orphaned page gets crawled late and ranks slowly.
- If the piece supersedes an older one, update the older one's `updated` date and link
  forward.

---

## Backlog — evergreen queries worth answering properly

Ordered roughly by (demand × how badly it is currently served):

1. What does each DisplayHDR tier actually require, in cd/m²?
2. Why does my monitor say 1ms when it clearly isn't?
3. QD-OLED vs WOLED — which characteristics follow from the panel itself?
4. Is OLED burn-in still a real risk, and what do the warranties actually cover?
5. Why won't my 4K 144Hz work over this HDMI cable?
6. What does ClearMR certify, and how do the tiers map to perceived blur?
7. Does higher refresh rate help if the frame rate is lower?
8. What is the panel lottery, and can you check before you buy?
9. Why does HDR look washed out in Windows?
10. Contrast ratio: native, dynamic, and which number the box is quoting.
11. What does 10-bit colour require end to end, and do you have it?
12. Does local dimming zone count matter more than peak brightness?
13. Why do two units of the same model measure differently?
14. What DSC does to your signal, and when it engages without telling you.
15. Text clarity on OLED: subpixel layout, ClearType, and why it looks fringed.
