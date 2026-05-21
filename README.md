# NoTrace+
Two in-browser privacy tools plus a DuckDuckGo search shortcut: strip photo metadata and remove tracking parameters from URLs.

Live: `https://notrace.plus` (Vercel)

![NoTrace+ preview](og.png)

Made by [gitpushnico](https://github.com/gitpushnico).

## Motivation
I built NoTrace+ because a lot of people (including me) don’t think about the small privacy steps that add up, like hidden photo metadata and tracking parameters in shared links.
I wanted a single, simple place to handle those in seconds, and to make privacy feel approachable rather than technical.

## What it does
NoTrace+ is a small, static, browser-first site:

- **Photo Metadata** (tool): removes EXIF / metadata from images and exports a clean copy — processed entirely in your browser.
- **URL Tracking** (tool): removes common tracking parameters from URLs (UTM, click IDs, etc.) while preserving meaningful parameters — processed entirely in your browser.
- **Search** (shortcut): opens DuckDuckGo in a new tab with privacy-focused URL settings (less profiling, not invisibility). NoTrace+ does not log your query.

## Privacy model (what’s true, precisely)
NoTrace+ is designed so you can **verify** what it does by reading the source.

- **NoTrace+ has no backend**: it’s a static site (HTML/CSS/JS).
- **We don’t receive your files or URLs**: photo processing and URL cleaning happen in your browser.
- **No analytics / no trackers**: no cookies, pixels, or third‑party analytics scripts are included.

### About search
Search is a shortcut, not a third processing tool:

- Your query **is sent to DuckDuckGo** when you click Search (that’s unavoidable for any web search).
- DuckDuckGo will also see your **IP address**, as with any direct request to an external service.
- NoTrace+ does not store or log what you type.

## Limitations (what each part does not do)
NoTrace+ is scoped to specific browser-side tasks. Each part reduces one signal, not all tracking or identification:

- **Photo Metadata**: Removing EXIF does not remove identifying content in the image itself (faces, landmarks, vehicle plates, background details).
- **URL Tracking**: Stripping URL parameters does not block first-party cookies, browser fingerprinting, server-side logging, or IP-based identification.
- **Search**: DuckDuckGo receives your query and IP address when you search, as with any direct request to an external service. NoTrace+ cannot change that.

## How it works (high level)
- **Photo Metadata**: reads the image locally, redraws/exports without metadata, and downloads the cleaned file.
- **URL Tracking**: parses the URL and removes known tracking keys; non-tracking parameters remain.
- **Search**: builds a DuckDuckGo URL and opens it in a new tab when you click Search.

## Project structure
This repo is intentionally lightweight:

- `notrace_plus.html` — the main app (single-file HTML + CSS + JS)
- `vercel.json` — Vercel routing + security headers
- `404.html` — custom 404 page
- `og.png` — link preview image (Open Graph / Twitter)
- `logo.png` — site logo
- `icons/` — UI icons used inside the app
- `favicon/` — favicon + Apple touch icon
- `robots.txt` / `sitemap.xml` — basic SEO crawl hints

## Run locally
Just open the file in a browser:

1. Double‑click `notrace_plus.html`, or
2. Serve it locally (recommended so fonts load consistently):

```bash
python3 -m http.server 5173
```

Then open `http://localhost:5173/notrace_plus.html`.

## Deploy on Vercel (with `notrace.plus`)
One common setup:

1. Push this repo to GitHub.
2. Import the project in Vercel (Framework preset: **Other**).
3. Set the **Build Command** to empty and **Output Directory** to empty (static).
4. Add your custom domain `notrace.plus` in Vercel → Domains.
5. Update DNS at your registrar as Vercel instructs.

## Open source & license
This project is **open source** so anyone can inspect the code, verify the privacy claims, and fork/host their own version.

- **License**: MIT
- **Font licenses**: SIL Open Font License 1.1 (see `fonts/OFL-DMMono.txt` and `fonts/OFL-Unbounded.txt`)

## Compliance docs
- `PRIVACY.md` — project privacy notice
- `THIRD_PARTY_NOTICE.md` — third-party assets, runtime behavior, and trademark notes (including GitHub Invertocat use)

## Trademarks
GitHub and the Invertocat logo are trademarks of GitHub, Inc. This project is not affiliated with GitHub. Details: `THIRD_PARTY_NOTICE.md` and [GitHub Brand Toolkit – Logo](https://brand.github.com/foundations/logo).
