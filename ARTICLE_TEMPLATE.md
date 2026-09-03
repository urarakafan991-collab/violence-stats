# TruthBased.org Article Template

Reference for what every new article needs. Two files are touched: a new
`<slug>.html` at repo root, and a new row added to the right section in
`index.html`.

Publishing is one step: add the file, add the homepage row, add the sitemap entry, push.

---

## 1. File outputs per new article

1. **`<slug>.html`** at the repo root — the article itself. Kebab-case slug matching the existing pattern (e.g. `does-x-cause-y.html`).
2. **One new `<a class="article-row">` block in `index.html`**, inside the correct section's `<div class="article-list">`.
3. **One new `<url>` entry in `sitemap.xml`** and a line in `llms.txt`.
4. **Rebuild the search index**: `python3 build_search_index.py`, which regenerates `search-index.js` so the new article is searchable by its own headings and terms.

---

## 2. Anatomy of `<slug>.html` — top to bottom

In this order, every article should have:

| # | Element | Purpose |
|---|---|---|
| 1 | `<header class="article-header">` with category eyebrow, h1 title, italic deck, meta-pills row | Identification + at-a-glance metadata |
| 2 | **(political only)** Amber `box-amber` titled "Why this is filed under Political Fact Checks" | States the political stakes / who's using the claim |
| 3 | `<div class="sources-bar">` with linked `source-pill`s | Shows the receipts up front |
| 4 | `<div class="tldr-box">` labeled **Summary** | One paragraph in full sentences with the headline numbers. Not "TL;DR", not fragments. |
| 5 | **(optional)** `<div class="scope-box">` italic ethics/scope note | Caveats about what's included/excluded |
| 6 | 2–3 preliminary `<div class="claim-row">` blocks | Misconception / Claim vs Evidence sample pairs |
| 7 | **5–7 numbered `<section>` Parts** | The actual analysis |
| 8 | Final `<div id="summary" class="claims-box">` with 3–6 `claim-row`s | Summary table at the bottom |
| 9 | **`<div class="falsify-box">`** labeled "What would change this conclusion" with 2–4 numbered empirical conditions | Keep the content; keep the label plain. |
| 10 | `<div class="sources-section">` listing every source with author, year, journal/outlet, link | Full bibliography |
| 11 | `<div class="cite-this">` with italic suggested citation | User-selectable citation block |

Outside the `<article>`: the standard `ymal-section` (3 related-article cards), support CTA, and footer.

### Hero meta-pills, standard set

```html
<span class="meta-pill live">● Live</span>   <!-- kept in markup, hidden by the stylesheet -->
<span class="meta-pill">Last reviewed: <Mon Year></span>
<span class="meta-pill">Data through <Mon Year></span>   <!-- if numeric-heavy -->
<a href="/methodology" class="meta-pill">Methodology →</a>
```

### Part header pattern

```html
<section id="partN">
  <div class="part-header">
    <h2 class="part-title">Plain descriptive heading. No "Topic — Subtitle" or "Topic: Subtitle" form.</h2>
  </div>
  <span class="section-label">Optional subheading</span>
  <p>…</p>
</section>
```

One Part is almost always a variant of **"The Strongest Case for [opposing view]"** — explicit steelmanning is a brand convention. On controversial topics, two consecutive Parts often steelman each side ("Strongest case for X" / "Strongest case for Y") before a "What the science actually settles" Part.

---

## 3. Reusable components

### `box-green` — confirmed / key finding
```html
<div class="box box-green">
  <span class="box-label">The central scientific paper</span>
  <p>…</p>
</div>
```

### `box-amber` — caveat / framing
```html
<div class="box box-amber">
  <span class="box-label">A note on methodology</span>
  <p>…</p>
</div>
```

### `claim-row` — misconception / claim vs evidence (in a `claims-box` or inline)
```html
<div class="claim-row">
  <div class="claim-cell">
    <span class="claim-cell-label claim-said">Claim</span>"…"
  </div>
  <div class="claim-cell">
    <span class="claim-cell-label claim-data">Evidence</span>…
  </div>
</div>
```

### `stat-block` — structured numerical findings
```html
<div class="stat-block">
  <div class="stat-block-header">
    <span class="stat-block-name">Study name — short id</span>
    <span class="stat-block-period">Journal, N=…</span>
  </div>
  <div class="stat-block-body">
    <div class="stat-row"><span class="stat-key">Metric</span><span class="stat-val positive">value</span></div>
    <div class="stat-row"><span class="stat-key">Metric</span><span class="stat-val neutral">value</span></div>
    <div class="stat-row"><span class="stat-key">Metric</span><span class="stat-val warn">value</span></div>
    <div class="stat-row"><span class="stat-key">Metric</span><span class="stat-val negative">value</span></div>
  </div>
</div>
```
`positive` → ✓ prefix, `negative` → ✗, `warn` → ⚠, `neutral` → em-dash.

### `falsify-box` — required near end of article
```html
<div class="falsify-box">
  <span class="falsify-label">What would change this conclusion?</span>
  <p>This article concludes [X]. This would change if:</p>
  <p><strong>1.</strong> Specific empirical condition.</p>
  <p><strong>2.</strong> Specific empirical condition.</p>
  <p><strong>3.</strong> Specific empirical condition.</p>
</div>
```
Conditions must be *concrete and empirically testable*. Don't write "if new evidence emerged" — write what kind of evidence, of what magnitude.

### `sources-section` — bibliography
```html
<div class="sources-section">
  <span class="sources-section-label">Full Sources & References</span>
  <div class="source-item">
    <strong>Author A., Author B. (Year)</strong> — Paper title.
    <em>Journal</em>. <a href="…" target="_blank" rel="noopener noreferrer">Identifier</a>
  </div>
  <!-- repeat for each source -->
</div>
```

### `cite-this` — suggested citation
```html
<div class="cite-this">
  <span class="cite-this-label">Cite this article</span>
  <span class="cite-this-text">TruthBased.org. "Title." Month Year.
    https://www.truthbased.org/<slug></span>
</div>
```

---

## 4. Voice conventions

The site was rewritten in September 2026 to remove machine-prose habits. New articles follow the same rules.

- **Plain sentences.** State the finding. Do not announce it, frame it, or land it.
- **Dashes:** at most one em dash per 500 words, and only where nothing else is clearer. Never spaced en dashes as em dashes. Use commas, periods, parentheses, or a colon.
- **No negative parallelism:** no "not X, but Y", "it's not about X, it's about Y", "not just X — Y". Say the positive claim.
- **No aphoristic closers.** End sections on the last fact, not a line meant to be quoted.
- **No data-as-agent metaphors:** nothing "survives contact with the data", "tells a story", "paints a picture", or "frames" anything. Write "the data show", "the estimate is", "the record contradicts".
- **No taglines** anywhere: no "Every counterargument tested. No agenda.", no "Every X. Every Y." stacks, no "every angle".
- **No intensifier adverbs:** dramatically, genuinely, remarkably, strikingly, starkly, fundamentally, crucially, notably, importantly, critically, explicitly. Replace with the number that justified them, or delete.
- **No signposts:** it's worth noting, in other words, put simply, to be clear, that said, the bottom line, at its core.
- **No colon reveals** ("The result: underrepresentation."). Write the sentence.
- **Headings** are plain noun phrases. No numbered "Part N of M" labels.
- **Rule of three:** only when the content has three items. Vary sentence length; merge fragments that add no information.
- **Keep:** the hedge ladder (settled / well-supported / suggestive but not settled / contested / not supported), inline author-plus-year citations, technical terms, the top summary, the steelman section, and the falsifiability conditions. Those carry information; the habits above only decorate it.
- **Site-specific tics to avoid:** "confirmed/unconfirmed" as a verbal reflex, "explicitly", "approximately" (use "about"), "methodologically", and "consistent" as praise.

One Part is still a variant of **"The strongest case for [the opposing view]"**. That is a content convention, not a phrase to repeat.

---

## 5. Meta-conventions

| Property | Typical value |
|---|---|
| Length | 15–45 minute read |
| Primary sources | 15–25 |
| Parts | 5–7 |
| Falsifiability conditions | 2–4 |
| `meta-pill live` | in markup, hidden by the stylesheet |
| `Last reviewed` | current month/year on publish |
| Methodology link | always in the meta row |

---

## 6. Homepage row — adding to `index.html`

Add one list item inside the correct section's `<ul class="home-list">`:

```html
<li><a href="/<slug>">Display title</a><span class="desc">One or two full sentences saying what the article measures and with which sources. No fragment stacks.</span></li>
```

Also add the article to the `articles` array in the search script at the bottom of `index.html` (url, cat, title, keywords, snippet). The `cat` value must be one of the search filter categories used in that array.

**Note**: the homepage title does not have to match the article's `<h1>`, but both must be individually accurate; flag divergences before publishing.

---

## 7. Section-mapping reference

These are the 8 homepage sections and what belongs in each. Pick one per article.

| # | Section | Description in UI | Topics that fit |
|---|---|---|---|
| 01 | Political Fact Checks | Claims politicians make, measured against the record | Voter fraud, party-switch, jobs by president, federal spending, political violence by side, immigration crime, border crisis |
| 02 | History & Myth-Busting | Things everyone "knows," tested against primary documents | Columbus, Hitler-as-socialist |
| 03 | Science & Perception | Viral phenomena explained with primary source neuroscience and physics | The dress, Mandela effect, Mpemba effect |
| 04 | Science & Media Accuracy | What studies actually say vs. how they get reported | Social media + teen mental health, ultra-processed food |
| 05 | Economics & Policy | Contested economic claims vs. BLS, CBO, peer-reviewed data | Wage gap, inflation, federal spending, college ROI, tariffs, minimum wage |
| 06 | Health & Medicine | Medical statistics and health claims vs. peer-reviewed evidence | Vaccines, ultra-processed food, social media and mental health |
| 07 | Religion & Society | Measurable claims about religiosity and social outcomes | Does religion cause violence, are religious countries better off |
| 08 | International Comparisons | How U.S. outcomes compare globally | Gun violence vs peer nations, education ranking |

If a topic doesn't fit one of these, the section list itself may need to change
— don't force-fit; ask first.

---

## 8. Pre-publish gut-check

Before pushing a new article to main, verify:

- [ ] All 11 anatomical elements present (header, sources bar, TL;DR, prelim claims, parts × N, summary, falsifiability, sources, cite-this — plus the political-context box if political)
- [ ] Falsifiability conditions are concrete and testable (not "if new evidence appears")
- [ ] At least one Part steelmanns the opposing view explicitly
- [ ] Every quantitative claim has an inline source
- [ ] Hedge ladder is honest — overclaiming is a brand violation
- [ ] Homepage row added
- [ ] If row title and h1 diverge — both are individually accurate
- [ ] `sitemap.xml` and `llms.txt` updated
