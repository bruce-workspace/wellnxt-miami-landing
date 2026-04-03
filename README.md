# WellNXT Miami X Fest 2026 — Landing Page

Static landing page for the WellNXT Miami X Fest 2026 wellness festival.

**Live site:** https://tickets.wellnxtfest.com
**Cloudflare Pages project:** `wellnxt-miami`
**Staging URL:** https://wellnxt-miami.pages.dev

---

## Structure

```
/
├── index.html          # Single-page site — all HTML + CSS + JS inline
├── assets/             # Images (not tracked by git — upload separately)
│   ├── hero-venue.jpg
│   ├── crowd.jpg
│   ├── promo-food.jpg
│   ├── promo-woman-yoga.jpg
│   ├── speaker-1.jpg … speaker-9.jpg
│   └── speaker-ryan-hawell.jpg
└── README.md
```

No build step. No framework. No node_modules. Just static files.

---

## Deploy workflow

```
git push origin main  →  Cloudflare Pages auto-builds  →  tickets.wellnxtfest.com updates
```

Cloudflare Pages is connected to this repo via GitHub integration. Every push to `main` triggers a production deployment. Every push to another branch creates a preview URL.

**Build settings in Cloudflare Pages:**
- Build command: *(none)*
- Build output directory: `/` (root)
- Root directory: *(leave blank)*

---

## Making changes

1. Edit `index.html` locally
2. Commit and push to `main`
3. Deployment takes ~30 seconds

```bash
git add index.html
git commit -m "your change description"
git push
```

---

## Images / assets

Images are served from the `./assets/` folder. Since they can be large, they are **not** committed to this repo. They live directly on Cloudflare Pages via direct upload.

To add or update an image:
1. Place the file in your local `/assets/` folder
2. Use `wrangler pages deploy . --project-name wellnxt-miami` to push a full deployment including assets, OR upload via the Cloudflare Pages dashboard.

---

## GA4 tracking

The GA4 measurement ID (`G-XXXXXXXXXX`) in `index.html` is a placeholder. Replace it with the real ID from your Google Analytics property.

---

## Before the event

Key things to update in `index.html` before April 18:
- GA4 measurement ID (replace `G-XXXXXXXXXX`)
- Speaker photos (ensure all load correctly on mobile)
- Eventbrite URL (confirm ticket link is live)
- `og:image` path if hero image changes
