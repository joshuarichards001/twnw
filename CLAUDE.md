# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # start dev server at localhost:4321
npm run build    # build production site to ./dist/
npm run preview  # preview the production build locally
```

## Architecture

Astro static site for "Tax Wealth Not Work" — a New Zealand-focused political/advocacy website. Domain: twnw.nz

**Stack:** Astro 6 · Tailwind CSS 4 · DaisyUI 5 · TypeScript (strict)

**Key paths:**

- `src/pages/index.astro` — main landing page (file-based routing; each `.astro` file in `src/pages/` becomes a URL route)
- `src/styles/global.css` — Tailwind + DaisyUI imports, applied globally
- `public/` — static assets served as-is (no processing)

All styling should use Tailwind utility classes and DaisyUI components where possible. Avoid custom CSS unless Tailwind/DaisyUI cannot achieve the result.
