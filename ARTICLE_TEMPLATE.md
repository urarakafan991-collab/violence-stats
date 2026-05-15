# TruthBased.org Article Template

Reference for what every new article needs. Two files are touched: a new
`<slug>.html` at repo root, and a new row added to the right section in
`index.html`.

For early-access publishing, see `EARLY_ACCESS_CHECKLIST.md` — that's the
*workflow*. This file is the *structure*.

---

## 1. File outputs per new article

1. **`<slug>.html`** at the repo root — the article itself. Kebab-case slug matching the existing pattern (e.g. `does-x-cause-y.html`).
2. **One new `<a class="article-row">` block in `index.html`**, inside the correct section's `<div class="article-list">`.
3. **One new `<url>` entry in `sitemap.xml`** *(only on public promotion — not during early-access window).*

---

## 2. Anatomy of `<slug>.html` — top to bottom

In this order, every article should have:

| # | Element | Purpose |
|---|---|---|
| 1 | `<header class="article-header">` with category eyebrow, h1 title, italic deck, meta-pills row | Identification + at-a-glance metadata |
| 2 | **(political only)** Amber `box-amber` titled "Why this is filed under Political Fact Checks" | States the political stakes / who's using the claim |
| 3 | `<div class="sources-bar">` with linked `source-pill`s | Shows the receipts up front |
| 4 | `<div class="tldr-box">` | One dense paragraph with the headline numbers, bolded |
| 5 | **(optional)** `<div class="scope-box">` italic ethics/scope note | Caveats about what's included/excluded |
| 6 | 2–3 preliminary `<div class="claim-row">` blocks | Misconception / Claim vs Evidence sample pairs |
| 7 | **5–7 numbered `<section>` Parts** | The actual analysis |
| 8 | Final `<div id="summary" class="claims-box">` with 3–6 `claim-row`s | Summary table at the bottom |
| 9 | **`<div class="falsify-box">`** — "What would change this conclusion?" with 2–4 numbered empirical conditions | Popperian close. Most distinctive element on the site. |
| 10 | `<div class="sources-section">` listing every source with author, year, journal/outlet, link | Full bibliography |
| 11 | `<div class="cite-this">` with italic suggested citation | User-selectable citation block |

Outside the `<article>`: the standard `ymal-section` (3 related-article cards), support CTA, and footer.

### Hero meta-pills, standard set

```html
<span class="meta-pill live">● Live</span>
<span class="meta-pill">Last reviewed: <Mon Year></span>
<span class="meta-pill">Data through <Mon Year></span>   <!-- if numeric-heavy -->
<span class="meta-pill">~N primary sources</span>
<span class="meta-pill">~N min read</span>
<a href="/methodology" class="meta-pill">Methodology →</a>
```

### Part header pattern

```html
<section id="partN">
  <div class="part-header">
    <span class="part-label">Part N of M</span>
    <h2 class="part-title">Descriptive heading — usually with em-dash subtitle</h2>
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

- **Em-dash heavy.** "The data shows X — but the methodology has caveats."
- **Hedge ladder**, from strongest to weakest: *settled / well-supported / suggestive but not settled / contested / not supported.*
- **Recurring phrases**:
  - "Every counterargument tested"
  - "Under any consistent methodology"
  - "The claim does not survive contact with the data"
  - "Three databases, every definition" *(for data-driven pieces)*
- Numbers use **tabular-nums**. Primary sources cited inline with author + year.
- Late-article Part titled some variant of **"What the science actually settles — and what it doesn't."**

---

## 5. Meta-conventions

| Property | Typical value |
|---|---|
| Length | 15–45 minute read |
| Primary sources | 15–25 |
| Parts | 5–7 |
| Falsifiability conditions | 2–4 |
| `meta-pill live` | always present once article is public |
| `Last reviewed` | current month/year on publish |
| Methodology link | always in the meta row |

---

## 6. Homepage row — adding to `index.html`

When the article goes public (Phase 2 of `EARLY_ACCESS_CHECKLIST.md`), add this
block inside the correct section's `<div class="article-list">`:

```html
<a href="/<slug>" class="article-row">
  <span class="row-status live">● Live</span>
  <div class="row-body">
    <span class="row-title">Display title — can be different from article h1</span>
    <span class="row-desc">~30–50 word teaser. Lead with the strongest specific finding or the most provocative reframe of the claim.</span>
    <div class="row-sources">
      <span class="source-pill">Source 1</span>
      <span class="source-pill">Source 2</span>
      <span class="source-pill">Source 3</span>
      <!-- 3–5 source pills typical -->
    </div>
  </div>
  <span class="row-arrow">→</span>
</a>
```

**Note**: the homepage `row-title` does not have to match the article's `<h1>`.
Example: row title "Policing, Race & Crime: What the Data Shows" → article h1
"Did Police Funding Cuts Cause the 2020 Crime Surge?" The row title can be the
*evergreen topic frame*; the article h1 can be the *specific question version*.
(Note: title/h1 mismatches like these need explicit alignment — flag to Maya
before publishing if they diverge.)

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
| 06 | Health & Medicine | Medical statistics and health claims vs. peer-reviewed evidence | Vaccines, gender medicine, gender-affirming care patient outcomes, death penalty deterrence |
| 07 | Religion & Society | Measurable claims about religiosity and social outcomes | Does religion cause violence, are religious countries better off |
| 08 | International Comparisons | How U.S. outcomes compare globally | Gun violence vs peer nations, education ranking |

If a topic doesn't fit one of these, the section list itself may need to change
— don't force-fit; ask first.

---

## 8. Pre-publish gut-check

Before pushing a new article to main (even for early access), verify:

- [ ] All 11 anatomical elements present (header, sources bar, TL;DR, prelim claims, parts × N, summary, falsifiability, sources, cite-this — plus the political-context box if political)
- [ ] Falsifiability conditions are concrete and testable (not "if new evidence appears")
- [ ] At least one Part steelmanns the opposing view explicitly
- [ ] Every quantitative claim has an inline source
- [ ] Hedge ladder is honest — overclaiming is a brand violation
- [ ] Homepage row added (for Phase 2 only; *not* during early access)
- [ ] If row title and h1 diverge — both are individually accurate
- [ ] `sitemap.xml` updated (Phase 2 only)
- [ ] If early access: `<meta name="robots" content="noindex,nofollow">` present
