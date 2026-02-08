# CLAUDE.md

## Project Overview

CCS (Cardiovascular Clinical Sciences) — a demo/concept website for a real cardiovascular CRO based in Boston. Single-page site designed to demonstrate what a redesigned ccstrials.com could look like. Not a live production site.

## Tech Stack

- **Static HTML** — no build tools, no bundler, no package manager
- **Tailwind CSS v3** via CDN (`cdn.tailwindcss.com`) with inline config
- **Vanilla JavaScript** — no frameworks
- **Google Fonts** — Cormorant Garamond (display) + Source Sans 3 (body)
- Deploy anywhere as static files (no build step)

## File Structure

- `index.html` — Complete single-page site (~1,436 lines, self-contained)
- `CLAUDE.md` — This file

## Design Direction

**"World-class cardiology practice"** — warm, confident, trustworthy. NOT a tech startup, NOT a design showcase. The buyer is a 55-year-old VP of Clinical Development evaluating a $20M cardiovascular program.

### Palette
- **Navy**: `#1a2744` (primary, hero bg, dark sections)
- **Navy light**: `#243352` (radial gradient centers)
- **Warm white**: `#f8f6f3` (light section backgrounds)
- **CCS Red**: `#c41230` (CTAs only, used sparingly)
- **Gold**: `#b8953e` (accents, numbers, decorative elements)
- **Gold light**: `#d4b85a` (gradient endpoints)
- **Warm gray**: `#4a5568` (body text)

### Typography
- **Display**: Cormorant Garamond 600/700 — academic serif for headings
- **Body**: Source Sans 3 400/600 — humanist sans for readability

## Architecture

Single self-contained HTML file with all CSS and JS inline.

**Section order:** Nav → Hero (navy, full-bleed) → Stats → Leadership (editorial layout) → Problem We Solve (navy, clip-path diagonal) → Three Commitments → Services (accordion/expandable) → Core Lab Spotlight (navy, sonar animation) → Data Timeline → Global Reach (bar chart) → Quality → Contact Form → Footer

**Section IDs:** `stats`, `leadership`, `about`, `services`, `corelab`, `contact`

## Key Design Decisions

- **Hero is navy, not white** — creates immediate visual impact vs generic AI-generated white page
- **Leadership uses editorial magazine layout** — large monograms with pull quotes, NOT card grid
- **Services use accordion/expandable rows** — click to reveal descriptions, NOT card grid
- **Global Reach uses bar chart visualization** — proportional gold bars, NOT identical white cards
- **5 distinct scroll animations** — reveal-up, reveal-left, reveal-right, reveal-scale, reveal-blur (varied, not uniform)
- **SVG noise grain overlay** at 1.8% opacity for texture across entire page
- **Diagonal clip-path cuts** on navy sections for visual tension
- **No glassmorphism, cursor glow, particles, aurora, or showcase effects** — restraint IS the design
- **Stats numbers are oversized** (text-7xl) with "SINCE 1997" watermark behind them
- **Commitment numbers** (01, 02, 03) are 120px watermarks behind text, not inside card boxes
- **Form inputs use bottom-border-only style** — no full border boxes

## Copy Source

All copy strategy comes from `/Users/sanman/Documents/cro-website/ccs.md` — comprehensive copy and design strategy document covering:
- Company facts from ccstrials.com
- Current site problems analysis
- Copy strategy (prospect-first, specific over superlative)
- Theme1 copy learnings applied to CCS
- Konstam & Udelson credentials (SOLVD PI, HFSA founder, Braunwald's chapter author, flurpiridaz trials)
- QMS, Core Lab PET reads, Data Management, DBL importance
- Five Unchallengeable Claims framework

## CCS Company Facts

- **Full name**: Cardiovascular Clinical Sciences
- **Founded**: 1997 by Marvin Konstam, M.D. and James Udelson, M.D.
- **HQ**: 75 Kneeland St, Suite 702, Boston, MA 02111
- **Phone**: (617) 423-7999 | info@ccstrials.com
- **Model**: ARO + CRO hybrid (academic thought leadership + commercial execution)
- **Network**: 2,500+ specialized CV research sites across 16 countries
- **Range**: Phase I single-center to 5,000-patient pivotal trials

## Production Gaps

### Must-have (can't launch without)
1. **Real photography** — SVG monograms must be replaced with professional headshots of Konstam, Udelson, Rusch, Patel. Warm-lit, documentary style, not corporate blue-tint stock.
2. **Working contact form** — Currently fakes submit with `setTimeout`. Needs real backend (Formspree, Netlify Forms, or serverless function).
3. **Verified metrics** — 94% team continuity and 0 CRLs are plausible placeholders. Must be substantiated by CCS before launch. Made-up specificity is worse than no specificity.
4. **Content sign-off** — Every credential listed for Konstam and Udelson needs their approval. One wrong fellowship or overstated role destroys credibility.
5. **Favicon + Open Graph meta** — No icon, no social preview image. URL shares show nothing.

### Should-have (professional standard)
6. **SEO** — Schema.org markup (MedicalOrganization), sitemap.xml, robots.txt. Has good `<title>` and meta description but nothing structured.
7. **Analytics** — No tracking. Needs GA4 or Plausible + conversion tracking on form submit.
8. **Privacy policy / legal** — No cookie notice, privacy policy, or terms. Required in most jurisdictions.
9. **Accessibility audit** — Has aria on mobile nav but missing: skip-to-content link, focus management on accordion, heading hierarchy check, color contrast verification on gray-on-navy text.
10. **Production CSS** — Tailwind CDN loads entire framework (~300KB). Production should use built/purged CSS. Acceptable for now since it's cached.

### Nice-to-have (phase 2)
11. **Additional pages** — ccs.md strategy calls for 6 pages: Clinical Research Services detail, Core Lab detail, About/Why CCS, Investigators recruitment, dedicated Contact. Single page covers the story but deeper pages help SEO.
12. **Investigator recruitment form** — ccstrials.com has one. Site networks are a business function.
13. **News/publications section** — Konstam and Udelson publish constantly. Curated publication list reinforces credibility.
14. **Custom domain + hosting** — Needs to live somewhere (Vercel, Netlify, or basic hosting).

## What NOT to Do

- Don't add dark-mode showcase effects (cursor glow, particles, aurora)
- Don't replace accordion services with card grids
- Don't use generic white cards with rounded corners + hover lift
- Don't make all scroll animations the same translateY fade-in
- Don't use uniform section patterns (heading + subheading + grid)
- Don't add stock photography or clip-art icons
