# Portfolio Rework Plan

Visual reference: [bchiang7/v4](https://github.com/bchiang7/v4)
Stack: Astro + Tailwind CSS v4 + TypeScript

---

## Session Log

### Session 1 — 2026-04-19
Explored the current site (vanilla HTML5, Solid State template by HTML5 UP). Evaluated two reference portfolios: RyanFitzgerald/devportfolio (Astro + Tailwind, white/minimal) and bchiang7/v4 (Gatsby + React, dark navy). Decided to adopt the **bchiang7/v4 visual design** but build in **Astro** for lower long-term maintenance overhead. Created CLAUDE.md and this plan.

---

## Tasks

### Phase 1 — Bootstrap
- [ ] Initialize Astro project (`npm create astro@latest`) inside the repo
- [ ] Install and configure Tailwind CSS v4 (`@tailwindcss/vite`)
- [ ] Set up TypeScript (`tsconfig.json`)
- [ ] Configure Astro for GitHub Pages static output (`astro.config.mjs` with `output: 'static'` and correct `site` URL)
- [ ] Set up design tokens: color palette, fonts, CSS custom properties (navy, teal accent, slate, mono font)

### Phase 2 — Shell & Layout
- [ ] Build root layout (`src/layouts/Layout.astro`): HTML shell, global styles, font imports
- [ ] Build `Loader` component (fade-in intro animation, runs once on first visit)
- [ ] Build `Nav` component: fixed top bar, scroll-shrink effect (100px → 70px), mobile hamburger menu
- [ ] Build `Social` component: side-mounted icons on the left (GitHub, LinkedIn, email)
- [ ] Build `Email` component: vertical email link on the right side
- [ ] Build `Footer` component

### Phase 3 — Sections
- [ ] **Hero**: full-viewport, left-aligned — mono "Hi, my name is" → large name → muted subtitle → short bio → CTA button, with staggered fade-up on load
- [ ] **About**: bio paragraph + skills grid + photo
- [ ] **Experience**: tab navigation between roles, content driven by `src/content/jobs/`
- [ ] **Featured Work**: 2–3 projects with alternating image/text layout, driven by `src/content/featured/`
- [ ] **Other Projects**: 3-column card grid, driven by `src/content/projects/`
- [ ] **Contact**: centered section with large heading + email CTA button

### Phase 4 — Content
- [ ] Write `src/config.ts`: name, title, email, social links, nav links
- [ ] Write job entries in `src/content/jobs/` (ASML internship / Boost Mode)
- [ ] Write featured project entries in `src/content/featured/` (Boost Mode, Stellar, Khemia)
- [ ] Write other project entries in `src/content/projects/` (nand2tetris, LearnOpenGL, Chronicles, Acrobabot, La Retirada, IoT4SafeDriving, Temperature War)
- [ ] Source/optimize project images for the new layout

### Phase 5 — Polish & QA
- [ ] Verify ScrollReveal-style animations on all sections
- [ ] Test responsive layout: mobile (hamburger, no side links), tablet, desktop
- [ ] Accessibility pass: keyboard nav, focus states, aria labels
- [ ] Lighthouse audit (performance, accessibility)

### Phase 6 — Cutover
- [ ] Configure GitHub Pages to serve from `dist/` output
- [ ] Verify deployment end-to-end
- [ ] Delete legacy files: `index.html`, `pages/`, `assets/`, `images/`
- [ ] Update `CLAUDE.md` to reflect final stack (remove legacy references)
