# CrawlAlt — SEO validation probe

Static site for **crawl space encapsulation alternatives** niche. Domain: **crawlalt.com**

## Pages

| URL | Target keyword |
|-----|----------------|
| `/` | alternatives to crawl space encapsulation |
| `/negatives.html` | negatives to crawl space encapsulation |
| `/diy-cost-reddit.html` | crawl space encapsulation cost reddit |
| `/tax-credit.html` | can I write off crawl space encapsulation |
| `/checklist.html` | contractor screening (lead magnet, free print) |

## Local preview

```powershell
cd e:\web3\alternatives
python -m http.server 8780
```

Open: http://127.0.0.1:8780/

## Deploy to Cloudflare Pages (recommended)

1. Buy **crawlalt.com** on Namecheap (~$9/yr with coupon).
2. Push this folder to a GitHub repo (or upload via Cloudflare dashboard).
3. Cloudflare Dashboard → **Workers & Pages** → Create → Connect Git → build settings:
   - **Framework preset:** None
   - **Build command:** (empty)
   - **Build output directory:** `/` (repo root = site root)
4. After deploy, **Custom domains** → add `crawlalt.com` + `www` (redirect www → apex).
5. Namecheap DNS: point nameservers to Cloudflare (or CNAME to `*.pages.dev`).

## Google Search Console

1. https://search.google.com/search-console → add property **crawlalt.com**
2. Verify via DNS TXT (Cloudflare one-click) or HTML file
3. **Sitemaps** → submit `https://crawlalt.com/sitemap.xml`
4. **URL inspection** → request indexing for `/` and `/diy-cost-reddit.html`

## GSC weekly checklist (weeks 1–12)

| Week | Check | Pass signal |
|------|-------|-------------|
| 1 | Pages indexed (`site:crawlalt.com`) | 5 URLs in index |
| 2–4 | Performance → Queries | Any impression on "alternatives" / "crawl space" |
| 4 | Top queries list | Target long-tails appear |
| 8 | Impressions total | > 50 cumulative on money pages |
| 8 | Avg position | Main terms < 50 |
| 12 | Clicks | ≥ 1 click = probe alive; ≥ 10/mo = continue |

**Do not** judge success at 2 weeks. Use **4 / 8 / 12 week** gates.

## Refresh Reddit digest

PullPush API rate-limits; script falls back to seed data.

```powershell
python e:\web3\alternatives\scripts\build_reddit_digest.py
python e:\web3\alternatives\scripts\render_pages.py
```

- Live API data replaces seed when ≥10 posts returned.
- Seed = manual coding of Google-visible Reddit threads (honest methodology in page).

## Monetization (after impressions)

1. **Checklist page** — already free; later add optional email capture
2. **Amazon / Home Depot** affiliate links on dehumidifier & vapor barrier sections
3. **Angi / HomeAdvisor** outbound on checklist + contractor section (when traffic exists)

## File map

```
alternatives/
  index.html          # pillar: alternatives comparison
  negatives.html
  diy-cost-reddit.html  # includes theme digest section
  tax-credit.html
  checklist.html      # printable PDF checklist
  css/style.css
  data/reddit_digest.json
  scripts/build_reddit_digest.py
  scripts/render_pages.py
  sitemap.xml
  robots.txt
```
