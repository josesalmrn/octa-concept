# OCTA CONCEPT Design System

## Overview

**OCTA CONCEPT** is a San Salvador–based electronic music event production company and nightlife brand. They operate two distinct web products:

1. **OCTA CONCEPT** (`octaconcept.com`) — Main marketing/event landing page listing upcoming events, partners, gallery, and team.
2. **MUSIKLUB** (`octaconcept.com/musiklub`) — Their flagship electronic music club (San Salvador, 3er nivel, Calle La Ceiba 4730). Thu–Sat venue with Pioneer CDJ-3000 system, recurring "Open Deck" nights for emerging DJs, and table reservations.

### Sources
- **GitHub repo**: `https://github.com/josesalmrn/octa-concept`
  - `index.html` — OCTA CONCEPT main landing page (single-file, all CSS + JS inline)
  - `musiklub/index.html` — MUSIKLUB club site (single-file, all CSS + JS inline)
  - `partners/` — 12 partner brand logos (PNG, 500×500)
  - `musiklub/musiklub-photo-1..8.jpg` — Club photography

---

## Content Fundamentals

### Language
- **Primary language: Spanish (El Salvador)**. All UI copy is in Spanish. English appears only in music genre names (techno, house, minimal) and the hero tagline "Electronic Music Experiences."

### Tone
- Terse, confident, uppercase-heavy. The brand speaks like a promoter, not a brand marketer.
- Short punchy statements. No fluff or explanatory prose.
- Exclusivity signals: "Experiencia única y exclusiva", "de clase mundial", "$35"

### Casing
- **All-caps for headings** via `font-family: 'Bebas Neue'` — which is inherently uppercase display.
- `text-transform: uppercase` used consistently on labels, nav links, event dates, tags.
- Sentence case for body descriptions (event descriptions, about text).

### Copy style
- **1st/2nd person**: Uses "tú" / "tu" language ("Asegura tu lugar", "Trae tu música, comparte tu sonido").
- Action-oriented CTAs: "COMPRAR BOLETO", "ENVIAR RESERVA POR WHATSAPP", "VER EN GOOGLE MAPS"
- Date/time written in formal Spanish: "Sábado 2 de Mayo", "8:00 PM – 3:00 AM"
- Social handles referenced directly as copy: `@klub_sv`, `@octaconcept`

### Emoji
- **No emoji used anywhere in the UI.** (Meta tags use emoji for SEO purposes only — not visible UI.)

### Examples of brand voice
> "Espacio diseñado para que los DJs emergentes tengan su lugar. Trae tu música, comparte tu sonido, construye tu audiencia."
> "Prepárate para vivir al máximo la música electrónica."
> "El mejor club de música electrónica en San Salvador."

---

## Visual Foundations

### Color
- **Background**: `#0A0A0A` — near-black, not pure black; creates warmth vs stark #000
- **Surface**: `#1A1A1A` (elevated cards/panels), `#2A2A2A` (borders, dividers)
- **Foreground**: `#FFFFFF` (primary text)
- **Muted text**: `#888888`
- **Accent**: `#00FF88` — electric neon green. Single dominant accent used everywhere: borders, dates, labels, CTAs, hover glows
- **Accent dim**: `#00CC6E` — for hover/pressed states

### Typography
- **Bebas Neue** — Display / all headings. All-caps condensed, wide letter-spacing (0.05–0.20em). Sizes from 1.5rem (card titles) up to `clamp(3rem, 10vw, 8rem)` for hero.
- **DM Mono** — Body / UI text. Monospace gives techy, underground feel. Used for nav, descriptions, buttons, labels.
- **Space Mono** — Data-specific: times, schedules, clocks. Heavier monospace weight.
- No serif fonts used anywhere.

### Spacing & Layout
- Large section padding: `8rem 4rem` desktop, `4rem 2rem` mobile
- CSS Grid used for event cards (`auto-fill, minmax(350px, 1fr)`) and info layouts
- Max content width: `1200px` centered
- Cards are borderless but have `1px solid var(--surface-light)` border

### Backgrounds & Textures
- **Noise texture overlay** on entire body via inline SVG `feTurbulence` at 3% opacity — subtle film grain feel
- **Hero**: full-bleed photo with dark overlay (`rgba(0,0,0,0.5)`)
- **Animated grid**: 50px grid of accent-colored lines animating diagonally in hero, 10% opacity
- **Cursor glow**: 600px radial gradient that follows cursor (`rgba(0,255,136,0.15)`)
- **Scanline texture** on MUSIKLUB hero: repeating horizontal lines at 3% opacity

### Corners & Borders
- **Zero border-radius throughout** — sharp, architectural feel
- Default border: `1px solid #2A2A2A`
- Active/hover border: `1px–2px solid #00FF88`
- Left-border accent on schedule items (`border-left: 2px–3px solid var(--accent)`)

### Cards
- Background: `#1A1A1A`
- Border: `1px solid #2A2A2A` → `1px solid #00FF88` on hover
- `transform: translateY(-5px)` on hover (event cards)
- `transform: translateX(5px)` on hover (list items / club event cards)
- Left-border scaleY animation on club event cards
- No shadows — depth via border color change only

### Buttons & CTAs
- **Primary CTA**: transparent bg + `2px solid #00FF88` + green text → fills with green on hover (slide-in `::before` pseudo)
- **Secondary**: `1px solid #2A2A2A` → border turns accent on hover + `rgba(0,255,136,0.05)` bg
- **Filled**: `background: #00FF88; color: #0A0A0A` — used for form submit
- All buttons: uppercase, letter-spacing 0.15–0.20em, 0 border-radius

### Animation & Motion
- **Entry**: `fadeInUp` (opacity 0→1, translateY 40px→0) — used on hero content, cards
- **Nav**: `slideDown` from top on load
- **Shimmer**: rotating gradient on event image placeholders
- **gridMove**: animated background grid in hero (20s linear infinite)
- **scrollPulse**: scroll indicator line fades up/down
- **Partner slider**: `slidePartners` — continuous horizontal scroll (40s linear infinite), pauses on hover
- **Countdown**: JS-driven real-time countdown
- Easing: `ease` everywhere — no spring/bounce animations
- No page transitions

### Hover States
- Text links: `color → #00FF88` + underline grows via `::after` width
- Cards: border → accent + slight translate
- Social buttons: platform-specific color (WhatsApp green, Instagram pink, Facebook blue)
- Partner logos: `grayscale(100%) brightness(0) invert(1)` at 60% opacity → full color on hover + scale(1.1)

### Imagery
- **Photography**: club/event photography — low-light, moody, warm-toned club imagery
- Color grade: warm highlights, dark shadows — typical nightlife photography
- **Dreamwoods**: festival/outdoor event imagery (dreamwoods.png — another OCTA event brand)
- No illustrations, no hand-drawn elements, no patterns beyond the noise/grid
- Partner logos displayed in grayscale, colored only on hover

### Iconography
See ICONOGRAPHY section below.

---

## ICONOGRAPHY

### Approach
- **Inline SVG icons only** — no icon font, no CDN icon library
- All icons are simple filled Material Design–style path icons drawn inline in HTML
- Icon size: 16–24px typical, 20px most common
- Icon color: inherits from parent or explicitly set to `var(--accent)` for filled icons, `currentColor` for interactive ones
- No emoji used as icons

### Icons in use
- **Location pin** (map marker) — venue address, Google Maps links
- **WhatsApp logo** (filled path) — contact / reservation CTA
- **Instagram logo** (filled path) — social links
- **Facebook logo** (filled path) — social links
- **Arrow left** — back navigation, slider prev
- **Arrow right** — slider next, hover CTA indicator
- **Send/paper plane** — form submit (implicit in WhatsApp CTA)

### Logos
- `assets/favicon.png` — OCTA CONCEPT favicon / logo mark (512px)
- `assets/favicon-32x32.png` — 32px favicon
- `assets/musiklub-logo.png` — MUSIKLUB wordmark/logo (white on transparent, used as hero centrepiece)
- MUSIKLUB logo has green glow filter applied: `drop-shadow(0 0 30px rgba(0,255,136,0.6))`

### Partner logos
Located in `assets/partners/`:
- `3am.png`, `electrolit.png`, `jagger.png`, `fun.png` (+ 8 more in repo)
- Displayed as white/inverted at 60% opacity; full color on hover
- Always inside `.partner-logo` wrapper at 180×120px (desktop), 120×80px (mobile)

---

## File Index

```
README.md                    — This file (brand context, visual foundations, iconography)
colors_and_type.css          — CSS custom properties: colors, type, spacing, borders, shadows
SKILL.md                     — Agent skill definition for Claude Code compatibility

assets/
  hero-background.png        — OCTA CONCEPT hero photo (full-bleed dark party scene)
  dreamwoods.png             — Dreamwoods festival brand imagery
  musiklub-logo.png          — MUSIKLUB logo (white, transparent bg)
  favicon.png                — OCTA CONCEPT logo/favicon (512px)
  favicon-32x32.png          — OCTA CONCEPT favicon (32px)
  musiklub-photo-1..3.jpg    — Club interior/event photography
  partners/                  — Partner brand logos (PNG 500×500)
    3am.png, electrolit.png, jagger.png, fun.png (+ 8 in repo)

preview/
  colors-brand.html          — Brand color palette swatches
  colors-semantic.html       — Semantic / UI color tokens
  type-display.html          — Display type specimens (Bebas Neue)
  type-body.html             — Body & data type specimens (DM Mono, Space Mono)
  type-scale.html            — Full type scale reference
  spacing.html               — Spacing, border & shadow tokens
  component-buttons.html     — Button variants & states
  component-cards.html       — Event cards & info cards
  component-nav.html         — Navigation bar
  component-forms.html       — Form inputs & reservation form
  brand-logos.html           — Logo & favicon display
  brand-partners.html        — Partner logo strip
  brand-imagery.html         — Hero & event photography

ui_kits/
  octa_concept/
    README.md                — UI kit context & usage notes
    index.html               — Interactive OCTA CONCEPT landing prototype
    Components.jsx           — Shared components (Nav, Hero, EventCard, Footer)
    EventsSection.jsx        — Events grid section
    MusikLubSection.jsx      — MUSIKLUB club info section
  musiklub/
    README.md                — MUSIKLUB UI kit notes
    index.html               — Interactive MUSIKLUB club site prototype
    Components.jsx           — Shared components (Nav, Hero, Schedule, Gallery)
    EventsGrid.jsx           — Club events grid
    ReservationForm.jsx      — Table reservation form
```
