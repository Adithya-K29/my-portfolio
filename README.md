# Adithya K — People Systems Portfolio

**Live →** [adithya-k29.github.io/my-portfolio](https://adithya-k29.github.io/my-portfolio)

---

A single-page portfolio built around one idea: people decisions in organizations are systems problems. Every section reflects that — not just in content, but in structure and intent.

Built as a single self-contained HTML file. No framework, no bundler, no dependencies beyond two CDN scripts. 3,024 lines. 464 KB.

---

## Sections

| Section | Nav Label | Purpose |
|---|---|---|
| Pre-hero (Morse stage) | — | Full-screen Morse animation intro. The word decoded: STAY. |
| `hero` | Hero | Two lines. Entry point. |
| `signal` | Origin | Why this work. How the thinking formed. |
| `missions` | Experience | Five roles as system phases. Each clickable with outcomes. |
| `telemetry` | Impact | Three verified metrics. Click each for methodology. |
| `now` | Active | What is being built right now, across two tracks. |
| `mann` | Builds | Six systems designed from zero. Click each for problem → solution → outcome. |
| `docking` | Credentials | Five certifications, three recognitions. Orbital ring layout. |
| `tesseract` | Validation | Six testimonials across depth and recency. Tesseract wireframe background. |
| `transmit` | Signals | LinkedIn posts as signal. Two-column layout with embedded video. |
| `gargantua` | Open Channel | Contact. TARS animation. Not for roles. |
| Cooper Station | Hidden | Easter egg. Requires two correct answers to reach. |

---

## Tech Stack

### Core
- **HTML5 / CSS3 / Vanilla JavaScript** — no framework, no build step
- **Single-file architecture** — everything in `index.html`, deployed directly via GitHub Pages

### Animation Layers

| Layer | Used for |
|---|---|
| **Three.js r128** (CDN) | Hero overlay — WebGL `ShaderMaterial` with custom GLSL fragment shader |
| **Canvas 2D** | Hero blob animation, mission path draw, Tesseract wireframe, Gargantua orbital particles, Cooper Station grid + particle drift |
| **CSS `@keyframes`** | 27 named animations — section reveals, status pulses, TARS drop, Morse blink, care→see morph, wave drift, card entry, modal open |
| **SVG `stroke-dashoffset`** | Mission log connecting path, animated on scroll entry |
| **`IntersectionObserver`** | All scroll-triggered reveals and one-time animations |

### GLSL (fragment shader on `hcv2`)

Fractal Brownian motion noise (`fbm`, 4 octaves) layered over a ray-marched comet tail with skew matrix deformation. `tanh` tone mapping. Runs as a WebGL overlay (`THREE.ShaderMaterial`) on top of the hero canvas at `z-index: 1`.

### Typography

| Font | Weight | Source | Used for |
|---|---|---|---|
| **Technor** | Semibold (600) | [Fontshare](https://www.fontshare.com/fonts/technor) | All headings |
| **Supreme** | Regular / Medium (400, 500) | [Fontshare](https://www.fontshare.com/fonts/supreme) | Body text |
| **IBM Plex Mono** | 300–500 | Google Fonts | Labels, codes, metadata |
| Bodoni Moda | Variable | Google Fonts | Pre-hero accent |
| Cormorant Garamond | 300–400 | Google Fonts | Pre-hero serif |

### Color System

```css
--void:   #020408   /* primary background     */
--copper: #C4813A   /* primary accent          */
--chi:    #E09B4A   /* warm highlight          */
--star:   #F0EDE8   /* primary text            */
--mid:    #8C8882   /* secondary text          */
--ice:    #88B4E7   /* cool accent             */
```

### Embedded Assets

| Asset | Format | Size | Used in |
|---|---|---|---|
| Hero background | JPEG | 49 KB | `#hero` |
| Mann / Builds background | JPEG | 28 KB | `#mann` |
| Signal section backgrounds (×2) | WebP | 26 KB each | `#signal` |
| Gargantua background | JPEG | 85 KB | `#gargantua` |
| Navbar logo | PNG | 16 KB | Sidebar |
| Signals section video | MP4 (no audio, CRF 28) | 38 KB | `#transmit` |

Total embedded asset weight: ~268 KB. Total file size: 464 KB.

---

## Interactive Features

- **Mission modals** — Problem / System Built / What Changed for all five roles
- **Telemetry modals** — What Changed / How / System Insight for each of three metrics
- **System Build modals** — Problem / System Designed / What Changed for all six builds
- **Tab switching** — People Systems ↔ Decision Systems with staggered card entry animation
- **Docking orbital ring** — 8 rotating nodes (5 certs + 3 awards), click to focus and expand
- **Easter egg** — Two-stage quiz with 380ms processing delay, shake + color glitch on wrong input, 3 failures routes to hero
- **TARS animation** — CSS-only linear drop from top, bump landing, words fade in sequentially; clicking routes to easter egg
- **Cooper Station** — Canvas background with green grid, particle drift, camera drift, warm gold vignette, fade-in text layer

---

## File Structure (single file breakdown)

```
index.html  (3,024 lines / 464 KB)
├── <head>              Fonts, meta, viewport, CDN links
├── <style>             ~140 KB — all layout, animation, component styles
├── <main>
│   ├── <aside>         Sidebar nav (10 items, scroll-tracked)
│   ├── #morse-stage    Pre-hero Morse intro (fixed overlay, scroll to dismiss)
│   ├── #hero           Canvas blob + Three.js WebGL overlay
│   ├── #signal         Origin section + drone SVG animation
│   ├── #missions       Experience cards + SVG path + click modals
│   ├── #telemetry      Metric cards + pillar section + click modals
│   ├── #now            Active Build — two-tab card system
│   ├── #mann           System Builds 2×3 grid + click modals
│   ├── #docking        Credentials orbital ring (Canvas 2D)
│   ├── #tesseract      Testimonials + Tesseract wireframe (Canvas 2D)
│   ├── #transmit       LinkedIn posts + embedded video
│   └── #gargantua      Contact + TARS + orbital particles (Canvas 2D)
├── #cap                Capsule click trigger (easter egg entry point)
├── #egg                Easter egg overlay (two-stage quiz)
├── #cs                 Cooper Station (hidden, Canvas 2D)
└── <script>            ~42 KB — all animation logic and interaction
```

---

## Running Locally

No build step required.

```bash
git clone https://github.com/Adithya-K29/my-portfolio.git
cd my-portfolio
open index.html
```

Fonts (Fontshare, Google Fonts) and Three.js load from CDN. An internet connection is required for both.

---

## Thematic reference

Section IDs (`gargantua`, `tesseract`, `mann`), the Morse decode (`STAY`), and the Cooper Station easter egg are all references to *Interstellar* (2014). The theme is intentional: signal and noise, time under pressure, and the idea that the most important things are communicated outside of conventional channels.

Cooper Station is the last section. You have to earn it.

---

[LinkedIn](https://www.linkedin.com/in/adithya-k-talent-acquisition/) · [Peerlist](https://peerlist.io/adi_procedure)
