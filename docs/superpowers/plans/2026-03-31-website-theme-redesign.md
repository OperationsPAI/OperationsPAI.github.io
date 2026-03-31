# Website Theme Redesign — "The Monograph" Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Implement a scholarly, warm-neutral Jekyll theme with great markdown rendering for any content.

**Architecture:** Pure CSS design system (custom properties) + Jekyll layouts + inline SVG illustrations. No frameworks. Layouts are content-agnostic — any markdown file renders beautifully. Only `index.md` uses custom HTML sections for the landing page.

**Tech Stack:** Jekyll (github-pages gem), CSS custom properties, Google Fonts (Playfair Display, Inter, JetBrains Mono), inline SVGs.

**Key Principle:** Layouts style standard HTML elements generically. All heading levels, paragraphs, lists, tables, code blocks, blockquotes, images, and links must look excellent without any special classes. The homepage is the only page with custom HTML.

---

### Task 1: CSS Design System — Tokens, Reset, and Typography

**Files:**
- Create: `assets/css/main.css`

This is the foundation. All design tokens, base reset, and typography styles for rendering any markdown content.

- [ ] **Step 1: Create the CSS file with design tokens and reset**

```css
/* ============================================
   The Monograph — OperationsPAI Design System
   ============================================ */

/* --- Design Tokens --- */
:root {
  --bg-primary: #FDFBF7;
  --bg-secondary: #F5F0E8;
  --bg-accent: #EDE6D8;
  --text-primary: #2C2825;
  --text-secondary: #6B6560;
  --text-muted: #9C9590;
  --accent: #B8860B;
  --accent-light: #D4A84B;
  --border: #E0D8CC;
  --code-bg: #F0EBE1;

  --font-heading: 'Playfair Display', Georgia, 'Times New Roman', serif;
  --font-body: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;

  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 32px;
  --space-2xl: 48px;
  --space-3xl: 64px;

  --max-width: 1200px;
  --content-width: 65ch;
  --content-wide: 75ch;
}

/* --- Reset --- */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  font-size: 16px;
  scroll-behavior: smooth;
  -webkit-text-size-adjust: 100%;
}

body {
  font-family: var(--font-body);
  font-weight: 400;
  line-height: 1.7;
  color: var(--text-primary);
  background-color: var(--bg-primary);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

img, svg, video {
  display: block;
  max-width: 100%;
  height: auto;
}

a {
  color: var(--accent);
  text-decoration-thickness: 1px;
  text-underline-offset: 2px;
  transition: color 0.2s ease;
}

a:hover {
  color: var(--accent-light);
}

a:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 2px;
  border-radius: 2px;
}

/* --- Typography — Generic Markdown Rendering --- */

h1, h2, h3, h4, h5, h6 {
  font-family: var(--font-heading);
  font-weight: 700;
  line-height: 1.3;
  color: var(--text-primary);
}

h1 { font-size: 2.441rem; margin: var(--space-3xl) 0 var(--space-lg); }
h2 { font-size: 1.953rem; margin: var(--space-2xl) 0 var(--space-md); }
h3 { font-size: 1.563rem; margin: var(--space-xl) 0 var(--space-md); }
h4 { font-size: 1.25rem;  margin: var(--space-lg) 0 var(--space-sm); }
h5 { font-size: 1.1rem;   margin: var(--space-lg) 0 var(--space-sm); }
h6 { font-size: 1rem;     margin: var(--space-lg) 0 var(--space-sm); font-style: italic; }

/* First heading on page — no top margin */
h1:first-child, h2:first-child, h3:first-child {
  margin-top: 0;
}

p {
  margin: 0 0 var(--space-md);
}

/* --- Lists --- */
ul, ol {
  margin: 0 0 var(--space-md);
  padding-left: var(--space-lg);
}

li {
  margin-bottom: var(--space-xs);
}

li > ul, li > ol {
  margin-top: var(--space-xs);
  margin-bottom: 0;
}

/* Task lists (GitHub Flavored Markdown) */
ul.task-list, .task-list {
  list-style: none;
  padding-left: 0;
}

.task-list li {
  position: relative;
  padding-left: var(--space-lg);
}

.task-list input[type="checkbox"] {
  position: absolute;
  left: 0;
  top: 0.35em;
  accent-color: var(--accent);
}

/* --- Blockquotes --- */
blockquote {
  margin: var(--space-lg) 0;
  padding: var(--space-md) var(--space-lg);
  border-left: 3px solid var(--accent-light);
  background: transparent;
  font-family: var(--font-heading);
  font-style: italic;
  color: var(--text-secondary);
}

blockquote p:last-child {
  margin-bottom: 0;
}

blockquote blockquote {
  margin-top: var(--space-md);
}

/* --- Code --- */
code {
  font-family: var(--font-mono);
  font-size: 0.875em;
  background: var(--code-bg);
  padding: 2px 6px;
  border-radius: 3px;
  color: var(--text-primary);
}

pre {
  margin: var(--space-lg) 0;
  padding: var(--space-md) var(--space-lg);
  background: var(--code-bg);
  border-left: 3px solid var(--accent);
  border-radius: 4px;
  overflow-x: auto;
  line-height: 1.5;
}

pre code {
  background: none;
  padding: 0;
  border-radius: 0;
  font-size: 0.85rem;
}

/* --- Tables --- */
table {
  width: 100%;
  margin: var(--space-lg) 0;
  border-collapse: collapse;
  font-size: 0.95rem;
}

thead {
  border-bottom: 2px solid var(--border);
}

th {
  font-family: var(--font-heading);
  font-weight: 600;
  text-align: left;
  padding: var(--space-sm) var(--space-md);
  color: var(--text-primary);
}

td {
  padding: var(--space-sm) var(--space-md);
  border-bottom: 1px solid var(--border);
}

tbody tr:hover {
  background: var(--bg-secondary);
}

/* --- Horizontal Rule --- */
hr {
  border: none;
  border-top: 1px solid var(--border);
  margin: var(--space-2xl) 0;
}

/* --- Images in markdown --- */
.content img {
  border-radius: 6px;
  border: 1px solid var(--border);
  margin: var(--space-lg) 0;
}

/* --- Definition lists --- */
dl {
  margin: 0 0 var(--space-md);
}

dt {
  font-weight: 600;
  margin-top: var(--space-md);
}

dd {
  margin-left: var(--space-lg);
  color: var(--text-secondary);
}

/* --- Keyboard / abbreviations --- */
kbd {
  font-family: var(--font-mono);
  font-size: 0.85em;
  padding: 2px 6px;
  border: 1px solid var(--border);
  border-radius: 3px;
  background: var(--bg-secondary);
  box-shadow: 0 1px 0 var(--border);
}

abbr[title] {
  text-decoration: underline dotted var(--text-muted);
  cursor: help;
}

/* --- Details / Summary --- */
details {
  margin: var(--space-md) 0;
  padding: var(--space-md);
  background: var(--bg-secondary);
  border-radius: 6px;
  border: 1px solid var(--border);
}

summary {
  cursor: pointer;
  font-weight: 500;
  color: var(--text-primary);
}

details[open] summary {
  margin-bottom: var(--space-md);
}
```

- [ ] **Step 2: Verify the file was created**

Run: `wc -l assets/css/main.css`
Expected: ~230 lines

- [ ] **Step 3: Commit**

```bash
git add assets/css/main.css
git commit -m "feat: add CSS design tokens, reset, and markdown typography"
```

---

### Task 2: CSS — Layout, Components, and Responsive

**Files:**
- Modify: `assets/css/main.css` (append)

Adds layout system, card/button components, header/footer styles, and all responsive breakpoints.

- [ ] **Step 1: Append layout and component styles to main.css**

Append the following after the existing content:

```css
/* ============================================
   Layout
   ============================================ */

/* --- Skip to content (accessibility) --- */
.skip-link {
  position: absolute;
  top: -100%;
  left: var(--space-md);
  padding: var(--space-sm) var(--space-md);
  background: var(--accent);
  color: var(--bg-primary);
  border-radius: 0 0 4px 4px;
  z-index: 1000;
  font-size: 0.875rem;
  text-decoration: none;
}

.skip-link:focus {
  top: 0;
}

/* --- Site Header --- */
.site-header {
  position: sticky;
  top: 0;
  z-index: 100;
  background: var(--bg-primary);
  border-bottom: 1px solid var(--border);
}

.header-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--space-md) var(--space-lg);
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.site-logo {
  font-family: var(--font-heading);
  font-size: 1.35rem;
  font-weight: 700;
  color: var(--text-primary);
  text-decoration: none;
}

.site-logo:hover {
  color: var(--accent);
}

.site-nav {
  display: flex;
  align-items: center;
  gap: var(--space-lg);
}

.site-nav a {
  font-family: var(--font-body);
  font-weight: 500;
  font-size: 0.9rem;
  color: var(--text-secondary);
  text-decoration: none;
  position: relative;
  padding-bottom: 4px;
}

.site-nav a:hover {
  color: var(--text-primary);
}

.site-nav a.active {
  color: var(--text-primary);
}

.site-nav a.active::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 50%;
  transform: translateX(-50%);
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background: var(--accent);
}

/* --- Mobile Nav (CSS-only) --- */
.nav-toggle {
  display: none;
}

.nav-toggle-label {
  display: none;
  cursor: pointer;
  width: 28px;
  height: 20px;
  position: relative;
  z-index: 200;
}

.nav-toggle-label span,
.nav-toggle-label span::before,
.nav-toggle-label span::after {
  display: block;
  width: 100%;
  height: 2px;
  background: var(--text-primary);
  border-radius: 2px;
  position: absolute;
  transition: all 0.3s ease;
}

.nav-toggle-label span { top: 50%; transform: translateY(-50%); }
.nav-toggle-label span::before { content: ''; top: -8px; }
.nav-toggle-label span::after { content: ''; top: 8px; }

.nav-toggle:checked ~ .nav-toggle-label span { background: transparent; }
.nav-toggle:checked ~ .nav-toggle-label span::before { top: 0; transform: rotate(45deg); }
.nav-toggle:checked ~ .nav-toggle-label span::after { top: 0; transform: rotate(-45deg); }

.nav-toggle:checked ~ .site-nav {
  transform: translateX(0);
}

/* --- Site Footer --- */
.site-footer {
  background: var(--bg-secondary);
  border-top: 1px solid var(--border);
  margin-top: var(--space-3xl);
}

.footer-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--space-2xl) var(--space-lg);
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  gap: var(--space-xl);
}

.footer-section h4 {
  font-family: var(--font-heading);
  font-size: 1rem;
  margin: 0 0 var(--space-md);
  color: var(--text-primary);
}

.footer-section p,
.footer-section a {
  font-size: 0.875rem;
  color: var(--text-secondary);
}

.footer-section a {
  text-decoration: none;
  display: block;
  margin-bottom: var(--space-xs);
}

.footer-section a:hover {
  color: var(--accent);
}

.footer-bottom {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--space-md) var(--space-lg);
  border-top: 1px solid var(--border);
  font-size: 0.8rem;
  color: var(--text-muted);
  text-align: center;
}

/* --- Content Container --- */
.content {
  max-width: var(--content-width);
  margin: 0 auto;
  padding: var(--space-2xl) var(--space-lg);
}

.content-wide {
  max-width: var(--content-wide);
  margin: 0 auto;
  padding: var(--space-2xl) var(--space-lg);
}

.content-full {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--space-2xl) var(--space-lg);
}

/* ============================================
   Components
   ============================================ */

/* --- Buttons --- */
.btn {
  display: inline-flex;
  align-items: center;
  gap: var(--space-sm);
  padding: 12px 24px;
  border-radius: 6px;
  font-family: var(--font-body);
  font-weight: 500;
  font-size: 0.95rem;
  text-decoration: none;
  transition: all 0.2s ease;
  cursor: pointer;
  border: none;
}

.btn:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 2px;
}

.btn-primary {
  background: var(--accent);
  color: var(--bg-primary);
}

.btn-primary:hover {
  background: var(--accent-light);
  color: var(--bg-primary);
}

.btn-ghost {
  background: transparent;
  border: 1px solid var(--accent);
  color: var(--accent);
}

.btn-ghost:hover {
  background: var(--bg-accent);
  color: var(--accent);
}

/* --- Cards --- */
.card {
  background: var(--bg-secondary);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: var(--space-lg);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}

.card-icon {
  width: 24px;
  height: 24px;
  color: var(--accent);
  margin-bottom: var(--space-md);
}

.card h3 {
  font-family: var(--font-heading);
  font-size: 1.15rem;
  margin: 0 0 var(--space-sm);
}

.card p {
  font-size: 0.9rem;
  color: var(--text-secondary);
  margin: 0;
}

/* Link card — entire card clickable */
a.card {
  text-decoration: none;
  color: inherit;
  display: block;
}

a.card:hover {
  border-color: var(--accent);
}

a.card h3 {
  color: var(--text-primary);
}

/* --- Grid --- */
.grid {
  display: grid;
  gap: var(--space-lg);
}

.grid-2 { grid-template-columns: repeat(2, 1fr); }
.grid-3 { grid-template-columns: repeat(3, 1fr); }
.grid-auto { grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); }

/* --- Section helpers --- */
.section {
  padding: var(--space-3xl) 0;
}

.section-label {
  font-family: var(--font-mono);
  font-size: 0.8rem;
  color: var(--accent);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  display: block;
  margin-bottom: var(--space-sm);
}

.section-title {
  font-family: var(--font-heading);
  font-size: 1.953rem;
  margin: 0 0 var(--space-md);
}

.section-desc {
  color: var(--text-secondary);
  max-width: var(--content-width);
  margin-bottom: var(--space-xl);
}

.section-header {
  margin-bottom: var(--space-xl);
}

/* --- Contributor Card --- */
.contributor {
  display: flex;
  align-items: center;
  gap: var(--space-md);
  padding: var(--space-md);
  background: var(--bg-secondary);
  border-radius: 8px;
  border: 1px solid var(--border);
}

.contributor img {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  object-fit: cover;
}

.contributor-name {
  font-weight: 500;
  font-size: 0.95rem;
}

.contributor-role {
  font-size: 0.85rem;
  color: var(--text-secondary);
}

.contributor-quote {
  font-style: italic;
  font-size: 0.85rem;
  color: var(--text-secondary);
  margin-top: var(--space-xs);
}

/* --- Evolution / Timeline --- */
.timeline {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-lg);
  padding: var(--space-xl) 0;
}

.timeline-step {
  text-align: center;
}

.timeline-number {
  font-family: var(--font-heading);
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--accent);
}

.timeline-label {
  font-family: var(--font-body);
  font-weight: 500;
  font-size: 0.9rem;
  color: var(--text-secondary);
  margin-top: var(--space-xs);
}

.timeline-arrow {
  font-size: 1.25rem;
  color: var(--border);
}

/* --- Hero (homepage only) --- */
.hero {
  padding: var(--space-3xl) var(--space-lg);
  max-width: var(--max-width);
  margin: 0 auto;
  display: flex;
  align-items: center;
  gap: var(--space-3xl);
}

.hero-content {
  flex: 1;
}

.hero-illustration {
  flex: 0 0 auto;
  width: 280px;
  height: 280px;
  color: var(--accent);
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: var(--space-sm);
  font-family: var(--font-mono);
  font-size: 0.8rem;
  color: var(--accent);
  margin-bottom: var(--space-lg);
}

.hero-badge .dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--accent);
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.4; }
}

.hero h1 {
  font-size: 2.8rem;
  margin: 0 0 var(--space-md);
  line-height: 1.15;
}

.hero h1 em {
  font-style: normal;
  color: var(--accent);
}

.hero-tagline {
  font-size: 1.15rem;
  color: var(--text-secondary);
  line-height: 1.6;
  margin-bottom: var(--space-xl);
  max-width: 540px;
}

.hero-actions {
  display: flex;
  gap: var(--space-md);
  flex-wrap: wrap;
}

/* ============================================
   Layout: Docs (sidebar + TOC)
   ============================================ */

.docs-layout {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--space-xl) var(--space-lg);
  display: grid;
  grid-template-columns: 220px 1fr 180px;
  gap: var(--space-xl);
}

.docs-sidebar {
  position: sticky;
  top: 80px;
  max-height: calc(100vh - 100px);
  overflow-y: auto;
}

.docs-sidebar nav a {
  display: block;
  padding: var(--space-xs) var(--space-sm);
  font-size: 0.875rem;
  color: var(--text-secondary);
  text-decoration: none;
  border-radius: 4px;
}

.docs-sidebar nav a:hover {
  color: var(--text-primary);
  background: var(--bg-secondary);
}

.docs-sidebar nav a.active {
  color: var(--accent);
  background: var(--bg-accent);
}

.docs-content {
  max-width: var(--content-width);
  min-width: 0;
}

.docs-toc {
  position: sticky;
  top: 80px;
  max-height: calc(100vh - 100px);
  overflow-y: auto;
  font-size: 0.8rem;
}

.docs-toc a {
  display: block;
  padding: var(--space-xs) 0;
  color: var(--text-muted);
  text-decoration: none;
}

.docs-toc a:hover {
  color: var(--accent);
}

/* Sidebar toggle for mobile */
.docs-sidebar-toggle {
  display: none;
}

/* ============================================
   Responsive
   ============================================ */

@media (max-width: 1024px) {
  :root {
    --space-3xl: 48px;
  }

  h1 { font-size: 2rem; }
  h2 { font-size: 1.65rem; }

  .hero h1 { font-size: 2.2rem; }

  .grid-3 { grid-template-columns: repeat(2, 1fr); }

  .docs-layout {
    grid-template-columns: 200px 1fr;
  }

  .docs-toc {
    display: none;
  }

  .hero-illustration {
    width: 200px;
    height: 200px;
  }

  .footer-inner {
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-width: 640px) {
  :root {
    --space-2xl: 32px;
    --space-3xl: 40px;
  }

  h1 { font-size: 1.75rem; }
  h2 { font-size: 1.45rem; }
  h3 { font-size: 1.25rem; }

  .hero h1 { font-size: 1.85rem; }

  /* Mobile nav */
  .nav-toggle-label {
    display: block;
  }

  .site-nav {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    width: 260px;
    background: var(--bg-primary);
    border-left: 1px solid var(--border);
    flex-direction: column;
    padding: var(--space-3xl) var(--space-lg) var(--space-lg);
    transform: translateX(100%);
    transition: transform 0.3s ease;
    z-index: 150;
    gap: var(--space-md);
  }

  .site-nav a {
    font-size: 1rem;
    padding: var(--space-sm) 0;
  }

  /* Hero stacked */
  .hero {
    flex-direction: column;
    text-align: center;
    padding: var(--space-2xl) var(--space-md);
  }

  .hero-tagline {
    margin-left: auto;
    margin-right: auto;
  }

  .hero-actions {
    justify-content: center;
  }

  .hero-illustration {
    width: 180px;
    height: 180px;
    order: -1;
  }

  /* Grid single column */
  .grid-2, .grid-3 { grid-template-columns: 1fr; }

  /* Timeline vertical */
  .timeline {
    flex-direction: column;
    gap: var(--space-md);
  }

  .timeline-arrow {
    transform: rotate(90deg);
  }

  /* Docs sidebar */
  .docs-layout {
    grid-template-columns: 1fr;
  }

  .docs-sidebar {
    position: static;
    max-height: none;
    display: none;
  }

  .docs-sidebar-toggle {
    display: block;
    margin-bottom: var(--space-md);
  }

  .docs-sidebar-toggle:checked ~ .docs-sidebar {
    display: block;
  }

  /* Footer single column */
  .footer-inner {
    grid-template-columns: 1fr;
    gap: var(--space-lg);
  }

  .content, .content-wide {
    padding: var(--space-xl) var(--space-md);
  }
}

/* --- Print styles --- */
@media print {
  .site-header, .site-footer, .hero-illustration, .docs-sidebar, .docs-toc {
    display: none;
  }

  body {
    color: #000;
    background: #fff;
  }

  a { color: #000; text-decoration: underline; }
  a[href]::after { content: " (" attr(href) ")"; font-size: 0.8em; }
}
```

- [ ] **Step 2: Verify total CSS size**

Run: `wc -l assets/css/main.css && wc -c assets/css/main.css`
Expected: ~600 lines, under 15KB

- [ ] **Step 3: Commit**

```bash
git add assets/css/main.css
git commit -m "feat: add layout, components, and responsive styles"
```

---

### Task 3: Header and Footer Includes

**Files:**
- Create: `_includes/header.html`
- Create: `_includes/footer.html`

These are shared across all layouts.

- [ ] **Step 1: Create header.html**

```html
<a href="#main-content" class="skip-link">Skip to content</a>

<header class="site-header">
  <div class="header-inner">
    <a href="{{ '/' | relative_url }}" class="site-logo">OperationsPAI</a>

    <input type="checkbox" id="nav-toggle" class="nav-toggle" aria-hidden="true">
    <label for="nav-toggle" class="nav-toggle-label" aria-label="Toggle navigation">
      <span></span>
    </label>

    <nav class="site-nav" aria-label="Main navigation">
      <a href="{{ '/' | relative_url }}" {% if page.url == '/' %}class="active"{% endif %}>Home</a>
      <a href="{{ '/docs/community/vision.html' | relative_url }}" {% if page.url contains 'vision' %}class="active"{% endif %}>Vision</a>
      <a href="{{ '/ROADMAP.html' | relative_url }}" {% if page.url contains 'ROADMAP' %}class="active"{% endif %}>Roadmap</a>
      <a href="{{ '/CONTRIBUTING.html' | relative_url }}" {% if page.url contains 'CONTRIBUTING' %}class="active"{% endif %}>Contributing</a>
      <a href="{{ '/docs/FAQ.html' | relative_url }}" {% if page.url contains 'FAQ' %}class="active"{% endif %}>FAQ</a>
      <a href="https://github.com/OperationsPAI" target="_blank" rel="noopener">GitHub</a>
    </nav>
  </div>
</header>
```

- [ ] **Step 2: Create footer.html**

```html
<footer class="site-footer">
  <div class="footer-inner">
    <div class="footer-section">
      <h4>OperationsPAI</h4>
      <p>Building the world's first self-evolving training environment for Root Cause Analysis in microservices.</p>
    </div>
    <div class="footer-section">
      <h4>Resources</h4>
      <a href="{{ '/docs/community/vision.html' | relative_url }}">Vision</a>
      <a href="{{ '/ROADMAP.html' | relative_url }}">Roadmap</a>
      <a href="{{ '/CONTRIBUTING.html' | relative_url }}">Contributing</a>
      <a href="{{ '/docs/FAQ.html' | relative_url }}">FAQ</a>
    </div>
    <div class="footer-section">
      <h4>Community</h4>
      <a href="https://github.com/OperationsPAI" target="_blank" rel="noopener">GitHub</a>
      <a href="{{ '/GOVERNANCE.html' | relative_url }}">Governance</a>
      <a href="{{ '/CODE_OF_CONDUCT.html' | relative_url }}">Code of Conduct</a>
    </div>
  </div>
  <div class="footer-bottom">
    Built by the community. Licensed under Apache 2.0.
  </div>
</footer>
```

- [ ] **Step 3: Commit**

```bash
git add _includes/header.html _includes/footer.html
git commit -m "feat: add header and footer includes"
```

---

### Task 4: SVG Illustration Includes

**Files:**
- Create: `_includes/svg/hero-network.html`
- Create: `_includes/svg/icon-lightning.html`
- Create: `_includes/svg/icon-waveform.html`
- Create: `_includes/svg/icon-community.html`
- Create: `_includes/svg/icon-book.html`

Hand-drawn-style line-art SVGs using `currentColor` so they inherit the accent color.

- [ ] **Step 1: Create hero-network.html — interconnected microservice nodes**

```html
<!-- Hero: Network graph — interconnected microservice nodes -->
<svg viewBox="0 0 280 280" fill="none" aria-hidden="true" class="hero-illustration">
  <style>
    .node-pulse { animation: node-pulse 3s ease-in-out infinite; }
    .node-pulse-delay { animation: node-pulse 3s ease-in-out 1.5s infinite; }
    @keyframes node-pulse { 0%,100% { opacity: 0.7; } 50% { opacity: 1; } }
  </style>
  <!-- Connection lines — slightly imperfect paths -->
  <path d="M140 60 L80 130" stroke="currentColor" stroke-width="1.5" opacity="0.3" stroke-linecap="round"/>
  <path d="M140 60 L200 120" stroke="currentColor" stroke-width="1.5" opacity="0.3" stroke-linecap="round"/>
  <path d="M80 130 L60 210" stroke="currentColor" stroke-width="1.5" opacity="0.3" stroke-linecap="round"/>
  <path d="M80 130 L150 180" stroke="currentColor" stroke-width="1.5" opacity="0.3" stroke-linecap="round"/>
  <path d="M200 120 L150 180" stroke="currentColor" stroke-width="1.5" opacity="0.3" stroke-linecap="round"/>
  <path d="M200 120 L230 200" stroke="currentColor" stroke-width="1.5" opacity="0.3" stroke-linecap="round"/>
  <path d="M150 180 L130 250" stroke="currentColor" stroke-width="1.5" opacity="0.3" stroke-linecap="round"/>
  <path d="M60 210 L130 250" stroke="currentColor" stroke-width="1.5" opacity="0.3" stroke-linecap="round"/>
  <path d="M230 200 L130 250" stroke="currentColor" stroke-width="1.5" opacity="0.3" stroke-linecap="round"/>
  <!-- Nodes -->
  <circle cx="140" cy="60" r="12" stroke="currentColor" stroke-width="2" fill="none" class="node-pulse"/>
  <circle cx="140" cy="60" r="4" fill="currentColor" class="node-pulse"/>
  <circle cx="80" cy="130" r="10" stroke="currentColor" stroke-width="1.5" fill="none" class="node-pulse-delay"/>
  <circle cx="80" cy="130" r="3.5" fill="currentColor" class="node-pulse-delay"/>
  <circle cx="200" cy="120" r="10" stroke="currentColor" stroke-width="1.5" fill="none"/>
  <circle cx="200" cy="120" r="3.5" fill="currentColor"/>
  <circle cx="150" cy="180" r="14" stroke="currentColor" stroke-width="2" fill="none" class="node-pulse"/>
  <circle cx="150" cy="180" r="5" fill="currentColor" class="node-pulse"/>
  <circle cx="60" cy="210" r="8" stroke="currentColor" stroke-width="1.5" fill="none" class="node-pulse-delay"/>
  <circle cx="60" cy="210" r="3" fill="currentColor" class="node-pulse-delay"/>
  <circle cx="230" cy="200" r="9" stroke="currentColor" stroke-width="1.5" fill="none"/>
  <circle cx="230" cy="200" r="3" fill="currentColor"/>
  <circle cx="130" cy="250" r="11" stroke="currentColor" stroke-width="2" fill="none" class="node-pulse"/>
  <circle cx="130" cy="250" r="4" fill="currentColor" class="node-pulse"/>
  <!-- Small satellite dots -->
  <circle cx="110" cy="42" r="2" fill="currentColor" opacity="0.4"/>
  <circle cx="168" cy="48" r="2.5" fill="currentColor" opacity="0.3"/>
  <circle cx="248" cy="175" r="2" fill="currentColor" opacity="0.4"/>
  <circle cx="38" cy="195" r="2" fill="currentColor" opacity="0.3"/>
</svg>
```

- [ ] **Step 2: Create icon-lightning.html**

```html
<!-- Fault Injection: Lightning bolt -->
<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
  <path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/>
</svg>
```

- [ ] **Step 3: Create icon-waveform.html**

```html
<!-- Algorithm: Waveform / signal analysis -->
<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
  <polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/>
</svg>
```

- [ ] **Step 4: Create icon-community.html**

```html
<!-- Community: Connected figures -->
<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
  <path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/>
  <circle cx="9" cy="7" r="4"/>
  <path d="M23 21v-2a4 4 0 0 0-3-3.87"/>
  <path d="M16 3.13a4 4 0 0 1 0 7.75"/>
</svg>
```

- [ ] **Step 5: Create icon-book.html**

```html
<!-- Research: Open book with chart -->
<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
  <path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/>
  <path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/>
</svg>
```

- [ ] **Step 6: Commit**

```bash
git add _includes/svg/
git commit -m "feat: add SVG illustration includes"
```

---

### Task 5: Layouts — default.html, home.html, docs.html, community.html

**Files:**
- Modify: `_layouts/default.html`
- Create: `_layouts/home.html`
- Create: `_layouts/docs.html`
- Create: `_layouts/community.html`

All layouts render `{{ content }}` generically. Only `home.html` has a different wrapper.

- [ ] **Step 1: Rewrite _layouts/default.html — common shell**

Replace the entire file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ page.title | default: site.title }}</title>
  <meta name="description" content="{{ page.description | default: site.description | strip_html | truncatewords: 50 }}">

  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500&family=JetBrains+Mono:wght@400&family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">

  <!-- Styles -->
  <link rel="stylesheet" href="{{ '/assets/css/main.css' | relative_url }}">

  <!-- Favicon -->
  <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>&#9672;</text></svg>">
</head>
<body>
  {% include header.html %}

  <main id="main-content">
    {{ content }}
  </main>

  {% include footer.html %}
</body>
</html>
```

- [ ] **Step 2: Create _layouts/home.html — landing page**

This wraps `{{ content }}` in a full-width container. The actual homepage HTML sections live in `index.md`.

```html
---
layout: default
---

<div class="content-full">
  {{ content }}
</div>
```

- [ ] **Step 3: Create _layouts/docs.html — documentation with sidebar**

```html
---
layout: default
---

<div class="docs-layout">
  <input type="checkbox" id="sidebar-toggle" class="docs-sidebar-toggle" aria-hidden="true">
  <label for="sidebar-toggle" class="btn btn-ghost docs-sidebar-toggle" style="display:none;">
    Toggle Navigation
  </label>

  <aside class="docs-sidebar">
    <nav aria-label="Documentation navigation">
      <a href="{{ '/docs/community/vision.html' | relative_url }}">Vision</a>
      <a href="{{ '/docs/community/values.html' | relative_url }}">Values</a>
      <a href="{{ '/docs/community/resources.html' | relative_url }}">Resources</a>
      <a href="{{ '/docs/FAQ.html' | relative_url }}">FAQ</a>
      <a href="{{ '/ROADMAP.html' | relative_url }}">Roadmap</a>
      <a href="{{ '/CONTRIBUTING.html' | relative_url }}">Contributing</a>
      <a href="{{ '/GOVERNANCE.html' | relative_url }}">Governance</a>
    </nav>
  </aside>

  <article class="docs-content content">
    {{ content }}
  </article>

  <aside class="docs-toc" aria-label="Table of contents">
    <!-- TOC is auto-generated by Jekyll or can be populated per-page -->
  </aside>
</div>
```

- [ ] **Step 4: Create _layouts/community.html — wide single-column**

```html
---
layout: default
---

<article class="content-wide">
  {{ content }}
</article>
```

- [ ] **Step 5: Commit**

```bash
git add _layouts/
git commit -m "feat: add default, home, docs, and community layouts"
```

---

### Task 6: Update index.md — Homepage Content

**Files:**
- Modify: `index.md`

Rewrite the homepage to use the new CSS classes and SVG includes. This is the only page with custom HTML — all other pages are pure markdown.

- [ ] **Step 1: Rewrite index.md**

Replace the entire file with:

```markdown
---
layout: home
title: OperationsPAI - Self-Evolving RCA Training Environment
---

<!-- Hero Section -->
<section class="hero">
  <div class="hero-content">
    <div class="hero-badge">
      <span class="dot"></span>
      Open Source Community
    </div>

    <h1>World's First <em>Self-Evolving</em> RCA Training Environment</h1>

    <p class="hero-tagline">
      Intelligent fault injection, algorithm evaluation, and microservice testing
      for building the next generation of root cause analysis systems.
    </p>

    <div class="hero-actions">
      <a href="https://github.com/OperationsPAI" class="btn btn-primary" target="_blank" rel="noopener">
        Join on GitHub
      </a>
      <a href="{{ '/docs/community/vision.html' | relative_url }}" class="btn btn-ghost">
        Explore Vision
      </a>
    </div>
  </div>

  {% include svg/hero-network.html %}
</section>

<!-- Core Capabilities -->
<section class="section">
  <div class="section-header">
    <span class="section-label">Core Capabilities</span>
    <h2 class="section-title">Intelligent. Adaptive. Evolving.</h2>
    <p class="section-desc">
      Our platform combines cutting-edge AI with real-world microservice architectures
      to create the ultimate training ground for root cause analysis.
    </p>
  </div>

  <div class="grid grid-auto">
    <div class="card">
      {% include svg/icon-lightning.html %}
      <h3>Intelligent Fault Injection</h3>
      <p>Advanced fault injection that simulates real-world microservice failures.
        From network latency to cascading failures, test against production-like scenarios.</p>
    </div>

    <div class="card">
      {% include svg/icon-waveform.html %}
      <h3>Algorithm Evaluation</h3>
      <p>Comprehensive benchmarking framework for comparing RCA algorithms.
        Standardized metrics, reproducible experiments, and detailed analysis.</p>
    </div>

    <div class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <rect x="2" y="3" width="20" height="14" rx="2" ry="2"/>
        <line x1="8" y1="21" x2="16" y2="21"/>
        <line x1="12" y1="17" x2="12" y2="21"/>
      </svg>
      <h3>Microservice Testing</h3>
      <p>Production-grade testbed with realistic service dependencies.
        Deploy, monitor, and analyze distributed systems in a controlled environment.</p>
    </div>

    <div class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <path d="M12 2v4"/><path d="M12 18v4"/>
        <path d="M4.93 4.93l2.83 2.83"/><path d="M16.24 16.24l2.83 2.83"/>
        <path d="M2 12h4"/><path d="M18 12h4"/>
        <path d="M4.93 19.07l2.83-2.83"/><path d="M16.24 7.76l2.83-2.83"/>
      </svg>
      <h3>Self-Evolving System</h3>
      <p>Continuously expanding fault scenario library. The platform learns from new failure patterns
        and automatically generates challenging test cases.</p>
    </div>

    <div class="card">
      {% include svg/icon-book.html %}
      <h3>Research Ready</h3>
      <p>Designed for academic research with citation support, experiment reproducibility,
        and integration with PyTorch and TensorFlow.</p>
    </div>

    <div class="card">
      {% include svg/icon-community.html %}
      <h3>Open Community</h3>
      <p>Active community of researchers and engineers.
        Contribute algorithms, share experiments, and collaborate on advancing RCA.</p>
    </div>
  </div>
</section>

<!-- Evolution -->
<section class="section" style="background: var(--bg-secondary); margin: 0 calc(-1 * var(--space-lg)); padding-left: var(--space-lg); padding-right: var(--space-lg);">
  <div class="section-header" style="text-align: center;">
    <span class="section-label">The Evolution</span>
    <h2 class="section-title">From Static to Living Systems</h2>
    <p class="section-desc" style="margin-left: auto; margin-right: auto;">
      Traditional RCA tools are static. OperationsPAI evolves.
    </p>
  </div>

  <div class="timeline">
    <div class="timeline-step">
      <div class="timeline-number">01</div>
      <div class="timeline-label">Inject</div>
    </div>
    <div class="timeline-arrow">&#8594;</div>
    <div class="timeline-step">
      <div class="timeline-number">02</div>
      <div class="timeline-label">Observe</div>
    </div>
    <div class="timeline-arrow">&#8594;</div>
    <div class="timeline-step">
      <div class="timeline-number">03</div>
      <div class="timeline-label">Analyze</div>
    </div>
    <div class="timeline-arrow">&#8594;</div>
    <div class="timeline-step">
      <div class="timeline-number">04</div>
      <div class="timeline-label">Adapt</div>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="section" style="text-align: center;">
  <h2 class="section-title">Ready to Evolve?</h2>
  <p class="section-desc" style="margin-left: auto; margin-right: auto;">
    Join our community of researchers and engineers building the future
    of root cause analysis.
  </p>
  <div class="hero-actions" style="justify-content: center;">
    <a href="{{ '/CONTRIBUTING.html' | relative_url }}" class="btn btn-primary">
      Start Contributing
    </a>
    <a href="{{ '/docs/FAQ.html' | relative_url }}" class="btn btn-ghost">
      Read FAQ
    </a>
  </div>
</section>

<!-- Quick Links -->
<section class="section">
  <div class="section-header">
    <span class="section-label">Documentation</span>
    <h2 class="section-title">Explore Our Resources</h2>
  </div>

  <div class="grid grid-auto">
    <a href="{{ '/docs/community/vision.html' | relative_url }}" class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <circle cx="12" cy="12" r="10"/>
        <line x1="12" y1="16" x2="12" y2="12"/>
        <line x1="12" y1="8" x2="12.01" y2="8"/>
      </svg>
      <h3>Vision &amp; Mission</h3>
      <p>Our long-term goals and the future we are building towards.</p>
    </a>

    <a href="{{ '/ROADMAP.html' | relative_url }}" class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <line x1="18" y1="20" x2="18" y2="10"/>
        <line x1="12" y1="20" x2="12" y2="4"/>
        <line x1="6" y1="20" x2="6" y2="14"/>
      </svg>
      <h3>Project Roadmap</h3>
      <p>Timeline, milestones, and upcoming features.</p>
    </a>

    <a href="{{ '/CONTRIBUTING.html' | relative_url }}" class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <line x1="12" y1="5" x2="12" y2="19"/>
        <line x1="5" y1="12" x2="19" y2="12"/>
      </svg>
      <h3>Contributing Guide</h3>
      <p>How to get involved and make an impact.</p>
    </a>

    <a href="{{ '/docs/FAQ.html' | relative_url }}" class="card">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true" class="card-icon">
        <circle cx="12" cy="12" r="10"/>
        <path d="M9.09 9a3 3 0 0 1 5.83 1c0 2-3 3-3 3"/>
        <line x1="12" y1="17" x2="12.01" y2="17"/>
      </svg>
      <h3>FAQ</h3>
      <p>Frequently asked questions and answers.</p>
    </a>
  </div>
</section>
```

- [ ] **Step 2: Commit**

```bash
git add index.md
git commit -m "feat: rewrite homepage with new theme classes and SVG includes"
```

---

### Task 7: Update _config.yml

**Files:**
- Modify: `_config.yml`

Ensure no conflicting theme is set, and add the new layouts to defaults.

- [ ] **Step 1: Update _config.yml**

Add defaults section at the end of the file (after the `exclude:` block):

```yaml

# Layout defaults
defaults:
  - scope:
      path: ""
    values:
      layout: "default"
  - scope:
      path: "docs"
    values:
      layout: "docs"
```

- [ ] **Step 2: Commit**

```bash
git add _config.yml
git commit -m "feat: add layout defaults to config"
```

---

### Task 8: Build and Verify

**Files:** None (verification only)

- [ ] **Step 1: Install dependencies if needed**

Run: `cd /home/ddq/AoyangSpace/OperationsPAI.github.io && bundle install`

- [ ] **Step 2: Build the site**

Run: `bundle exec jekyll build`
Expected: Build completes without errors.

- [ ] **Step 3: Verify key output files exist**

Run: `ls -la _site/index.html _site/assets/css/main.css _site/ROADMAP.html _site/CONTRIBUTING.html _site/docs/community/vision.html`
Expected: All files exist.

- [ ] **Step 4: Verify CSS is included in output**

Run: `head -20 _site/index.html`
Expected: Contains `<link rel="stylesheet" href="/assets/css/main.css">` and Google Fonts link.

- [ ] **Step 5: Verify markdown pages render with correct layout**

Run: `grep -c 'site-header' _site/ROADMAP.html && grep -c 'site-footer' _site/ROADMAP.html`
Expected: Both return `1` — header and footer are included.

- [ ] **Step 6: Start local server for visual inspection**

Run: `bundle exec jekyll serve --port 4000`
Open: `http://localhost:4000`

Verify visually:
- Homepage: hero with SVG, feature cards, timeline, CTA, quick links
- Any markdown page (e.g., /ROADMAP.html): proper heading styles, code blocks, lists, tables
- Mobile: hamburger menu works, grid collapses to single column
- Footer: three columns on desktop, stacked on mobile

- [ ] **Step 7: Final commit if any fixes needed**

```bash
git add -A
git commit -m "fix: address build verification issues"
```
