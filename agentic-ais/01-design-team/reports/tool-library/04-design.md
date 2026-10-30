# Design Specification — Neighbourhood Tool Library Website

## EXPERIENCE PRINCIPLES

1. **Trust through clarity.** Show exact availability status (available / reserved), requested date ranges, and a clear path from search to form. No ambiguous states.
2. **Minimal friction for volunteers.** The form collects only what volunteers need. No accounts, no login, no real-time inventory management.
3. **Mobile-first, recognition over recall.** Categories and search surface tools without requiring prior knowledge. Form fields are optimized for phone entry.

---

## INFORMATION ARCHITECTURE

**Navigation model:** Flat, single-level. Home → Catalogue → Tool detail (optional) → Reservation form → Confirmation.

**Pages:**
- Home — hero, call-to-action, brief instructions
- Catalogue — searchable tool grid with category filters and counts
- Tool detail — full description, availability, reserve button (optional)
- Reservation form — all fields visible, no progressive disclosure
- Confirmation — success message with next steps

**Content model (Airtable):**
- Tool record: name, category, description, availability status, colour tag
- Reservation record: name, email, phone, tool ID, requested dates, timestamp

---

## USER FLOWS

**Flow A: Borrower finds and reserves a tool**
1. Land on home, read "What we lend" snippet, click "Browse tools"
2. View catalogue grid (all tools shown on first load)
3. Filter by category or search by keyword; results count updates
4. Click tool card or "Reserve" button; opens reservation form
5. Enter name, email, phone, requested date range
6. Submit form (POST to Airtable via webhook)
7. See confirmation message with volunteer contact info and next steps

**Flow B: Volunteer updates tool status (out of scope for front-end)**
- Volunteer edits Airtable record directly
- Static site reflects updated status on next page load

---

## SCREEN INVENTORY

**1. Home**
- Hero (headline + subheading), three-column benefit callout, CTA button, footer (contact, hours)
- Main action: Browse tools → catalogue

**2. Catalogue**
- Search bar (sticky), horizontal category pill filters, result count, tool card grid (2 cols mobile / 3+ desktop)
- Main action: Filter / search; click tool card

**3. Tool detail (optional panel)**
- Name, category, description, availability badge, reserve button
- Main action: Reserve button

**4. Reservation form**
- Single column, six fields: name, email, phone, tool name (read-only), start date, end date, submit button
- Main action: Submit

**5. Confirmation screen**
- Success icon, message, request summary, close/return button

---

## COMPONENT LIST

| Component | Description |
|-----------|-------------|
| Search bar | Text input with icon, clear button |
| Filter pill | Category label, active/inactive state |
| Tool card | Title, category tag, one-line description, availability badge, reserve button |
| Availability badge | "Available" (green) or "Reserved" (grey) — text always present |
| Date picker | Native HTML5 `<input type="date">` |
| Button — primary | Submit, reserve |
| Button — secondary | Close, cancel |
| Text input | text, email, tel with appropriate input types |
| Result count | "Showing X tools" |

---

## DESIGN TOKENS

### Colour Palette

| Role | Hex | Purpose |
|------|-----|---------|
| Primary action | #2D7F2B | Buttons, links, active state |
| Secondary action | #555555 | Tertiary buttons, cancel |
| Available status | #4CAF50 | "Available" badge |
| Reserved status | #CCCCCC | "Reserved" badge |
| Background | #FFFFFF | Page, cards |
| Surface dark | #F5F5F5 | Filter pills, input backgrounds |
| Text primary | #212121 | Body, headings |
| Text secondary | #666666 | Labels, helper text |
| Focus outline | #0056B3 | Keyboard focus (2px solid) |
| Error | #D32F2F | Form validation |

### Typography

| Scale | Size | Line-height | Weight | Use |
|-------|------|-------------|--------|-----|
| Hero | 36px | 1.2 | 700 | H1 home |
| Large | 24px | 1.3 | 600 | H2, page titles |
| Medium | 18px | 1.4 | 400 | Buttons, form labels |
| Body | 16px | 1.6 | 400 | Paragraphs, card descriptions |
| Small | 14px | 1.5 | 400 | Helper text, captions |
| Tiny | 12px | 1.4 | 400 | Badge labels |

Font family: system stack (no custom web fonts — performance and simplicity).

### Spacing Scale (8px base)

| Token | Size | Use |
|-------|------|-----|
| xs | 4px | Icon + text grouping |
| sm | 8px | Button padding, inline gaps |
| md | 16px | Card padding, input padding |
| lg | 24px | Section margins, form field gaps |
| xl | 32px | Page margins, major section gaps |
| xxl | 48px | Hero bottom margin |

---

## ACCESSIBILITY

- Every input has a persistent `<label>` with `for` attribute — no placeholder-only labels
- Date range fields grouped under a `<legend>` ("When do you need this tool?")
- All interactive elements keyboard-focusable with 2px #0056B3 focus outline
- Availability status is text + colour — never colour alone
- Required fields marked with `*` and mentioned in form introduction
- Form errors appear in summary above form, each linked to its field
- Meets WCAG 2.2 AA contrast on all text/background pairs

---

## KEY DESIGN DECISIONS

**No login or accounts** — volunteer overhead. Every loan already requires volunteer contact; accounts add friction without reducing it.

**Date picker, not text input** — mobile-first; prevents invalid dates; borrowers specify a range to accommodate different loan windows.

**Tool detail is optional** — if the catalogue card shows category, description, and availability, most borrowers can reserve immediately.

**Filter pills, not dropdown** — shows all categories at once, lets borrowers scan and combine without modal overhead.

**No real-time updates** — form logs a request; volunteer confirms via Airtable + email. Static HTML is always snapshot-accurate.

**Airtable over custom database** — volunteers already use spreadsheets. No custom admin UI needed.

**No custom fonts or images** — system fonts load instantly; photos increase curation effort without MVP benefit.

---

## SOURCES

- WCAG 2.2 Compliance guidelines
- Libraries of Things HCI research (ACM Digital Library)
- Accessible Form Design best practices
