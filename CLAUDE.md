# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static landing page for **Core & Calm Studio** — a community fitness studio. Built as a The Odin Project exercise using pure HTML + CSS (Flexbox only). No JavaScript. No responsive design (desktop layout only).

## Deployment

Use the `/commit` custom command to handle the full Git → GitHub → GitHub Pages deployment flow. It will prompt for a commit message, then stage/commit/push and enable GitHub Pages if not already active.

## Architecture

Single-page layout with two files:
- `index.html` — all 6 sections in order: Header, Hero, Features (4 cards), Quote, CTA, Footer
- `style.css` — all styles; single file, no preprocessor

Reference documents in `ref/` define the design constraints — consult them before making visual changes:
- `02-content.md` — all copy/text content
- `03-design-spec.md` — color system, typography sizes/weights, Flexbox layout per section

## Design Constraints

**Colors** (do not deviate):
- Dark background (Header, Hero, Footer): `#1F2937`
- Primary text on dark: `#F9FAF8`
- Secondary text / nav links: `#E5E7EB`
- Accent / buttons / CTA background: `#3882F6`
- Quote section background: `#E5E7EB`

**Typography**: Roboto via Google Fonts; hero title 48px/900, section header 36px/900, quote 36px/300 italic, logo 24px/700, body/nav 18px/400.

**Layout**: Every section uses Flexbox. Cards section uses `justify-content: space-evenly` with 4 cards. Hero and CTA are horizontal flex rows with vertical centering.

## Images

All images live in `images/`. Five files are required: `hero.jpg`, `card-strength.jpg`, `card-cardio.jpg`, `card-antiaging.jpg`, `card-coaching.jpg`. Card images use rounded borders; hero image uses `border-radius`.
