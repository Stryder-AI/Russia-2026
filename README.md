# White Nights & Golden Domes — Russia Itinerary 2026

A single-page interactive landing page for the 8-day Moscow + St. Petersburg trip (28 June – 05 July 2026), designed to be deployed as a static site on Vercel.

## What's inside

- `index.html` — the entire site, self-contained. No build step, no framework. Drop it on any static host.
- `vercel.json` — Vercel config with clean URLs and sensible security headers.

## Features

- Imperial Gold & Deep Red design system with Cinzel / Playfair / Cormorant / Inter typography.
- Interactive per-day photo carousels (auto-advance, swipe, dot nav, pause-on-hover).
- Live Leaflet map plotting the **full journey**: Islamabad → Moscow (flight), Moscow → St. Petersburg (Sapsan), St. Petersburg → Islamabad (return flight) — with animated great-circle arcs, plane/train icons, and a legend.
- Sticky day navigation that highlights the current section on scroll.
- Scroll-reveal animations, parallax hero, and ken-burns photo motion.
- Full `prefers-reduced-motion` support.
- Responsive down to 360px.

## Local preview

Just open `index.html` in a browser, or run:

```bash
npx serve .
# or
python3 -m http.server 8000
```

## Deploy to Vercel

### Option A — CLI (fastest)

```bash
npm i -g vercel
cd russia-itinerary
vercel          # follow the prompts, accept defaults
vercel --prod   # promote to production
```

### Option B — GitHub + Vercel dashboard

1. Push this folder to a new GitHub repo (either as the root or under a subdirectory).
2. Go to https://vercel.com/new, import the repo.
3. If the folder is nested, set **Root Directory** to `russia-itinerary`.
4. Framework preset: **Other**. No build command needed. Output directory: `.` (or leave default).
5. Click **Deploy**.

### Option C — drag & drop

1. Go to https://vercel.com/new
2. Drag the `russia-itinerary` folder onto the page.
3. Done.

## Editing the content

Everything — days, captions, photos, hotel details — lives in `index.html`. The per-day photo sets are JSON inside `data-slides="..."` attributes on each `[data-carousel]` element; change the `src`, `label`, and `caption` fields there.

## Photo credits

All photography is served from **Wikimedia Commons** (`upload.wikimedia.org`) — verified named landmarks (St. Basil's, the Kremlin, Hermitage, Peterhof, Catherine Palace, the Sapsan, etc.) rather than generic stock photos. Images are public-domain or Creative-Commons licensed. If you want to use your own photos, replace the URLs with relative paths (e.g. `./images/day1/kremlin.jpg`) and drop the files in an `images/` subfolder — Vercel will serve them automatically.
