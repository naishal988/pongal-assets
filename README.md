# Pongal — Interactive Cultural Web Experience

[![Live Deployment](https://img.shields.io/badge/Live%20Experience-Cloudflare%20Edge-f38020?style=for-the-badge&logo=cloudflare&logoColor=white)](https://pongal.naishalpnadiya988.workers.dev/)
[![Author](https://img.shields.io/badge/Architect-Naishal%20Nadiya-09090b?style=for-the-badge&logo=github&logoColor=white)](https://naishal988.naishalpnadiya988.workers.dev/)
[![Status](https://img.shields.io/badge/Architecture-Production%20Grade-22c55e?style=for-the-badge)](https://pongal.naishalpnadiya988.workers.dev/)

> **Live Production URL:** [https://pongal.naishalpnadiya988.workers.dev/](https://pongal.naishalpnadiya988.workers.dev/)

An editorial, physics-driven web experience celebrating the ancient Tamil harvest festival of **Pongal**. Built with modern web standards, tactile micro-interactions, bento-box glassmorphism, and a decoupled edge-ready media architecture.

---

## 🌾 About the Pongal Festival

Pongal is a historic four-day thanksgiving festival celebrated by Tamil communities worldwide to express gratitude to the Sun God (*Surya*), Mother Nature, and farm animals for agricultural abundance. Derived from the Tamil verb *pongu* ("to boil over"), it marks the beginning of the auspicious month of *Thai*.

### The Four-Day Chronological Journey

1. **[Day 1: Bhogi Pongal](https://pongal.naishalpnadiya988.workers.dev/bhogi_pongal.html)**  
   The festival of renewal and spiritual cleansing. Families burn discarded belongings in traditional bonfires to discard old habits and welcome fresh beginnings.
2. **[Day 2: Surya Pongal](https://pongal.naishalpnadiya988.workers.dev/surya_pongal.html)**  
   The central day honoring the Sun God. Fresh harvest rice, milk, and jaggery are boiled outdoors in decorated clay pots until they boil over, accompanied by the joyful chant *"Pongalo Pongal!"*.
3. **[Day 3: Maatu Pongal](https://pongal.naishalpnadiya988.workers.dev/maatu_pongal.html)**  
   A day consecrated to honoring cattle as vital partners in agriculture. Cows and bulls are bathed, painted, adorned with flower garlands, and worshipped.
4. **[Day 4: Kaanum Pongal](https://pongal.naishalpnadiya988.workers.dev/kaanum_pongal.html)**  
   The day of kinship, community bonding, outdoor reunions, and vibrant traditional performing arts.

### Thematic Cultural Explorations

- **[Pongal in the City](https://pongal.naishalpnadiya988.workers.dev/city.html):** How ancient agricultural traditions thrive in high-density urban environments through apartment community gatherings, corridor Kolam competitions, and temple festivities.
- **[Traditional Folk Dances](https://pongal.naishalpnadiya988.workers.dev/dances.html):** The energetic folklore of Tamil Nadu, spotlighting rhythmic arts such as *Kummi*, *Karagattam*, and *Mayilattam*.
- **[What's in the Pot?](https://pongal.naishalpnadiya988.workers.dev/pot.html):** The culinary alchemy and symbolic anatomy of *Sakkarai Pongal* (newly harvested rice, organic jaggery, pure ghee, roasted cashews, and raisins).
- **[Bring Home the Fun!](https://pongal.naishalpnadiya988.workers.dev/fun.html):** Family-friendly crafts and activities, from terracotta pot painting and paper sugarcane crafting to drawing symmetrical *Pulli Kolams*.

---

## ⚡ Architecture & Interactive Engines

Engineered without heavyweight external runtime dependencies (zero GSAP, zero Framer Motion), this platform leverages native browser APIs and hardware-accelerated CSS for 60fps performance across mobile and desktop.

### 1. Custom Physics Cursor Engine
- Dual-layer cursor architecture comprising a zero-latency center point (`#cursor-dot`) and an outer dynamic ring (`#cursor-ring`) operating in `mix-blend-mode: difference`.
- Outer ring tracks pointer trajectories via `requestAnimationFrame` spring interpolation (`ringX += (mouseX - ringX) * 0.15`).
- Automatically disabled on touch-enabled hardware via `@media (pointer: coarse)` to prevent mobile rendering penalties.

### 2. Fluid Interactive Mesh Gradient
- Hardware-accelerated radial blurs (`filter: blur(100px)`) that translate dynamically along X and Y axes in response to cursor position, creating an organic, atmospheric backdrop.

### 3. Magnetic UI Elements Engine
- Elements tagged with `.magnetic` calculate real-time cursor offsets relative to the element's center point on `mousemove` and spring back smoothly via `cubic-bezier(0.34, 1.56, 0.64, 1)` on `mouseleave`.

### 4. 3D Squircle Tilt & Dynamic Edge-Glow Cards
- Interactive feature cards calculate local cursor coordinates to update CSS custom properties (`--mouse-x`, `--mouse-y`), casting a spotlight radial border gradient while rotating up to 10 degrees in 3D perspective (`rotateX`, `rotateY`, `scale3d(1.02, 1.02, 1.02)`).

### 5. Interactive Knowledge Quiz Engine
- A lightweight Vanilla JavaScript state machine powering a 3-question knowledge test with real-time feedback, reactive progress bar transitions, glassmorphic option selectors, score aggregation, and state resets.

### 6. BFCache-Resilient Page Transitions
- Smooth horizontal page exit animations (`translateX(-100vw)`) paired with `pageshow` lifecycle listeners (`event.persisted`) to ensure browser Back/Forward Cache restorations never freeze or show blank canvases.

### 7. Centralized CDN & Video Architecture (`assets.js`)
- Unified asset management via `assets.js`, preparing the codebase for external media offloading (e.g. `pongal-assets` on jsDelivr / Cloudflare):
  - Single `CDN_BASE_URL` constant for zero-hunt asset rebasing.
  - Dual-stacked video streaming specification (`.webm` + `.mp4`) with zero-CLS poster frames.
  - Declarative DOM hydration via `data-asset` and `data-video` attributes.

---

## 🌐 Technical SEO & Search Entity Graph

The platform incorporates advanced technical SEO and semantic entity modeling:
- **Unified Schema.org `@graph`:** Direct JSON-LD Knowledge Graph connection between the `WebSite`, `CreativeWork`, and author's `Person` entity (`@id: "https://naishal988.naishalpnadiya988.workers.dev/#person"`).
- **Social Media Cards:** Complete OpenGraph (`og:*`) and Twitter Card (`summary_large_image`) metadata with high-fidelity canonical URL resolution.
- **AI Crawler & Bot Fallback:** Accessible semantic `<noscript>` block (without `display: none;`) delivering complete thematic hierarchy, narrative context, and author credits to search engine bots and LLM scrapers.

---

## 👨‍💻 System Architect & Creative Developer

**Naishal Nadiya (`naishal988`)**  
*System Architect & Creative Developer*

- **Portfolio:** [https://naishal988.naishalpnadiya988.workers.dev/](https://naishal988.naishalpnadiya988.workers.dev/)
- **GitHub:** [@naishal988](https://github.com/naishal988)
- **LinkedIn:** [Naishal Nadiya](https://linkedin.com/in/naishal-nadiya/)
- **Dev.to:** [@naishal988](https://dev.to/naishal988)

---

## 🚀 Deployment

This application is deployed and served globally on the **Cloudflare Global Edge Network**, utilizing Cloudflare Workers / Pages for low-latency asset delivery and fast time-to-first-byte (TTFB).

**Live Site:** [https://pongal.naishalpnadiya988.workers.dev/](https://pongal.naishalpnadiya988.workers.dev/)
