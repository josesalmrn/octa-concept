---
name: octa-concept-design
description: Use this skill to generate well-branded interfaces and assets for OCTA CONCEPT and MUSIKLUB — El Salvador's premier electronic music event production company and nightclub brand. Contains essential design guidelines, colors, type, fonts, assets, and UI kit components for prototyping or production.
user-invocable: true
---

Read the README.md file within this skill, and explore the other available files.

If creating visual artifacts (slides, mocks, throwaway prototypes, etc), copy assets out and create static HTML files for the user to view. If working on production code, you can copy assets and read the rules here to become an expert in designing with this brand.

If the user invokes this skill without any other guidance, ask them what they want to build or design, ask some questions, and act as an expert designer who outputs HTML artifacts _or_ production code, depending on the need.

## Quick Reference

**Brand**: OCTA CONCEPT — Electronic music events & nightlife, San Salvador, El Salvador
**Sub-brand**: MUSIKLUB — Electronic music nightclub (@klub_sv)

**Colors**:
- Background: `#0A0A0A`
- Surface: `#1A1A1A` / `#2A2A2A`
- Text: `#FFFFFF` / `#888888` (muted)
- Accent: `#00FF88` (electric green) / `#00CC6E` (dim)

**Fonts** (Google Fonts):
- Display: `Bebas Neue` — all headings, all-caps, wide tracking
- Body/UI: `DM Mono` — monospace, techy feel
- Data/times: `Space Mono`

**Key rules**:
- Zero border-radius everywhere — sharp corners only
- Thin 1px borders (`#2A2A2A`), turn `#00FF88` on hover
- Hover: cards lift `translateY(-5px)`, list items slide `translateX(5px)`
- CTA buttons: transparent + `#00FF88` border → fill green on hover
- Noise texture overlay on body (SVG feTurbulence at 3% opacity)
- Language: Spanish (El Salvador) — terse, uppercase-heavy, action-oriented

**Assets**: `assets/` folder — hero-background.png, musiklub-logo.png, favicons, club photos, partner logos
**UI Kits**: `ui_kits/octa_concept/` and `ui_kits/musiklub/`
**CSS Tokens**: `colors_and_type.css`
