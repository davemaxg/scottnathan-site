# QA Checklist — Scott Nathan Site Rebuild

## Context
- **Original site**: https://baddecisionsbook.com (scottnathan.com redirects here)
- **New site**: https://davemaxg.github.io/scottnathan-site/ (local: /home/openclaw/.openclaw/workspace/scottnathan/)
- **Repo**: https://github.com/davemaxg/scottnathan-site

## Your Job
Run a full QA audit comparing the new site against the original. Produce:
1. A pass/fail result for every check below
2. Fix anything you can fix directly in the HTML/assets
3. Write a final report to `/home/openclaw/.openclaw/workspace/scottnathan/QA-REPORT.md`

---

## Checks to Run

### 1. Link Audit — verify every `href` in index.html
For each link, use curl (follow redirects, -L) to confirm:
- HTTP 200 (or expected redirect to correct destination)
- NOT landing on a 404, generic homepage, or wrong product

Expected destinations:
| Link label | Expected URL |
|---|---|
| Buy on Amazon | https://www.amazon.com/dp/B0CN92GTKY/ |
| Signed Paperback | https://baddecisionsbook.com/product/signed-paperback/ |
| Burning Bridges Tee | https://baddecisionsbook.com/product/burning-bridges-organic-ribbed-neck-t-shirt/ |
| Bad Decisions Mug | https://baddecisionsbook.com/product/bad-decisions-podcast-mug/ |
| Hoodie | https://baddecisionsbook.com/product/unisex-hoodie/ |
| Tee All Colors | https://baddecisionsbook.com/product/bad-decisions-tee-in-all-the-colors/ |
| Organic Ribbed Tee | https://baddecisionsbook.com/product/bad-decisions-100-organic-ribbed-neck-t-shirt/ |
| Apple Podcasts | https://podcasts.apple.com/us/podcast/the-bad-decisions-podcast-with-scott-nathan/id1751541179 |
| Spotify | https://open.spotify.com/show/6FbgytR0w2E4JYYBO88yvf |
| YouTube channel | https://www.youtube.com/user/smnsmn |
| YouTube podcast playlist | https://www.youtube.com/playlist?list=PLTS2Q17qAOsM6LisgRGzdw7_G5ml4QIyr |
| Kickstarter | https://www.kickstarter.com/projects/baddecisions/the-big-book-of-bad-decisions |
| Confessional PDF | https://baddecisionsbook.com/wp-content/uploads/Scott_Nathan_Confessional_Exhibit.pdf |
| Linktree | https://linktr.ee/scottnathan |

### 2. Image Audit — every `src` in index.html
- Confirm every images/* file actually exists on disk
- Confirm no broken `src` paths (wrong filename, typo, etc.)
- Check image file sizes — flag anything over 300KB as a warning
- List any images still using placeholder text instead of real assets

### 3. Content Completeness — compare against original site
Scrape https://baddecisionsbook.com/ and verify the new site contains:
- [ ] Book title and description
- [ ] All 6 celebrity endorsement quotes (exact attributions)
- [ ] All merch items (name + price)
- [ ] Podcast name and all 3 platform links
- [ ] YouTube channel link
- [ ] About/bio text
- [ ] Confessional series mention and link
- [ ] Kickstarter link

### 4. New Features Check — confirm additions work
- [ ] Japanese language toggle button exists in header
- [ ] All `data-i18n` keys have entries in both `en` and `ja` translation objects in the JS
- [ ] No missing translation keys (key exists in HTML but not in JS object)
- [ ] Favicon tag present in `<head>`
- [ ] Canonical URL tag present
- [ ] Open Graph tags present (og:title, og:description, og:image, og:url)
- [ ] Schema.org JSON-LD present for Person and Book
- [ ] All external links have `target="_blank" rel="noopener noreferrer"`
- [ ] Logo SVG loads (file exists at images/logo.svg)
- [ ] Mobile nav hamburger present in HTML

### 5. Fixes
For anything that fails:
- Fix broken image paths directly in index.html
- Fix any missing translation keys in the JS
- Fix any broken/wrong links
- Commit all fixes with message "QA fixes: [summary]" and push to origin main

---

## Report Format
Write `/home/openclaw/.openclaw/workspace/scottnathan/QA-REPORT.md` with:

```markdown
# QA Report — Scott Nathan Site
Date: YYYY-MM-DD

## Summary
- X checks passed
- X checks failed (and fixed)
- X checks failed (needs human action)

## Link Audit
[table: link label | expected URL | actual response | status]

## Image Audit  
[table: filename | size | status]

## Content Completeness
[checklist with pass/fail]

## New Features
[checklist with pass/fail]

## Fixes Applied
[list of what was changed and why]

## Improvements Over Original Site
[bullet list comparing new vs old — SEO additions, performance, features, etc.]

## Remaining Items (Needs Human Action)
[anything that can't be fixed without Scott's input — e.g. missing personal photos]
```

---

## When Done
Run:
```bash
openclaw system event --text "QA complete: scottnathan-site — report at scottnathan/QA-REPORT.md" --mode now
```
