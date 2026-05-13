# Early Access Checklist

Publish each new article to $15+ Patreon tiers first, then promote to the public site
1–2 weeks later. Goal: zero search-engine indexing during the early-access window.

---

## Phase 1 — Early access (article live but hidden)

The article must be reachable at its URL (so the Patreon link works) but invisible
to the public homepage AND to search engines.

- [ ] Save the article as `<slug>.html` at repo root (kebab-case slug matching existing pattern, e.g. `does-x-cause-y.html`)
- [ ] In `<head>`, include exactly:
  ```html
  <meta name="robots" content="noindex,nofollow">
  ```
- [ ] Do **NOT** add a row to `index.html` (no homepage card yet)
- [ ] Do **NOT** add an entry to `sitemap.xml`
- [ ] Pre-commit verification:
  ```bash
  grep -n 'noindex' <slug>.html              # must match
  grep -n '<slug>' index.html sitemap.xml    # must be empty
  ```
- [ ] Commit: `Add <slug> (early access, noindex)`
- [ ] Push to main → Vercel auto-deploys
- [ ] After deploy, curl the live URL and confirm `noindex` is in the served HTML
- [ ] Share `https://www.truthbased.org/<slug>` as a $15+ Patreon post

## Phase 2 — Public promotion (after 1–2 weeks)

Article becomes fully discoverable on the site and to search engines.

- [ ] Remove the `<meta name="robots" content="noindex,nofollow">` line from `<slug>.html`
- [ ] Add the article row to `index.html` in the correct section's `<div class="article-list">`, using the existing `<a class="article-row" href="/<slug>">…</a>` format
- [ ] Add a new `<url>` entry to `sitemap.xml`
- [ ] Pre-commit verification:
  ```bash
  grep -n 'noindex' <slug>.html              # must be empty
  grep -n '<slug>' index.html sitemap.xml    # must match in both
  ```
- [ ] Commit: `Promote <slug> to public (early access window ended)`
- [ ] Push to main → Vercel auto-deploys
- [ ] curl the live URL — confirm `noindex` is gone
- [ ] Update the Patreon post: change visibility to public, or delete (your call)

---

## Failure modes to watch for

1. **`noindex` tag deleted by accident** during edits to the article. Search engines
   index the URL during what should be a private window. Always grep before pushing.
2. **Sitemap entry added in Phase 1 by reflex.** Google discovers the URL via the
   sitemap even though the page is `noindex`. The sitemap should only contain
   articles that have completed Phase 2.
3. **Forgetting to remove `noindex` during promotion.** The article goes "public"
   on the homepage but search engines still treat it as noindex — it never ranks.
   Pre-push, state the expected outcome ("article appears in homepage section 0X
   AND is indexable by Google"); verify both after deploy.

---

## Notes

- The two phases are intentionally separate commits. Don't bundle.
- This file is internal documentation. It is not linked from the public site,
  but it is technically reachable at `truthbased.org/EARLY_ACCESS_CHECKLIST.md`
  if guessed. That's acceptable — it's a process doc, not a secret.
- Patreon shares = free marketing. Don't optimize against URL sharing.
