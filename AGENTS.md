# Agent Guidelines: yogu-one (Landing Page for Yogu.one)

## Project Overview

yogu-one is the primary landing page and parent project website for the
different yogu.one applications. It serves as a central hub for users to
discover and navigate to specialized tools hosted on subdomains (e.g.,
`fukuri.yogu.one`, `enkoda.yogu.one`, `shouhizei.yogu.one`, `tokun.yogu.one`,
`konbata.yogu.one`, `musakui.yogu.one`). The project prioritizes simplicity,
performance, and accessibility.

## Tech Stack

### Core Technologies (Mandatory)

- **HTML5**: Semantic markup for a clean and accessible landing page.
- **CSS3**: Modern layout (Grid, Flexbox) and Custom Properties for a consistent
  theme across the ecosystem.
- **Vanilla JavaScript (ES6+)**: Minimal DOM manipulation for navigation and
  theme switching; no external frameworks.
- **Deno**: Used for the local development server (`serve.ts`), code formatting,
  and linting.
- **Makefile**: Task runner for common operations (`serve`, `format`, `lint`).

### Prohibited Technologies

- ❌ **React, Vue, Angular, or any JS frameworks**: Keep it framework-free and
  lightweight.
- ❌ **Tailwind CSS, Bootstrap, or heavy CSS frameworks**: Use native CSS or a
  minimal classless framework (e.g., Pico CSS).
- ❌ **TypeScript**: Use vanilla JavaScript for zero build steps and simplicity.
- ❌ **Build tools (Webpack, Vite, etc.)**: No build process is required for
  this static site.
- ❌ **HTMX**: Not suitable for this simple landing-page project.

## Core Architecture

The project follows a simple static-site structure focused on performance and
maintainability:

```text
yogu-one/
├── web/                   # Website source files
│   ├── index.html         # Main landing page (UI structure)
│   ├── css/
│   │   ├── variables.css  # Global CSS variables (colours, spacing, typography)
│   │   └── styles.css     # Layout and component styling (cards, hero section)
│   ├── js/
│   │   └── theme.js       # Dark/Light mode logic (localStorage persisted)
│   └── assets/
│       ├── yogu-one.png   # Main logo/branding
│       ├── favicon-32.png # Optimized favicon (32x32)
│       ├── apple-touch-icon.png # Apple touch icon (180x180)
│       └── apps/          # Icons/screenshots for linked applications
│           ├── fukuri.png
│           ├── enkoda.png
│           ├── shouhizei.png
│           ├── tokun.png
│           ├── konbata.png
│           └── musakui.png
├── AGENTS.md              # Project guidelines for AI agents
├── LICENSE                # GPL v3 Licence
├── Makefile               # Task automation
├── README.md              # Documentation for developers
├── apps.json              # List of ecosystem applications and URLs
└── serve.ts               # Deno development server
```

## Coding Standards

### Naming Conventions

- **HTML**: Use `kebab-case` for IDs and class names (e.g., `app-card`,
  `hero-section`).
- **JavaScript**:
  - Use `camelCase` for variables, functions, and constants (e.g.,
    `toggleTheme`, `isDarkMode`).
  - Use descriptive names that reflect purpose.
- **CSS**: Use BEM or simple semantic class naming (e.g., `card__title`,
  `nav-links`).

### General Patterns

- **British English**: Use British English spelling (e.g., `colour`,
  `optimised`, `centre`) for both code comments and user-facing text.
- **No Build Step**: Do not add build tools or transpilers. The code must run
  directly in modern browsers.
- **Clean Navigation**: Ensure links to subdomains are clear, accessible, and
  open in the same/new window as appropriate.

### Performance & Accessibility

- **Target Metrics**: Total page size < 50KB, FCP < 1.0s, TTI < 1.5s.
- **Accessibility**: Follow WCAG AA standards, ensuring high contrast, ARIA
  labels, and full keyboard navigation.
- **Manual Verification**: Test across mobile (< 768px), tablet (768px -
  1024px), and desktop (> 1024px).

## Agent Constraints

### Dos

- ✅ **Use semantic HTML5**: Always use `<header>`, `<main>`, `<section>`,
  `<footer>`, `<nav>`, etc.
- ✅ **Mobile-first CSS**: Use Grid and Flexbox for responsive app card layouts.
- ✅ **Consistency**: Ensure the design language (colours, typography) matches
  the sub-projects (`fukuri`, `enkoda`, `shouhizei`, `tokun`).
- ✅ **Progressive Enhancement**: Ensure the site is functional and readable
  even if JavaScript is disabled.

### Don'ts

- ❌ **No Frameworks**: Do not introduce any external JS or CSS frameworks.
- ❌ **No innerHTML**: Use `textContent` for any dynamic text to prevent
  potential XSS issues.
- ❌ **No npm/Node**: Avoid `package.json` or `node_modules`. Stick to Deno for
  dev tasks.
- ❌ **No Absolute Paths**: Use relative paths for all internal assets and
  scripts.

## Agent Mode-Specific Instructions

### [CODE] Mode

- **Performance**: Maintain <50KB total page weight.
- **Accessibility**: Ensure WCAG AA compliance (ARIA labels, keyboard focus).
- **Updates**: Keep `apps.json` synced with `index.html` card entries.

### [ADVANCED_CHAT] Mode

- Use for discussing the vanilla JS architecture or cross-subdomain design
  consistency.
- Reference `web/css/variables.css` for any design-related queries.

### [SETUP] Mode

- Use `Makefile` for `fmt`, `lint`, and `serve` tasks.
- Deno is the required dev environment.

## Changelog

### v1.4 (2026-05-24)

- Added optimized favicon (`favicon-32.png`) and `apple-touch-icon.png` using
  the current yogu-one app icon.
- Updated `index.html` with multiple icon sizes for better browser and device
  support.

### v1.3 (2026-05-24)

- Added `Musakui` application to landing page, `apps.json`, and `README.md`.
- Synchronised `index.html` with updated `apps.json` and corrected `lang`
  attribute to `en-GB`.
- Added `musakui.png` icon and updated architectural overview.

### v1.2 (2026-03-06)

- Added `Konbata` application to landing page and `README.md`.
- Synchronised `index.html` with updated `apps.json`.
- Added `konbata.png` icon and updated architectural overview.

### v1.1 (2026-03-05)

- Added `apps.json` and `tokun.png` to architecture.
- Included mode-specific instructions for agents.
- Synchronised sub-project list in overview.

### v1.0 (2026-03-04)

- Initial guidelines for the `yogu-one` landing page.
- Established standards based on existing `fukuri`, `enkoda`, and `shouhizei`
  projects.
- Defined tech stack (Pure HTML/CSS/JS) and architecture.

---

**Last Updated**: 2026-05-24 **Document Owner**: Project Team **Review
Frequency**: As needed based on project evolution
