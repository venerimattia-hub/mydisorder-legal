# CLAUDE.md

## Project Overview

**mydisorder-legal** is a static HTML website hosting the legal documentation (Privacy Policy and Terms of Service) for the **MyDisorder** iOS app — a bipolar disorder self-monitoring application developed by Mattia Veneri.

The companion iOS app (not in this repository) tracks mood, sleep, medications, and health metrics, syncs via iCloud/CloudKit, and optionally uses Anthropic Claude AI for premium insights.

## Repository Structure

```
mydisorder-legal/
├── CLAUDE.md        # This file — AI assistant guide
├── README.md        # Project title
├── index.html       # Landing page with app description and links
├── privacy.html     # Privacy Policy (bilingual: Italian / English)
└── terms.html       # Terms of Service (bilingual: Italian / English)
```

## Tech Stack

- **Pure static HTML + CSS** — no JavaScript, no build tools, no dependencies
- No `package.json`, no bundler, no framework
- Designed for static hosting (e.g., GitHub Pages)

## Key Conventions

### Language & Content

- All legal pages are **bilingual** (Italian first, then English), separated by a visual divider
- Primary language attribute is `it` (`<html lang="it">`)
- Navigation anchors (`#italiano` / `#english`) allow jumping between language sections

### Styling

- Inline `<style>` blocks in each HTML file (no external CSS)
- Apple-inspired design system: `-apple-system` font stack, `#f5f5f7` background, `#0071e3` link color
- Shared design patterns across pages: `.container`, `section` cards with `border-radius: 16px`, consistent typography
- `index.html` uses a centered single-column layout (max-width 520px)
- Legal pages use a wider layout (max-width 720px) with card-based sections

### Contact & Legal

- Developer: Mattia Veneri
- Contact: venerimattia@gmail.com
- Copyright: 2026
- Governing law: Italian law / Italian Consumer Code
- Last updated date for legal docs: March 29, 2026

## Development Workflow

1. **No build step** — edit HTML files directly
2. **No tests** — manual visual review in a browser
3. **No CI/CD** — deploy by pushing to the hosting branch
4. **No linting** — maintain consistency with existing formatting manually

### When Editing Legal Pages

- Always update **both** Italian and English sections to keep them in sync
- Update the "Last updated" date in the `<header>` when content changes
- Preserve the existing HTML structure: `<section>` blocks with `<h3>` numbered headings
- Keep the `<hr class="divider">` separator between language versions
- Maintain the `warning-box` class for important medical/legal disclaimers (terms.html)

## App Context (for reference)

The MyDisorder iOS app described in these legal documents:

- **Data storage**: Local device + Apple CloudKit (user's private iCloud)
- **HealthKit**: Read-only access (steps, sleep, heart rate, HRV, weight, respiratory rate, O2 saturation)
- **AI features (Premium)**: Aggregated anonymized data sent to Anthropic Claude via Cloudflare Workers proxy
- **On-device AI**: Apple Foundation Models (iOS 26+), no external transmission
- **Subscriptions**: Free tier + Premium (monthly EUR 4.99 / annual EUR 24.99) via Apple StoreKit 2
- **Privacy stance**: No ads, no trackers, no third-party analytics SDKs, GDPR compliant
