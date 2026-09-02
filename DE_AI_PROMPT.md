# De-AI Prose Pass — prompt for outside AIs

Paste everything below the line into the AI, then paste the full HTML of ONE article after it.
Run one article per conversation. Save the returned file over the original, then diff it
before committing (numbers, links, and tag counts must be identical).

---

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
1. Dashes used as rhythm. Em dashes (—) and spaced en dashes ( – ) used to append a clause, land a
   contrast, or set off an aside. Target: no more than one dash per 500 words in the whole article.
   Replace with a period and a new sentence, a comma, parentheses, or a colon, or restructure the
   sentence. Keep a dash only where nothing else is clearer. Dashes inside numeric ranges (1962–1998)
   are not prose and stay.
2. Reframing pairs: "not X, but Y", "it's not about X, it's about Y", "isn't a bug, it's a feature",
   "less about A than B". State the point once, plainly.
3. Rule-of-three lists used for cadence ("real, replicated, and not fully explained by"). Keep the
   items that carry information; drop the ones that are there for rhythm.
4. Intensifier and thesis adverbs: dramatically, genuinely, remarkably, strikingly, starkly,
   fundamentally, critically, crucially, notably, importantly, essentially, precisely, simply.
   Delete them or replace with the specific fact that justified them.
5. Vocabulary that signals machine prose: robust, nuanced, nuance, paradigm, landscape, tapestry,
   delve, underscore, leverage, navigate, unpack, holistic, testament, sheds light, at its core,
   the reality is, when it comes to. Use the plain word or cut.
6. Signposting: "It's worth noting", "In other words", "Put simply", "The bottom line", "Here's the
   thing", "Let's", "To be clear", "Make no mistake", "In short", "Ultimately", "This is not a
   contradiction but", "The picture changes", "tells a different story", "the story". Cut the
   signpost and keep the sentence that follows.
7. Punchline closers: short aphoristic sentences that end a paragraph or section with a flourish
   ("The claim does not survive contact with the data." "Community need not be religious."). Allow
   at most one in the whole article, in the conclusion. Elsewhere, end on the finding itself.
8. Colon reveals ("The result: underrepresentation." "The mechanism: community, not theology.")
   Rewrite as an ordinary sentence.
9. Headings shaped as "Topic — Subtitle" or "Topic: Subtitle". Rewrite as one plain descriptive
   heading. Questions are fine as headings only in the FAQ section.
10. Rhetorical questions used as transitions inside body text. Replace with a statement.
11. Bold used on phrases for emphasis rhythm. Keep bold only on the specific finding or number a
    reader needs to find quickly.
12. Uniform sentence length and repeated parallel structure. Vary sentence length. Merge short
    punchy fragments into ordinary sentences where the fragment adds no information.
13. "But", "Yet", or "And" opening consecutive sentences for punch. Once in a while is fine.

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
