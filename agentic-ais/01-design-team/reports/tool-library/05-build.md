# Build — Starter Site

**Developer:** Soren Vale
**Output:** `reports/tool-library/starter/index.html`

## What was built

A complete single-file HTML starter for the neighbourhood tool library website.

**Stack:** Single HTML file — embedded CSS and JS, no external dependencies, no CDN.

**What it does:**
- One-page site with hero section, sticky search + category filter pills, responsive 2–3 column tool card grid
- Real-time filtering by keyword search and category pill
- Reserve buttons pre-fill the tool name in the reservation form below
- Reserved tools show the availability badge; their button reads "Not available" and is disabled
- Client-side form confirmation message (no page reload)
- All 12 sample tools hard-coded in JS
- WCAG 2.2 AA accessible: labels with for/id pairing, :focus-visible outlines, text always paired with colour

## Design tokens applied

All tokens from the design specification are implemented as CSS custom properties:
`--primary-action: #2D7F2B`, `--available-badge: #4CAF50`, `--reserved-badge: #CCCCCC`, `--focus-outline: 2px solid #0056B3`, system-ui font stack, 8px spacing base, 6px border radius.

## Three next steps for production

1. Wire form submit to a back-end endpoint (save to Airtable, send email to admin and borrower).
2. Add date validation: start date ≥ today, end date > start date, errors in `aria-describedby` containers.
3. Replace native date inputs with a calendar picker library for mobile and cross-browser consistency.

## Sources consulted

- Form Accessibility — Labels, Errors & Focus States (2026 Compliance Guide)
- A guide to designing accessible, WCAG-conformant focus indicators (Sara Soueidan)
