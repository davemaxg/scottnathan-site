# Scott Michael Nathan — New Website

**New site file:** `index.html` (single-file, no build step required)
**Preview URL:** Deploy to any static host and point scottnathan.com DNS there.

---

## Current Site Issues

1. **scottnathan.com redirects immediately to baddecisionsbook.com** — this bleeds all SEO equity away from his personal brand domain. Search engines and users land on a different URL, so scottnathan.com ranks for nothing.
2. **No personal brand hub** — There's nowhere for fans, press, or collaborators to discover Scott *as a person* beyond the book.
3. **Podcast is buried** — The Apple Podcast link is mid-page on the book site with no SEO signal around it.
4. **YouTube has no funnel** — The YouTube channel link exists but receives no contextual promotion.
5. **No structured data** — No Schema.org markup means Google can't understand the entity relationships (person → book → podcast).
6. **No Japanese/international presence** — Lost opportunity given podcast growth in non-English markets.

---

## SEO Recommendations

### Keyword Strategy
Target these clusters:

| Cluster | Keywords |
|---|---|
| Personal brand | "Scott Michael Nathan", "Scott Nathan author", "Scott Nathan photographer Los Angeles" |
| Book | "Big Book of Bad Decisions", "Bad Decisions book Scott Nathan", "Hollywood memoir" |
| Podcast | "Bad Decisions Podcast", "Bad Decisions Podcast Apple", "Scott Nathan podcast" |
| Photography | "Scott Nathan photographer", "Scott Nathan Frieze Art Fair" |

**Long-tail wins:** "Scott Nathan celebrity stories book", "Hollywood comedian memoir bad decisions"

### Fix the Redirect Problem
- Either **point scottnathan.com to this new site** (recommended), or
- Set a **301 redirect from baddecisionsbook.com → scottnathan.com** after the new site is live
- The personal domain is more brandable and defensible long-term

### On-Page SEO (Already Implemented)
- ✅ Optimized `<title>` tag
- ✅ Meta description with keywords
- ✅ Open Graph + Twitter Card tags
- ✅ Canonical URL set to scottnathan.com
- ✅ Schema.org Person JSON-LD
- ✅ Schema.org Book JSON-LD
- ✅ hreflang for en + ja
- ✅ Semantic HTML sections with proper heading hierarchy

### Structured Data to Add Later
- **Podcast schema** (`@type: PodcastSeries`) — Google can surface episodes directly in search
- **Review/Rating schema** — The celebrity blurbs can be marked up as `Review` objects
- **Event schema** — If Scott does book tours, signings, or live podcast recordings

### Technical SEO
- **Page speed**: The current site (baddecisionsbook.com) is WordPress-heavy. This new static HTML file loads in under 1 second.
- **Core Web Vitals**: Single-file HTML with no render-blocking JS = excellent LCP/FID/CLS scores
- **HTTPS**: Required — all hosts below support it free via Let's Encrypt/CloudFlare
- **Sitemap**: Not needed for a single-page site, but add `/sitemap.xml` if you expand to multi-page
- **robots.txt**: Add a simple one: `User-agent: * / Allow: /`

### Backlink Strategy
- Submit to podcast directories (already on Apple + Spotify — good)
- Get baddecisionsbook.com to link back to scottnathan.com prominently
- Press coverage: LA Times, Vulture, etc. — pitch the "Hollywood stories from a misfit-magnet" angle
- Guest podcast appearances → request hosts link to scottnathan.com in show notes
- Frieze Art Fair retrospective coverage — get those links pointing to scottnathan.com

### Content Expansion (Phase 2)
- **Blog/journal** — "Bad Decisions" stories as text content = long-tail SEO goldmine
- **Press page** — PDF kit, hi-res photos, quotes — improves E-A-T (Expertise, Authority, Trust)
- **Episode archive** — Individual pages for podcast episodes = massive SEO surface area
- **Photo portfolio** — Each series as a separate page with alt text

---

## Priority Order: Scott's Three Goals

### 1. 📚 Sell the Book (Primary)
- Hero section leads with book CTA
- Signed copy available for $35 (premium offer)
- Celebrity endorsements are social proof driving purchase decisions
- Fix: When real book cover image is added, it should be the most prominent visual on the page

### 2. 🎙️ Apple Podcast (Secondary)
- Podcast section appears immediately after the book
- Apple Podcasts gets visual hierarchy as the primary listen option (over Spotify/YouTube)
- Add Apple Podcast embed player code (available from Apple Podcasts Connect)
- **Key action**: Get Hurrdat Media to link back to scottnathan.com from their network

### 3. 🎥 YouTube (Third)
- Dedicated YouTube section with subscribe CTA
- YouTube also listed in podcast section (podcast playlist)
- Podcast clips are the best YouTube growth strategy — repurpose every episode

---

## Japanese Market Notes

### Why the Toggle Matters
- Apple Podcasts has massive penetration in Japan — Japanese users discovering the podcast may search "Scott Nathan" in Japanese contexts
- Hollywood memoir / celebrity culture content travels well internationally
- The toggle was implemented with full Japanese text for all UI elements
- `hreflang` tags signal to Google that Japanese-language visitors should see the Japanese version

### How to Expand
1. **Add Japanese social proof**: If any Japanese press has covered Scott, add that to the ja translations
2. **Localize podcast description**: Work with a native speaker to refine the Japanese translations for nuance
3. **Consider a Japanese-specific landing page** at `/ja/` for SEO targeting Japanese search queries
4. **Podcast subtitles**: Adding Japanese subtitles to YouTube episodes dramatically increases discoverability in Japan

---

## Deploying the New Site (Free Options)

### Option A: GitHub Pages (Recommended — Free)
```bash
# 1. Create a repo: github.com/new (name it "scottnathan-site" or similar)
# 2. Upload index.html
# 3. Settings → Pages → Deploy from main branch
# 4. Point scottnathan.com DNS to GitHub Pages:
#    A records: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
#    CNAME: www → yourusername.github.io
```

### Option B: Netlify (Free, Drag & Drop)
1. Go to netlify.com → drag the `scottnathan/` folder onto the deploy zone
2. It gives you a free URL instantly (e.g., `scott-nathan.netlify.app`)
3. Add custom domain: scottnathan.com → point DNS to Netlify's servers

### Option C: Vercel (Free)
```bash
npm i -g vercel
cd scottnathan/
vercel --prod
# Follow prompts, then add custom domain in Vercel dashboard
```

### DNS Change (All Options)
Once deployed, go to wherever scottnathan.com is registered (GoDaddy/Namecheap/etc.) and:
1. Remove the current redirect (currently forwarding to baddecisionsbook.com)
2. Add the DNS records for the chosen host
3. This reclaims all SEO equity for scottnathan.com

---

## What Scott Needs to Provide (To Complete the Site)

| Item | Where It Goes | Notes |
|---|---|---|
| Headshot / portrait photo | Hero circle + About section | 400×400px min, JPG/WebP |
| Book cover image | Book section | 600×800px min |
| 8 portfolio photos | Gallery section | Any aspect ratio — square crops work best |
| Apple Podcast embed code | Podcast section | Get from: podcasts.apple.com → your show → Share → Embed |
| Amazon direct buy link | Book CTAs | If different from baddecisionsbook.com |
| Contact info (optional) | Footer | Email or booking form |

---

*Built for David Golden by NSA1 — 2024*
