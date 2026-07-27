# Coffee Brothers — Website

A single-page site for Coffee Brothers, a cosy coffee stand on Western Road, by the Mardyke, Cork.

## What's in this folder

```
coffee-brothers/
├── index.html      ← the whole site (HTML + CSS + JS, no build step)
├── images/         ← drop your real photos in here (see list below)
└── README.md       ← this file
```

Everything is self-contained in `index.html` — nothing to compile or install. Open it directly in a browser to preview it, or deploy it as-is.

Fonts (Instrument Serif + Inter + IBM Plex Mono) load from Google Fonts over the internet, so an internet connection is needed to see the intended typefaces — it still works offline, just with fallback fonts.

## Design

Palette is black, wood, and silver — matching the brand colours you gave: a near-black ink base, warm walnut-wood accents (eyebrow marks, tags, the nav dot, the divider under the hero), and cool silver touches on the dark sections (opening-hours times, the marquee text).

## Animations included

- Staggered hero headline reveal on load (each line fades/slides in with its own delay)
- Scroll-triggered fades on every major section (`IntersectionObserver`-based)
- Cursor-follow spotlight glow on the menu cards
- Shimmer sweep on the main "Get Directions" button
- Animated count-up stats (1 stand, 7 days open, 8am weekday opening, 0 bookings required)
- A pausable marquee strip — hover pauses it, and there's a dedicated play/pause button for accessibility
- Everything respects `prefers-reduced-motion`: animations are disabled/instant for anyone with that OS setting on

## About the empty image slots

I don't have real photos of Coffee Brothers, so **I didn't fake any** — every photo slot currently shows a clean, on-brand placeholder (a thin dashed tag with the filename it's waiting for) instead of a stock photo or a broken-image icon. The page still looks fully designed and intentional as-is. As soon as you add a real file with the **exact filename** listed below to `images/`, it swaps in automatically — no HTML edits needed.

## Images to drop in

| Filename | Used for | Recommended size |
|---|---|---|
| `images/hero.jpg` | Full-bleed hero background (top of page) | 1920×1080 or larger, landscape. A wide shot of the stand, ideally in soft morning light |
| `images/stand.jpg` | Story section image + the location card in "Find Us" | 1200×1500, portrait-ish. Straight-on or three-quarter shot of the stand with the counter visible |
| `images/dish-1.jpg` | "Americano" card in the menu grid | 900×1200, portrait |
| `images/dish-2.jpg` | "Flat White" card | 900×1200, portrait |
| `images/dish-3.jpg` | "Filter Coffee" card | 900×1200, portrait |
| `images/dish-4.jpg` | "Daily Bake" card | 900×1200, portrait |
| `images/og-image.jpg` | Social share preview (link unfurl on WhatsApp/Instagram/etc.) — no on-page fallback, just skipped if missing | 1200×630, landscape |
| `images/favicon.png` | Browser tab icon — no on-page fallback, browser just shows its default icon if missing | 512×512, square, ideally your logo mark on a solid background |

Tips:
- Keep photos warm and true-to-life — wood tones, black fittings, brushed-steel equipment all read well against this palette. Avoid heavy colour filters.
- Filenames are case-sensitive on GitHub Pages — match them exactly.
- Large JPGs slow the page down — aim to export photos at roughly 200–500KB each (most photo editors' "web/export" quality ~75–85% gets you there).

## Editing content

Everything is plain text inside `index.html` — search for the text you want to change (e.g. `Western Road` or `8:00am`) and edit it directly. The address, opening hours, phone number, the review, and the Google Maps link are all near the top third of the `<body>`, and the Maps link is repeated in a few places (nav, hero, location card, CTA, footer) — search-and-replace all instances if it ever changes.

The Google Maps link is a search link built from the business name and address (`Coffee Brothers, Western Rd, Mardyke, Cork, T12 CA34`), so it doesn't depend on a specific Google Place ID — it'll work as soon as the listing exists on Google Maps.

## Deploying free on GitHub Pages

This folder is separate from any other site you already host on this machine, so give Coffee Brothers its **own** GitHub repository.

1. **Create a new empty repository on GitHub** named `coffee-brothers` (via github.com → New repository — do not initialize it with a README).

2. **From inside this folder**, initialize git and push:

```bash
cd "D:/Work/Webistes/coffee-brothers"
git init
git add .
git commit -m "Initial Coffee Brothers site"
git branch -M main
git remote add origin https://github.com/<your-username>/coffee-brothers.git
git push -u origin main
```

3. **Turn on GitHub Pages**:
   - Go to the repo on GitHub → **Settings** → **Pages**
   - Under "Build and deployment" → **Source**, choose **Deploy from a branch**
   - Branch: **main**, folder: **/ (root)** → **Save**

4. Wait 1–2 minutes, then your site is live at:

```
https://<your-username>.github.io/coffee-brothers/
```

To publish updates later (e.g. after adding real photos):

```bash
git add .
git commit -m "Add real photos"
git push
```

GitHub Pages redeploys automatically within a minute or two of every push to `main`.
