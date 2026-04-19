# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio site (b-aran.github.io). Currently a pure static HTML5 site (Solid State template by HTML5 UP), undergoing a full redesign on the `portfolio-rework` branch. See [plan.md](plan.md) for the task list and session log.

**Redesign target:** visual style of [bchiang7/v4](https://github.com/bchiang7/v4) (dark navy, teal accent, numbered sections), built in Astro + Tailwind CSS v4.

## Working Convention

**Update [plan.md](plan.md) on every commit** — mark completed tasks as `[x]` and add the commit hash + one-line description to the session log. This keeps plan.md the authoritative record of what has been done and what is next.

## Development

No build step for HTML. For CSS changes, edit SCSS source files and recompile:

```bash
sass assets/sass/main.scss assets/css/main.css
sass assets/sass/noscript.scss assets/css/noscript.css
```

Compiled CSS files are committed to the repo.

## Structure

- `index.html` — Main landing page: banner, two featured project spotlights, 8-item project grid, footer with contact
- `pages/*.html` — Individual project detail pages, each with a back link to `index.html`
- `pages/elements.html`, `pages/generic.html` — Unused HTML5 UP template references
- `assets/sass/` — SCSS source (base, components, layout, libs)
- `assets/css/` — Compiled CSS output
- `assets/js/` — Vendored jQuery + plugins, plus `main.js` for scroll/menu logic
- `images/` — Project screenshots; multi-image projects have subdirectories

## Content

Projects currently on the site:
- **Featured spotlights (2):** Boost Mode (ASML, C/C++/Python), Stellar (UE5, C++)
- **Grid (8):** Khemia (UE4/FMOD), nand2tetris, LearnOpenGL, Chronicles of Elathudel (Unity), Acrobabot (Unity), La Retirada (UE4), IoT4SafeDriving (Python/Docker), Temperature War (C#)

Contact: borja.aran.tejada@gmail.com · LinkedIn · GitHub
