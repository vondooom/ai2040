# AI 2040 — The 15-Year Map

A data-driven projection of AI adoption across 22 occupational categories from 2024 to 2040.

## Quick Deploy to Netlify

### Option A: Drag & Drop (fastest)
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag the entire `ai2040-site` folder onto the page
3. Done — you'll get a live URL in seconds

### Option B: Git Deploy (recommended for ongoing updates)
1. Create a new repo on GitHub (e.g., `ai2040`)
2. Push this folder:
   ```bash
   cd ai2040-site
   git init
   git add .
   git commit -m "Initial deploy"
   git remote add origin git@github.com:YOURUSERNAME/ai2040.git
   git push -u origin main
   ```
3. In Netlify: **New site from Git** → select the repo
4. Build settings: leave blank (static site, no build step)
5. Deploy

### Custom Domain Setup
1. In Netlify: **Site settings** → **Domain management** → **Add custom domain**
2. Enter your domain (e.g., `ai2040.com`)
3. Netlify will give you DNS settings — either:
   - **Option A**: Point your domain's nameservers to Netlify's (easiest)
   - **Option B**: Add a CNAME record pointing to your Netlify URL
4. Netlify auto-provisions SSL via Let's Encrypt

### Before You Deploy — Find & Replace These:
Search the codebase for these placeholders and replace them:

| Placeholder | Replace with |
|---|---|
| `YOURDOMAIN.com` | Your actual domain (e.g., `ai2040.com`) |
| `G-XXXXXXXXXX` | Your Google Analytics 4 measurement ID |
| `@VonDoom` | Your X/Twitter handle (already set) |

These appear in:
- `index.html` (meta tags, OG tags, structured data, GA4)
- `robots.txt` (sitemap URL)
- `sitemap.xml` (canonical URL)

### Google Analytics Setup
1. Go to [analytics.google.com](https://analytics.google.com)
2. Create a new GA4 property
3. Get your Measurement ID (starts with `G-`)
4. Replace `G-XXXXXXXXXX` in `index.html`

### OG Image for Social Sharing
The file `images/og-image.png` is used for X/Twitter and Facebook social cards.
To replace it with your Midjourney hero image:
1. Generate your 5:2 image
2. Crop/resize to 1200x630px for optimal social display
3. Replace `images/og-image.png`

## File Structure
```
ai2040-site/
├── index.html          # The full site
├── netlify.toml        # Netlify config (headers, caching)
├── robots.txt          # Search engine crawl rules
├── sitemap.xml         # SEO sitemap
├── README.md           # This file
└── images/
    ├── og-image.png    # Social sharing image (1200x630)
    ├── era_chart_*.png # Per-era radar charts
    └── delta_*.png     # Per-era bar charts
```

## Tech Stack
- Pure HTML/CSS/JS — no build step, no framework
- Chart.js 4.4.1 via CDN for interactive radar & bar charts
- Google Fonts: Instrument Serif, DM Sans, JetBrains Mono
- Netlify for hosting, SSL, CDN, and headers
