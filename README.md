# Raj Rayon Industries Limited — Corporate Website

A fully custom, multi-page corporate website built for **Raj Rayon Industries Limited (RRIL)** — a BSE & NSE-listed polyester yarn manufacturer based in Silvassa, India (est. 1993). The site was designed from scratch to replace RRIL's legacy web presence, restructure their brand story, and showcase their manufacturing process through an original AI-generated industrial video.

🔗 **Live reference site (in progress):** [rajrayon.com](https://www.rajrayon.com) · **Group company:** [SVG Fashions](https://www.svgfashions.com/)

---

## 📸 Overview

RRIL provided a 40-page corporate presentation, their existing website, and a process flow map covering their full production chain — from raw polymer to export-ready yarn. This project translates that material into a modern, animated, single-brand web experience across 6 pages, anchored by a custom **2 minute 30 second AI-generated animated video** depicting the entire industrial process (raw material intake → spinning → texturizing → dyeing → packaging → export).

## 🗂️ Pages

| Page | File | Purpose |
|---|---|---|
| Home | `home_.html` | Hero video, company snapshot, capability highlights, stats |
| Journey / About | `journey.html` | Company history and "About" narrative |
| Infrastructure | `infrastructure_.html` | Plant capacity, raw materials, manufacturing setup |
| Products | `products_.html` | POY / DTY / FDY / dope-dyed yarn product lines |
| Investor Relations | `investor.html` | Listing details, filings, shareholder information |
| Careers | `career.html` | Open roles / careers at RRIL |
| Contact | `contact.html` | Contact details, location, enquiry form |

Every page links out to the group's sister brand, **SVG Fashions**, via the top navigation.

## ✨ Features

- **Custom AI-animated hero video** — a 2:30 min explainer of RRIL's entire industrial process, built to match their process-flow diagram, with in-browser play/pause and mute/unmute controls
- Fully responsive layout (desktop → mobile), with an animated slide-in mobile nav
- Scroll-triggered reveal animations and animated stat counters (`IntersectionObserver`-based)
- Sticky navbar with scroll-aware styling and active-section highlighting
- Shared design system (colors, typography, spacing) applied consistently across all 6 pages
- Zero backend / zero build step — runs as static HTML, deployable anywhere

## 🛠️ Tech Stack

- **HTML5** — semantic, single-file-per-page structure
- **Tailwind CSS** (via CDN) — utility-first styling with an extended custom theme
- **Lucide Icons** — lightweight icon set
- **Google Fonts** — `Playfair Display` (headings) + `Inter` (body)
- **Vanilla JavaScript** — no frameworks; handles nav, scroll reveal, counters, and video controls
- **AI tooling** — used to generate the industrial-process explainer video from RRIL's provided process map

No build tools, bundlers, or package managers required — the site is dependency-free at runtime (all libraries load from CDN).

## 🎨 Design System

| Token | Value | Usage |
|---|---|---|
| Navy | `#1E2E6E` | Primary brand color, text, buttons |
| Sky Blue | `#7BB8D4` | Accent, highlights, hover states |
| Light Blue | `#D6EAF3` | Soft backgrounds, badges |
| Page BG | `#F4F7FB` | Base page background |
| Display Font | Playfair Display | Headings |
| Body Font | Inter | Body copy, UI text |

The navbar is kept white across all pages to preserve contrast against RRIL's logo, which does not have a transparent-on-dark variant.

## 📁 Project Structure

```
├── home_.html              # Homepage (hero video, overview, stats)
├── journey_.html           # About / company journey
├── infrastructure_.html    # Infrastructure & raw materials
├── products_.html          # Product lines (POY/DTY/FDY/Dope Dyed)
├── investor.html           # Investor relations
├── career.html             # Careers
├── contact.html            # Contact page
├── /videos                 # Logo assets + hero background video
├── /assets                 # Poster images, icons, misc. static assets
└── README.md
```

> Note: media assets (video, logos, high-res images) are referenced locally / via the legacy `rajrayon.com` CDN and are not all included in this repo — see **Assets** below.

## 🚀 Running Locally

No install required — this is static HTML.

```bash
# Clone the repo
git clone https://github.com/DHWANIVASA/<repo-name>.git
cd <repo-name>

# Option 1: just open it
open home_.html

# Option 2: serve it properly (recommended, avoids relative-path/video issues)
npx serve .
# or
python -m http.server 8000
```

Then visit `http://localhost:8000/home_.html`.

## 🎬 Assets

- **Hero video**: place the industrial-process animation at `videos/animated-industrial-video.mp4` and update the `<source>` path in `home_.html` (currently points to a local Windows dev path — needs to be corrected to a relative path before deployment).
- **Logos**: `videos/raj_rayon_logo_transparent.png`, `videos/SVG LOGO BMP.bmp`
- Several images (`infra.JPG`, `raw-2.jpg`) currently reference the legacy `rajrayon.com` CDN and should be migrated to local assets for reliability.

## ✅ Known TODOs

- [ ] Fix hero video source path (currently an absolute local Windows path — will not resolve on any other machine)
- [ ] Move remaining externally-hosted images to local `/assets`
- [ ] Replace placeholder social links in the footer
- [ ] Add favicon
- [ ] Compress hero video for faster load (2:30 min asset)

## 🙏 Acknowledgments

Built by studying RRIL's previous website, their 46-page corporate presentation, the SVG Fashions website, and RRIL's provided industrial process map, then rebuilt from the ground up as a modern, animated, brand-consistent web presence.

## 📄 License

© 2024–2026 Raj Rayon Industries Limited. All rights reserved. This repository contains client work; do not reuse brand assets, copy, or imagery without permission.
