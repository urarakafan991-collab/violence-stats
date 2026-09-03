# How AI writing gives itself away: consolidated research

Compiled 3 September 2026. Internal reference, not deployed with the site.

## What this file is, and what is missing

On 2 September 2026 nine research reports were commissioned from outside AI
systems, each asked to enumerate the concrete markers that make prose read as
machine-written. The reports were pasted into a working session, assessed,
merged into a single rule set, and applied across all site articles.

**The nine original reports are not recoverable.** They were uploaded as file
attachments, and the session transcript stores only their identifiers, not their
contents. What survives, and what is collected here, is:

1. the research prompt that produced them (`DE_AI_PROMPT.md`, reproduced in full
   in section 5 below);
2. the assessment of which reports were usable and where they disagreed;
3. the merged findings, in the order they mattered for this site;
4. the measured before-and-after data from applying them;
5. the rules now enforced on new articles.

If the reports are needed verbatim, they would have to be commissioned again
using the prompt in section 5.

---

## 1. Assessment of the nine reports

Eight of the nine were usable and agreed with each other more than expected.

One was discarded: a report titled "Deconstructing the Algorithmic Voice." It
was written in the style it claimed to be diagnosing, cited a TruthBased heading
that does not exist, and contradicted the other eight on badges.

Two cautions applied to the remaining eight:

- **Semicolon claims are worthless.** One report said AI avoids semicolons; four
  said AI overuses them. They cannot all be right, and none showed data.
- **Numeric thresholds are soft.** Several "pre-2022 baseline frequency" tables
  appeared to be invented. Treat every number in those reports as a rough guide
  rather than a measurement.

---

## 2. What the eight reports converged on

Ordered by how much each mattered for this site.

### 2.1 Structure that announces itself

The strongest signal, and the one least discussed publicly. Machine-written
long-form tends to wear its scaffolding on the outside:

- "Part 1 of 7" section labels
- TL;DR boxes
- Claim/Evidence grids on every page
- FAQ blocks appended regardless of fit
- Labels like "Falsifiability threshold"
- Bolded lead-ins at the start of paragraphs
- Headings shaped "Topic — Subtitle"

The content underneath can be excellent. The labelling is the tell.

### 2.2 Negative parallelism

Constructions that define a thing by first denying its opposite:

- "not X, but Y"
- "it's not about X, it's about Y"
- "isn't a bug, it's a feature"
- "less about A than B"
- "the narrative frames them as threats; the data frames them as targets"

Three reports flagged this independently as the single most reliable
sentence-level marker.

### 2.3 Aphoristic closers and data-as-agent metaphors

Short quotable sentences placed at the end of a section for effect, and
metaphors that give data a will of its own. Three separate reports named the
same phrase: **"does not survive contact with the data."**

Related: data that "tells a story," "paints a picture," or "frames" something.

### 2.4 Rhythm punctuation

- Em dashes used to append a clause, land a contrast, or set off an aside
- Spaced en dashes used as em dashes
- Rule-of-three stacks for cadence: "Every database. Every time window. Every
  population figure. Every assumption."
- Colon reveals: "The result: underrepresentation." "The mechanism: community,
  not theology."

### 2.5 Taglines

Two reports quoted "Every counterargument tested. No agenda." by name. Any
compressed slogan asserting rigour rather than demonstrating it.

### 2.6 Vocabulary, last and least

The famous words (delve, tapestry, testament, underscore, leverage, navigate,
unpack, holistic, paradigm, landscape) matter less than the structural markers,
and this site's articles already avoided most of them. One report instead
identified the site's own repeated tics, which is the more useful finding:

- "confirmed" / "unconfirmed" used as a verbal reflex
- "explicitly"
- "approximately" where "about" would do
- "methodological" / "methodologically"
- "consistent" / "consistently"

Intensifier and thesis adverbs flagged across reports: dramatically, genuinely,
remarkably, strikingly, starkly, fundamentally, critically, crucially, notably,
importantly, essentially, precisely, simply.

Signposts flagged: "It's worth noting," "In other words," "Put simply," "The
bottom line," "Here's the thing," "Let's," "To be clear," "Make no mistake," "In
short," "Ultimately," "The picture changes," "tells a different story."

### 2.7 What the reports warned against removing

Consistent across all eight, and worth keeping in view because over-correction
does more damage than the original problem:

- Real hedging. Uncertainty language is a feature of careful writing.
- Citations, author-plus-year attributions, technical terms.
- Summaries at the top of long pieces.
- Falsifiability content, as distinct from the label on it.

**Density and clustering are the signal, not any single word.** One em dash
proves nothing. Forty in two thousand words does.

**Word lists go stale within a year. Structure and rhythm tells do not.**

---

## 3. What was measured, before and after

The full pass ran across 33 articles on 2 September 2026. Every number in every
article was verified unchanged before writing.

| Marker | Before | After |
| --- | --- | --- |
| Em dashes | 1,414 (13.9 per 1,000 words) | 389 (3.7 per 1,000 words) |
| Spaced en dashes used as em dashes | 340 | 3 |
| Intensifier and signpost hits | 120 | 18 |
| "Topic — Subtitle" headings | 46 | 0 |
| "Part N of M" labels | present throughout | 0 |
| Read-time and source-count pills | present throughout | 0 |

Other changes in the same pass:

- 11 article decks rewritten from fragment stacks into full sentences
- 22 homepage descriptions rewritten as sentences
- 30 "not X, but Y" sentences rewritten
- "TL;DR" relabelled "Summary"
- "Falsifiability threshold" relabelled "What would change this conclusion"
- All taglines removed sitewide

Five "not just / not only" sentences were deliberately left in place, because in
those cases the construction carried factual content rather than rhythm.

### A caution learned from the pass

Removing marker words mechanically breaks sentences. Deleting "robust" from "one
of the most robust findings in the literature" left "one of the most findings"
on three pages, which went unnoticed until a later check. Any automated pass of
this kind needs a grammar check afterwards, not just a marker count.

---

## 4. The rules now enforced on new articles

Reproduced from `ARTICLE_TEMPLATE.md`, section 4.

- **Plain sentences.** State the finding. Do not announce it, frame it, or land it.
- **Dashes:** at most one em dash per 500 words, and only where nothing else is
  clearer. Never spaced en dashes as em dashes.
- **No negative parallelism.** Say the positive claim.
- **No aphoristic closers.** End sections on the last fact.
- **No data-as-agent metaphors.** Write "the data show."
- **No taglines** anywhere, and no "Every X. Every Y." stacks.
- **No intensifier adverbs.**
- **No signposts.**
- **No colon reveals.**
- **Headings** are plain noun phrases. No "Part N of M" labels.
- **Rule of three** only when the content has three items. Vary sentence length.
- **Keep:** the hedge ladder (settled / well-supported / suggestive but not
  settled / contested / not supported), inline author-plus-year citations,
  technical terms, and the top summary.
- **Site-specific tics to avoid:** "confirmed/unconfirmed" as a reflex,
  "explicitly," "approximately," "methodologically," "consistent."

---

## 5. The research prompt, verbatim

This is the prompt that produced the nine reports, as sent. It is also kept
separately as `DE_AI_PROMPT.md`. It is written to edit one article at a time; the
diagnostic value came from the lists in "WHAT TO REMOVE OR REWRITE," which each
AI expanded on in its report.

```
You are editing one article from TruthBased.org, a fact-checking site. The article is a complete
HTML file. Your only job is to remove the habits that make the prose read as machine-written,
without changing what the article says.

WHAT YOU MAY CHANGE
Only human-readable text between tags: paragraphs, headings, the deck under the title, the text
inside callout boxes, the Claim / Evidence cells, and the falsifiability conditions.

WHAT YOU MUST NOT CHANGE
- Anything inside <head>, <script>, or <style>.
- Any tag, attribute, id, class name, or link. Do not add, remove, or reorder tags.
- Tables, stat-block rows, chart titles, the sources section, and the "Cite this article" block.
  Leave those untouched even if they contain a dash.
- Every number, date, percentage, sample size, study name, author name, journal name, quotation,
  and hedge word (settled, well-supported, suggestive, contested, not supported). The facts and the
  level of confidence stay exactly as written. Do not add facts, remove caveats, or soften or
  strengthen any claim.
- The HTML comment at the end of the file.
- Overall length: stay within 10% of the original word count.

WHAT TO REMOVE OR REWRITE
1. Dashes used as rhythm. Em dashes and spaced en dashes used to append a clause, land a
   contrast, or set off an aside. Target: no more than one dash per 500 words in the whole article.
   Replace with a period and a new sentence, a comma, parentheses, or a colon, or restructure the
   sentence. Dashes inside numeric ranges (1962-1998) are not prose and stay.
2. Reframing pairs: "not X, but Y", "it's not about X, it's about Y", "isn't a bug, it's a feature",
   "less about A than B". State the point once, plainly.
3. Rule-of-three lists used for cadence. Keep the items that carry information; drop the ones that
   are there for rhythm.
4. Intensifier and thesis adverbs: dramatically, genuinely, remarkably, strikingly, starkly,
   fundamentally, critically, crucially, notably, importantly, essentially, precisely, simply.
   Delete them or replace with the specific fact that justified them.
5. Vocabulary that signals machine prose: robust, nuanced, nuance, paradigm, landscape, tapestry,
   delve, underscore, leverage, navigate, unpack, holistic, testament, sheds light, at its core,
   the reality is, when it comes to.
6. Signposting: "It's worth noting", "In other words", "Put simply", "The bottom line", "Here's the
   thing", "Let's", "To be clear", "Make no mistake", "In short", "Ultimately", "This is not a
   contradiction but", "The picture changes", "tells a different story", "the story".
7. Punchline closers: short aphoristic sentences that end a paragraph or section with a flourish
   ("The claim does not survive contact with the data."). Allow at most one in the whole article,
   in the conclusion.
8. Colon reveals ("The result: underrepresentation."). Rewrite as an ordinary sentence.
9. Headings shaped as "Topic - Subtitle" or "Topic: Subtitle". Rewrite as one plain descriptive
   heading.
10. Rhetorical questions used as transitions inside body text. Replace with a statement.
11. Bold used on phrases for emphasis rhythm. Keep bold only on the specific finding or number a
    reader needs to find quickly.
12. Uniform sentence length and repeated parallel structure. Vary sentence length. Merge short
    punchy fragments into ordinary sentences where the fragment adds no information.
13. "But", "Yet", or "And" opening consecutive sentences for punch.

WHAT TO KEEP
The site's voice: plain, direct, specific, skeptical of both sides. Author-plus-year citations
inline. The steelman sections must still present the opposing case at full strength. Do not make
the prose blander by deleting specifics; make it plainer by deleting flourishes.

OUTPUT
1. The complete file in a single code block, changed only where the rules above required it.
2. Below the code block, a short list: em dashes before and after, spaced en dashes before and
   after, and the categories of edits made, with rough counts.
3. Any sentence you could not fix without changing meaning: leave it as it was and list it.

Before you output, check: every number in the original still appears unchanged; the count of
each HTML tag is identical; nothing inside <head>, <script>, or <style> differs.
```

---

## 6. If this is run again

- Send the prompt to each AI in a separate conversation, without telling any of
  them what the others said. Agreement across independent runs is the only
  signal worth trusting.
- Expect one report in roughly nine to be unusable. Check whether a report
  exhibits the habits it is describing; that is the fastest disqualifier.
- Ignore any frequency table presented without a stated source.
- Re-check grammar after any automated word removal.
