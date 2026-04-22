# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio site (b-aran.github.io). Built with **Astro + Tailwind CSS v4 + TypeScript**, visual style based on [bchiang7/v4](https://github.com/bchiang7/v4) (dark navy, teal accent, numbered sections). Deployed via GitHub Actions to GitHub Pages.

## Working Convention

**Update [plan.md](plan.md) on every commit** — mark completed tasks as `[x]` and add the commit hash + one-line description to the session log.

## Development

```bash
npm run dev    # local dev server
npm run build  # production build to dist/
```

Deployment is automatic: pushing to `main` triggers the GitHub Actions workflow (`.github/workflows/deploy.yml`), which builds and deploys to GitHub Pages.

## Structure

- `src/pages/index.astro` — Single-page site entry point
- `src/layouts/Layout.astro` — HTML shell, global imports, IntersectionObserver for scroll-reveal
- `src/components/` — Shell components: `Loader`, `Nav`, `Social`, `Email`, `Footer`
- `src/components/sections/` — Page sections: `Hero`, `About`, `Experience`, `FeaturedWork`, `OtherProjects`, `Contact`
- `src/content/jobs/` — Job entries (Astro content collection)
- `src/content/featured/` — Featured project entries (Astro content collection)
- `src/content/projects/` — Other project card entries (Astro content collection)
- `src/styles/global.css` — Design tokens (CSS custom properties), base resets, scroll-reveal styles
- `src/config.ts` — Site metadata: name, email, nav links, social links
- `public/` — Static assets served as-is (favicon, images)

## Content

- **Featured (3):** Boost Mode @ ASML (C++), Game Systems @ Stellar Entertainment (UE5/C++), Khemia (UE4/FMOD)
- **Other projects (7):** nand2tetris, LearnOpenGL, Chronicles of Elathudel, Acrobabot, La Retirada, IoT4SafeDriving, Temperature War

Contact: borja.aran.tejada@gmail.com · LinkedIn · GitHub
