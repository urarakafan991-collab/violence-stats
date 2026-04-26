# CLAUDE.md — Coding standards for TruthBased.org

Maya runs this site solo. Static HTML, 37 files, Vercel auto-deploys on push to main. Every push is live in 15 seconds.

These rules exist because specific bugs happened. Follow them.

## Rules

**1. Think before regex.** Before any regex or non-trivial logic, write out: what should match, what should NOT match, and three adversarial inputs. Test in a REPL before any file is touched.
   *(In April 2026, `,\s*\.` corrupted CSS `rgba(184,58,30,.15)` site-wide. `\.\.(?!\.)` ate 11 legitimate ellipses. Both were preventable with 30 seconds of REPL testing.)*

**2. Read before write.** Always re-read a file immediately before editing it. Files change between turns. Never trust your memory of file contents.

**3. After bulk edits, diff-review adversarially.** Run `git diff`, pick at least 3 random files, and read them asking *"what changed that I didn't intend?"* — not *"did my fix land?"* Look for CSS damage, broken paths, ellipsis loss, and line-count drift outside the expected range.

**4. One logical change per commit.** If you notice a second issue while fixing the first, finish the first, push it, then start the second. Don't bundle.

**5. Ask, don't assume, on ambiguity.** When two valid interpretations exist (e.g., a homepage row title and an article h1 say different things), stop and ask Maya which to align. Don't pick.

**6. Pre-push: state the visible outcome.** Before pushing, name the user-facing change ("favicon will switch from scales to tB" / "no visible change, only meta tags"). If the live site doesn't match, revert before debugging.

**7. Live broke? Revert first.** If a push breaks the live site, revert and push the revert. Investigate after the site is restored.

**8. Disclose, don't oversell.** A commit message that says "complete" when the work is partial is a lie. Write what was done and what wasn't. Same for chat replies.

## Communication style

- Maya doesn't read long messages. Cut summaries. State results in 1-2 lines.
- If you need an answer, put the question on the last line as one sentence.
- Lead with what's blocked, broken, or needs a decision. Bury what's done.
- Don't hedge or pad. If you're unsure, say so directly.
- No emojis, no enthusiasm. Plain text.

## Site notes

- No build system. Edit HTML files directly.
- Chart.js is loaded inline per page; load order matters.
- Theme toggles via `data-theme` attribute on `<html>`.
- Auto-push every commit unless told otherwise.
