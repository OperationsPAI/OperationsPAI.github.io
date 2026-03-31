# OperationsPAI Website Theme Redesign — "The Monograph"

**Date:** 2026-03-31
**Status:** Approved
**Approach:** Custom Jekyll CSS + SVG illustrations, zero framework dependencies

## Overview

Redesign the OperationsPAI GitHub Pages site with an academic, research-oriented aesthetic using warm neutrals, serif headings, and hand-drawn-style SVG illustrations. The design should feel scholarly yet approachable — like a well-typeset research monograph with a human touch.

### Design Principles

1. **Scholarly authority** — Serif typography, generous white space, paper-like warmth
2. **Community warmth** — Warm color palette, hand-drawn illustrations, contributor highlights
3. **Minimalism with personality** — Clean base, light SVG illustrations to break up text
4. **Zero dependencies** — No CSS frameworks; only Google Fonts as external resource
5. **Maintainability** — CSS custom properties for easy theming, small total CSS footprint

## 1. Design System

### 1.1 Color Palette

All colors defined as CSS custom properties on `:root`:

| Token | Value | Usage |
|-------|-------|-------|
| `--bg-primary` | `#FDFBF7` | Page background — warm off-white |
| `--bg-secondary` | `#F5F0E8` | Card/section backgrounds |
| `--bg-accent` | `#EDE6D8` | Hover states, subtle highlights |
| `--text-primary` | `#2C2825` | Body text — warm dark brown |
| `--text-secondary` | `#6B6560` | Captions, labels, secondary info |
| `--text-muted` | `#9C9590` | Placeholder text, disabled states |
| `--accent` | `#B8860B` | Primary accent — muted gold/dark goldenrod |
| `--accent-light` | `#D4A84B` | Accent hover, highlights |
| `--border` | `#E0D8CC` | Borders, dividers |
| `--code-bg` | `#F0EBE1` | Code block backgrounds |

### 1.2 Typography

- **Headings:** Playfair Display (serif) — weights 600, 700
- **Body:** Inter (sans-serif) — weights 400, 500
- **Code/labels:** JetBrains Mono (monospace) — weight 400
- **Scale:** 1rem = 16px base, modular scale with 1.25 ratio
  - h1: 2.441rem, h2: 1.953rem, h3: 1.563rem, h4: 1.25rem

### 1.3 Spacing

4px base unit. Standard multiples: 8, 12, 16, 24, 32, 48, 64px.

## 2. Layout Structure

### 2.1 Common Shell (All Pages)

**Header:**
- Text-based logo: "OperationsPAI" in Playfair Display
- Horizontal nav links: Home, Vision, Roadmap, Contributing, FAQ, Community
- Clean style — no background color, thin bottom border (`--border`)
- Sticky on scroll
- Mobile: hamburger menu, nav slides in from right (CSS-only, checkbox hack)

**Footer:**
- Minimal: GitHub link, license info, "Built by the community" tagline
- Background: `--bg-secondary`
- Three-column on desktop (about, links, social), stacked on mobile

### 2.2 Layout: Landing Page (`home`)

Full-width sections, top to bottom:

1. **Hero Section**
   - Large serif heading (Playfair Display 700)
   - One-sentence tagline in Inter
   - Two CTA buttons (primary gold + ghost)
   - Small hand-drawn SVG illustration: network/graph motif
   - Generous white space, no background image

2. **Core Capabilities**
   - Section label + serif heading
   - 2x3 grid of feature cards
   - Each card: SVG icon (24x24, `--accent`), serif h3 title, sans-serif description
   - Card style: `--bg-secondary` background, 1px border, 8px border-radius
   - Hover: translateY(-2px) + soft box-shadow

3. **Evolution Timeline**
   - Horizontal 4-step flow: Inject -> Observe -> Analyze -> Adapt
   - Step numbers in `--accent` gold, thin connecting lines
   - Vertical layout on mobile

4. **Community Spotlight**
   - Contributor highlights with circular avatars (48px)
   - Name, role/affiliation, optional one-line quote
   - Horizontal layout on desktop, stacked on mobile

5. **CTA + Quick Links**
   - Final call to action with primary + ghost buttons
   - Documentation grid: 4 link cards (Vision, Roadmap, Contributing, FAQ)

### 2.3 Layout: Documentation (`docs`)

- Left sidebar: section navigation, collapsible on mobile (toggle button)
- Main content: max-width ~65ch for optimal reading
- Right sidebar (desktop only): sticky table of contents
- Well-styled markdown: headings, code blocks, tables, blockquotes

### 2.4 Layout: Community (`community`)

- Single-column centered layout, max-width ~75ch
- No sidebar — more breathing room
- Support for embedded cards: contributor profiles, paper citations, project links

## 3. Components

### 3.1 Cards

**Feature Card:**
- `--bg-secondary` background, 1px `--border`, 8px border-radius
- 24x24 SVG icon in `--accent` at top
- Playfair Display h3, Inter description
- Hover: translateY(-2px) + box-shadow: 0 4px 12px rgba(0,0,0,0.08)

**Link Card:**
- Same as feature card, entire card clickable (`<a>` wrapper)
- Hover: border color shifts to `--accent`

**Contributor Card:**
- Circular avatar (48px), name (Inter 500), role (Inter 400, `--text-secondary`)
- Optional one-line quote in italic
- Horizontal on desktop, stacked on mobile

### 3.2 Buttons

**Primary:** `--accent` background, `--bg-primary` text, 6px border-radius, medium padding (12px 24px). Hover: `--accent-light` background.

**Ghost:** Transparent background, 1px `--accent` border, `--accent` text. Hover: `--bg-accent` background.

### 3.3 Navigation

- Text links in Inter 500
- Underline on hover with `--accent` color
- Active page: small dot indicator below link

### 3.4 Code Blocks

- Background: `--code-bg`
- Left border: 3px solid `--accent`
- Font: JetBrains Mono 400
- Padding: 16px 24px

### 3.5 Blockquotes

- Left border: 3px solid `--accent-light`
- Italic Playfair Display
- Slight indent (24px left margin)

## 4. SVG Illustrations

Five hand-drawn-style line-art illustrations. Thin strokes (1.5-2px), slightly imperfect lines for a human feel. Colors: `--accent` and `--text-secondary`.

1. **Hero: Network Graph** — Interconnected nodes representing microservices. Subtle CSS pulse animation on some nodes (no JS).
2. **Fault Injection: Lightning** — Stylized bolt hitting a node in a service diagram.
3. **Algorithm: Waveform** — Heartbeat-like signal line with analysis markers.
4. **Community: Connected Figures** — Abstract people figures suggesting collaboration.
5. **Research: Open Book** — Book with graph/chart emerging from pages.

All SVGs are inline in HTML with `aria-hidden="true"` (decorative).

## 5. Responsive Design

### Breakpoints

| Name | Width | Key changes |
|------|-------|-------------|
| Mobile | < 640px | Single column, hamburger nav, stacked cards, vertical timeline |
| Tablet | 640-1024px | 2-column feature grid, sidebar collapses |
| Desktop | > 1024px | Full layout — 3-column docs, 2x3 feature grid |

### Mobile Specifics

- Header: Logo + hamburger icon. Nav overlay from right (CSS-only).
- Feature grid: single column, full-width cards
- Evolution timeline: vertical instead of horizontal
- Docs sidebar: hidden by default, toggle button
- Typography scales down ~10%

## 6. Accessibility

- **Color contrast:** All combinations meet WCAG AA (4.5:1 minimum)
  - `--text-primary` on `--bg-primary`: ~13:1
  - `--accent` on `--bg-primary`: ~5.2:1
- **Focus states:** Visible outline using `--accent` on all interactive elements
- **Semantic HTML:** `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`
- **Skip-to-content:** Hidden visually, accessible via keyboard
- **SVGs:** `aria-hidden="true"` on decorative illustrations
- **Links/buttons:** Clear, descriptive text (no "click here")

## 7. Performance

- No JavaScript for core functionality (nav toggle via CSS checkbox hack)
- Google Fonts loaded with `display=swap` — Playfair Display (600,700), Inter (400,500), JetBrains Mono (400). Replaces current Rajdhani + JetBrains Mono.
- All SVGs inline — no extra HTTP requests
- Target: total CSS under 15KB unminified
- No CSS framework dependencies

## 8. File Structure

```
_config.yml                  # Updated: remove old theme references
_layouts/
  default.html               # Common shell (header, footer, fonts)
  home.html                  # Landing page layout
  docs.html                  # Documentation layout (sidebar + TOC)
  community.html             # Community page layout (single column)
_includes/
  header.html                # Sticky header with nav
  footer.html                # Minimal footer
  nav-mobile.html            # Mobile nav overlay (CSS-only)
  svg/
    hero-network.html         # Network graph illustration
    icon-lightning.html        # Fault injection icon
    icon-waveform.html         # Algorithm icon
    icon-community.html        # Community icon
    icon-book.html             # Research icon
assets/
  css/
    main.css                  # All styles — design tokens, layouts, components, responsive
index.md                     # Homepage content (updated HTML)
docs/
  community/
    vision.md
    values.md
    resources.md
  FAQ.md
ROADMAP.md
CONTRIBUTING.md
GOVERNANCE.md
CODE_OF_CONDUCT.md
```

## 9. What Is NOT In Scope

- Dark mode toggle (can be added later via CSS custom properties)
- Search functionality
- Blog/post system
- Analytics integration
- Custom domain setup
- CI/CD pipeline changes
