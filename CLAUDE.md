# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio site for Joe Pillatsch, deployed to GitHub Pages at `joepillatsch.com`. Pure static HTML — no build step, no framework, no dependencies.

## Development

Open `index.html` directly in a browser. No server needed, no build step, no `npm install`.

To preview with a local server (for accurate path resolution):
```
npx serve .
```

## Architecture

Everything lives in a single file: `index.html`. All CSS is embedded in a `<style>` block in the `<head>` — there are no separate stylesheet files to maintain. Images live in `img/`.

**Layout:** Three full-viewport scroll-snap sections:
1. **Hero** — name + animated scroll hint
2. **Work & Projects** — CSS flex grid of project cards with logo + social links
3. **Contact** — personal social/contact icons + copyright

**Design system:** Dark theme (`#000` bg, `#fff` text), Inter font via Google Fonts, `clamp()` for fluid typography, opacity for visual hierarchy (0.7 → role text, 0.45 → dates, 0.35 → copyright), 0.25s opacity transitions on hover.

**Mobile breakpoint:** `max-width: 640px` — project grid switches from horizontal flex row (100px gap) to vertical column (56px gap).

## Deployment

Pushing to `master` deploys automatically via GitHub Pages. The `CNAME` file sets the custom domain to `joepillatsch.com`.
