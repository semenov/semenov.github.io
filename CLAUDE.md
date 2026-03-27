# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static landing page for **semenov.ai** — a personal/company site about autonomous AI agents. Hosted on GitHub Pages with a custom domain (CNAME: `semenov.ai`).

## Architecture

This is a **single-file site**. All HTML, CSS, and JavaScript live in `index.html` (~1150 lines). There is no build step, no bundler, no framework.

- **Lines 1–493**: `<style>` block — CSS custom properties (`--bg`, `--fg`, `--accent`, `--accent2`, `--dim`, `--mid`, `--border`), layout, responsive breakpoints at 960px and 640px
- **Lines 495–750**: HTML sections — Nav, Hero (with `<canvas>` background), Ticker, Manifesto, Architecture (terminal block), Capabilities, Stats, Services, Human+AI, Approach, Contact, Footer
- **Lines 750+**: `<script>` block — Three.js sphere animation (loaded via CDN), scroll-triggered reveals via IntersectionObserver, stat counter animation, nav scroll state, tilt effect on capability cards

Key design patterns:
- Fonts: Space Grotesk (body) + Space Mono (monospace/labels) via Google Fonts
- Color scheme: dark background (`#040404`) with green accent (`#00ffaa`) and purple accent (`#7b61ff`)
- Animations: CSS `@keyframes` for hero entrance, glitch effect, ticker scroll; JS for Three.js particle sphere
- Scroll reveal: `.reveal` class + `.vis` toggled by IntersectionObserver
- Mobile: responsive via CSS media queries, no separate mobile template

## Development

Open `index.html` in a browser. No build or install commands needed. For live reload during development, use any static file server (e.g., `python3 -m http.server`).

## Other Files

- `index_old.html` — previous version of the site (kept for reference)
- `docs/business_plan.pdf` — business plan document
- `semenov.svg` — logo asset
