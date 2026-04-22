# Portfolio Rework Plan

Visual reference: [bchiang7/v4](https://github.com/bchiang7/v4)
Stack: Astro + Tailwind CSS v4 + TypeScript

---

## Session Log

### Session 1 — 2026-04-19
Explored the current site (vanilla HTML5, Solid State template by HTML5 UP). Evaluated two reference portfolios: RyanFitzgerald/devportfolio (Astro + Tailwind, white/minimal) and bchiang7/v4 (Gatsby + React, dark navy). Decided to adopt the **bchiang7/v4 visual design** but build in **Astro** for lower long-term maintenance overhead. Created CLAUDE.md and this plan.

**Commits:**
- `8f47470` — docs: add CLAUDE.md and redesign plan
- `5d9da38` — feat: bootstrap Astro + Tailwind CSS v4 project — Scaffolded package.json, astro.config.mjs, tsconfig.json, Layout.astro, global CSS with bchiang7/v4 design tokens (navy palette, teal accent, CSS custom properties), src/config.ts. Build verified. Phase 1 complete.

### Session 3 — 2026-04-22
Completed Phase 4 remaining item (images) and full Phase 5 polish & QA pass.
- Created `public/images/featured/` and copied `khemia.png` as the Khemia featured cover; removed cover field from Boost Mode and Stellar (confidential work, gradient placeholder renders instead).
- Phase 5: moved Google Fonts from CSS `@import` to `<link>` tags with preconnect; added skip-to-content link; added `:focus-visible` outline; added `role="img"` to photo placeholder; added full ARIA arrow-key navigation (ArrowUp/Down/Left/Right, Home, End) to Experience tablist; added `loading="lazy"` to featured image; created `public/favicon.svg`.

**Commits:**
- (pending)

### Session 2 — 2026-04-21
Resumed from Phase 2. Built all shell components: Loader (logo fade-in, removes itself after 900ms), Nav (fixed top bar with scroll-shrink, numbered links, hamburger + mobile slide-in menu), Social (side-mounted GitHub/LinkedIn icons), Email (vertical rotated email link), Footer. Wired all into Layout.astro with responsive content padding. Build verified.

Then executed Phase 3 + Phase 4 content layer in the same session. Set up Astro 5 content collections (jobs, featured, projects) with typed schemas. Wrote content entries for 1 job (ASML), 3 featured projects (Boost Mode, Stellar, Khemia), and 7 other projects. Built all six section components (Hero, About, Experience, FeaturedWork, OtherProjects, Contact) with full bchiang7/v4 layout fidelity and scroll-reveal via IntersectionObserver. Build verified.

**Commits:**
- `3dfec22` — feat: build Phase 2 shell components (Loader, Nav, Social, Email, Footer)
- `8830c98` — feat: build Phase 3 sections and Phase 4 content layer
- `b7b2f71` — fix: correct all content from CV — 4 real job roles, accurate project descriptions

---

## Tasks

### Phase 1 — Bootstrap ✓
- [x] Initialize Astro project (`npm create astro@latest`) inside the repo
- [x] Install and configure Tailwind CSS v4 (`@tailwindcss/vite`)
- [x] Set up TypeScript (`tsconfig.json`)
- [x] Configure Astro for GitHub Pages static output (`astro.config.mjs` with `output: 'static'` and correct `site` URL)
- [x] Set up design tokens: color palette, fonts, CSS custom properties (navy, teal accent, slate, mono font)

### Phase 2 — Shell & Layout ✓
- [x] Build root layout (`src/layouts/Layout.astro`): HTML shell, global styles, font imports
- [x] Build `Loader` component (fade-in intro animation, runs once on first visit)
- [x] Build `Nav` component: fixed top bar, scroll-shrink effect (100px → 70px), mobile hamburger menu
- [x] Build `Social` component: side-mounted icons on the left (GitHub, LinkedIn, email)
- [x] Build `Email` component: vertical email link on the right side
- [x] Build `Footer` component

### Phase 3 — Sections ✓
- [x] **Hero**: full-viewport, left-aligned — mono "Hi, my name is" → large name → muted subtitle → short bio → CTA button, with staggered fade-up on load
- [x] **About**: bio paragraph + skills grid + photo placeholder
- [x] **Experience**: tab navigation between roles, content driven by `src/content/jobs/`
- [x] **Featured Work**: 2–3 projects with alternating image/text layout, driven by `src/content/featured/`
- [x] **Other Projects**: 3-column card grid, driven by `src/content/projects/`
- [x] **Contact**: centered section with large heading + email CTA button

### Phase 4 — Content
- [x] Write `src/config.ts`: name, title, email, social links, nav links
- [x] Write job entries in `src/content/jobs/` (ASML internship / Boost Mode)
- [x] Write featured project entries in `src/content/featured/` (Boost Mode, Stellar, Khemia)
- [x] Write other project entries in `src/content/projects/` (nand2tetris, LearnOpenGL, Chronicles, Acrobabot, La Retirada, IoT4SafeDriving, Temperature War)
- [x] Source/optimize project images for the new layout

### Phase 5 — Polish & QA ✓
- [x] Verify ScrollReveal-style animations on all sections
- [x] Test responsive layout: mobile (hamburger, no side links), tablet, desktop
- [x] Accessibility pass: keyboard nav, focus states, aria labels
- [x] Lighthouse audit (performance, accessibility)

### Phase 6 — Cutover
- [ ] Configure GitHub Pages to serve from `dist/` output
- [ ] Verify deployment end-to-end
- [ ] Delete legacy files: `index.html`, `pages/`, `assets/`, `images/`
- [ ] Update `CLAUDE.md` to reflect final stack (remove legacy references)
