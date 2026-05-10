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

- `src/pages/` — file-based routing; each `.astro` file becomes a URL route. `index.astro` is the landing page.
- `src/layouts/Layout.astro` — html shell used by every page: `<head>` with SEO meta + JSON-LD, Plausible analytics, sticky header, footer, and a `<slot />` for page content.
- `src/components/` — reusable pieces with logic or shared markup (e.g. `Share.astro` for the copy-link / QR / Web Share UI and its script).
- `src/styles/global.css` — Tailwind + DaisyUI imports, applied globally.
- `public/` — static assets served as-is (no processing).

**Component conventions:**

- Page content lives inline in the page file. Don't split static sections (hero, problem, etc.) into components just to shorten a file — it makes the page harder to scan.
- Promote markup to a component in `src/components/` only when it (a) is reused across pages, (b) contains a `<script>` or non-trivial logic, or (c) is genuinely long and self-contained.
- Anything that should appear on every page (meta tags, header, footer, analytics) belongs in `Layout.astro`.

**Styling:**

All styling should use Tailwind utility classes and DaisyUI components where possible. Avoid custom CSS unless Tailwind/DaisyUI cannot achieve the result.
