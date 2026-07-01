# system-design-guide

A comprehensive, beginner-friendly **System Design** study guide covering foundations, classic interview problems, IoT/mobile-specific designs, low-level design (LLD), interview execution playbooks, and 18 real-world case studies — published as a single self-contained website.

> Author: **Lakshmi Priya Anbu**
> © 2026. All rights reserved.

---

## 🔗 Live site

**[https://lakshmipriyaanbu.github.io/system-design-guide/](https://lakshmipriyaanbu.github.io/system-design-guide/)**

The site is served by GitHub Pages directly from this repository's `main` branch. It is publicly accessible — no login required.

---

## What's in the guide

The site is a single HTML page (`index.html`) organized into six parts plus an appendix:

| Part | Contents |
|---|---|
| **1. Foundations** (17 topics) | HTTP, DNS, load balancers, API gateways, SQL vs NoSQL, indexes, ACID/BASE, caching, message queues, CDNs, object storage, rate limiting, auth, scaling, CAP theorem, observability |
| **2. Classic Problems** (10) | URL shortener, chat app, notifications, ride booking, Instagram feed, Dropbox, video streaming, payments, autocomplete, distributed rate limiter |
| **3. IoT / Mobile** (8) | Mobile backend, sync, offline-first, push (deep dive), BLE device setup, telemetry, time-series storage, OTA firmware |
| **4. Low-Level Design** (5) | OOP, SOLID, design patterns, thread safety, LLD problem catalog |
| **5. Interview Execution** (4) | 45-minute system-design playbook, LLD playbook, behavioral (STAR), common rejection reasons |
| **6. Case Studies** (18) | WhatsApp, Twitter, YouTube, Uber (ETA + nearby drivers), Airbnb, Reddit, Google Search, Amazon S3, Kafka, LLM serving, stock exchange, Google Docs, Tinder, Nginx, leaderboards, AirTags, Vitess/MySQL |
| **Appendix** | Latency numbers, glossary |

Design and reading experience:

- Bullet-point layout for concept sections; short-article prose for case studies.
- Every jargon term is defined inline the first time it appears.
- A prominent Contents block sits at the top of the page with jump-links to every section; a sticky left sidebar duplicates this on desktop.
- Serif display type, warm-neutral paper background, blue accent.
- Subtle diagonal `© Lakshmi Priya Anbu 2026` watermark repeated across the page.

---

## Repository layout

```
system-design-guide/
├── index.html   ← the entire site (self-contained, no external assets)
└── README.md    ← this file
```

That's the whole thing. `index.html` inlines all CSS and content — no JavaScript, no external fonts, no image files. It renders identically on every modern browser (macOS, Windows, Linux, iOS, Android).

---

## How to modify the site

### Small edits (fix a typo, tweak one section)

1. Open [`index.html`](./index.html) in your editor.
2. Find the section (each `<h2>` marks a numbered topic).
3. Make the edit.
4. Commit and push:

   ```bash
   cd ~/Desktop/system-design-guide
   git add index.html
   git commit -m "Fix typo in Caching section"
   git push
   ```
5. GitHub Pages redeploys automatically within about a minute.

### Adding a new topic or case study

1. Copy an existing `<h2 id="...">` block that has the shape you want (concept-style or article-style) and paste it in the right place in the file.
2. Give the new section a unique ID (e.g. `id="c19"` for a new case study).
3. Add matching entries to:
   - The **Contents block** at the top of the page (inside `<div class="contents-block">`).
   - The **sticky sidebar** (`<nav class="toc">`).

### Changing styling

All CSS lives in the `<style>` block at the top of `index.html`. Palette variables are defined in `:root`:

```css
--paper:  #FBFAF7;   /* page background */
--ink:    #1A1D24;   /* main text */
--accent: #1F5F8B;   /* links, primary accent */
--warm:   #B25628;   /* section headers, callouts */
```

Change these to reskin the entire site.

### Changing the watermark

Locate the `body::before` block near the top of the `<style>` element. The SVG text inside the `background-image` URL is what shows on the page. Edit that string to change the text; adjust `fill-opacity` (currently `0.06`) for how faint or bold it appears.

---

## Local development

No build step. No dependencies. Just open the file:

```bash
open ~/Desktop/system-design-guide/index.html   # macOS
xdg-open index.html                             # Linux
start index.html                                # Windows
```

Or, to serve it locally over HTTP (useful for testing anchor links):

```bash
cd ~/Desktop/system-design-guide
python3 -m http.server 8000
# then open http://localhost:8000/
```

---

## Publishing

The site is deployed by **GitHub Pages** from the `main` branch, root path.

- **Source branch:** `main`
- **Source folder:** `/` (root)
- **Deploy trigger:** any push to `main` triggers a rebuild.
- **URL:** https://lakshmipriyaanbu.github.io/system-design-guide/

Deployment status: [Actions › pages-build-deployment](https://github.com/LakshmiPriyaAnbu/system-design-guide/actions).

To change these settings: repo **Settings → Pages**.

---

## Companion guide

An operating-systems study guide by the same author is available at [**os-guide**](https://github.com/LakshmiPriyaAnbu/os-guide) → [live site](https://lakshmipriyaanbu.github.io/os-guide/).

---

## Contributing

This is a personal study guide. Corrections and improvements are welcome — open an issue or a pull request.

---

## License

Content © 2026 **Lakshmi Priya Anbu**. All rights reserved.

The site is free to read; please do not republish substantial portions without permission.
