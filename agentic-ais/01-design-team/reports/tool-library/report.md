The team members are fictional AI characters. Research plans are proposals: no real people were interviewed. Check everything before you use it.

---

# Neighbourhood Tool Library — Full Team Report

**Brief:** Build a simple website for a neighbourhood tool library where people can see what is available and reserve a tool. It is run by volunteers in one town.

---

# Studio Review
*Imara Vance, Studio Director*

## Verdict

The team answered the brief faithfully: a resident can browse tools, filter by category, and initiate a reservation without creating an account. However, the system as delivered is a prototype, not a live service — the reservation form sends data nowhere, which means the core promise of the brief remains undelivered.

## Three strongest decisions

1. **Anselm Okafor** identified catalogue rot as the top failure mode and recommended minimising update friction. The decision to use a single Airtable source of truth, with no custom admin dashboard, directly addresses this. Fewer places to update means fewer places to forget.

2. **Mira Castellane** drew a clean MVP line: no user accounts, no real-time updates, no waitlists. Every deferred feature would have added volunteer overhead with no proven borrower demand. This is the right call for a first deployment.

3. **Kenji Aldaine's** accessibility decisions — persistent labels, focus-visible states, colour always paired with text — are implemented correctly in Soren's build. A skip link and live region for a screen reader are specific, verifiable choices present in the code.

## Three biggest risks

1. **The confirmation message is a lie.** Soren's form fires a client-side confirmation on submit without sending data to Airtable or notifying a volunteer. A borrower will believe their reservation is logged. A volunteer will receive nothing. This is not a cosmetic gap — it is a trust-destroying silent failure mode and is the single most urgent thing to fix before anyone uses the site. Treat this as a launch blocker, not a backlog item.

2. **The catalogue is hard-coded in JavaScript.** The twelve tools are static sample data. There is no mechanism for a volunteer to add, remove, or update a tool without editing the source code. The Airtable integration is described in the product plan but entirely absent from the delivered file. Until the front-end reads from Airtable, catalogue freshness cannot be measured.

3. **Date validation is unimplemented.** A borrower can submit a start date in the past, an end date before the start date, or a reservation that overlaps an existing booking. The reservation duration and SLA remain open questions that have not been answered by the client.

## Next three steps before going live

1. **Do not share the site URL with borrowers** until the Airtable webhook is wired and a test reservation lands in the table and triggers a volunteer notification. That is the go/no-go gate.

2. **Appoint a single named volunteer as catalogue owner** before launch. This person is responsible for updating Airtable when a tool is borrowed, returned, damaged, or retired. Without a named owner, the 7-day freshness target has no one accountable for it.

3. **Agree and encode the reservation rules** before the form goes live: maximum loan duration, how far ahead a borrower can book, and what "confirmed" means in the volunteer response email. These are operational decisions the design must reflect.

---

# Research
*Anselm Okafor, Director of Research*

## What the evidence says

**Existing platforms:** Platforms like MyTurn and Lend Engine exist for tool libraries. Both separate the catalogue and reservation system from the main website, which serves as an informational hub. The trend is toward consolidated platforms, but both may be overkill for a single small-town operation.

**Reservation handling:** A practical model observed: items held for two business days before moving to next in queue. High-demand tools use a waitlist; expensive specialist tools require advance reservation with a fee to reduce no-shows.

**Small catalogue advantage:** The Library of Things Toolkit notes that "small LoTs benefit from using LoT-specific software rather than spreadsheets alone," but emphasises tracking who is borrowing and returning as the core function.

**Back-end friction:** Airtable + Google Forms can automate data entry. However, "volunteers sometimes struggle with remembering processes they don't use frequently" — automation and simplicity matter more than feature richness in the back-end.

**Usability for browsing:** Combine search (known items) with category filters (exploratory discovery). Use plain language labels, limit visible filters to high-use criteria, and show result counts.

## What we do not know

- **Catalogue rot mechanisms:** No source describes what specifically triggers rot — update friction? Volunteer turnover? Forgotten items?
- **Reservation confidence:** No source measures borrower hesitation or what conditions make borrowers trust a reservation will be kept.
- **Volunteer sustainability:** No data on training time, error rates, or satisfaction in real deployments.
- **Low-code back-end costs:** No comparison of real time and error cost of Airtable vs. purpose-built tools.

## Primary research plan

**Recruit:** 3 active volunteers from tool libraries (people who update inventory at least monthly). 1 volunteer coordinator if available.

**Method:** Semi-structured interviews focused on past behaviour.

**Interview questions:**
1. Walk me through the last time you updated the catalogue — what took the most time?
2. How often do you hear from borrowers frustrated because an item wasn't there when they came to collect it?
3. What information do you need about each tool to feel confident updating the system?
4. Tell me about the last time a reservation went wrong — what happened?
5. If you could change one thing about the way you manage the catalogue, what would it be?

---

# Product Plan
*Mira Castellane, Chief Product Strategist*

## Problem

Volunteers managing a community tool library have no way to show residents what's available or process reservations without manual email threads and phone calls, leading to out-of-date inventory and unsustainable workload.

## MVP Scope

- Public tool catalogue: searchable, filterable view with name, category, description, and current availability status
- Simple search + category filter with result count
- Reservation form: name, email, phone, tool name, requested date range — no login required
- Volunteer back-end: Google Forms responses feed into Airtable; volunteer reviews daily, confirms by email within 24 hours
- Static HTML/CSS front-end; mobile responsive

## Cut / Defer

- User accounts and logins
- Real-time availability updates
- Custom admin dashboard for volunteers
- Automated confirmation emails
- Tool images, condition logs, borrower reviews
- Waitlists or queueing
- Analytics or reporting dashboards

## Success Metrics

1. **Catalogue freshness:** Volunteer updates reflect actual tool status within 7 days of change.
2. **Reservation completion rate:** If >20% of forms go unanswered, admin burden is unsustainable.
3. **Borrower phone calls:** Reduction in "what tools do you have?" calls signals the site is working.

## Technology Recommendation

**Stack:** Airtable (catalogue + back-end) + Netlify / GitHub Pages (static HTML/CSS) + serverless webhook for form submission.

**Avoid:** Lend Engine or MyTurn (overkill), custom Node.js + database (maintenance burden), real-time booking (out of scope).

## Open Questions (resolve before launch)

1. Who owns catalogue data entry, and how is training documented?
2. What is acceptable turnaround for volunteer confirmation — 24 hours? 48?
3. How long can a tool be checked out?
4. What tool status values are needed beyond "available" and "reserved"?
5. Approved domain name and hosting budget?
6. Will one actual volunteer test the Airtable workflow before launch?

---

# Design Specification
*Kenji Aldaine, Design Director*

## Experience Principles

1. **Trust through clarity.** Show exact availability status, requested date ranges, and a clear path from search to form.
2. **Minimal friction for volunteers.** The form collects only what volunteers need. No accounts, no real-time inventory management.
3. **Mobile-first, recognition over recall.** Categories and search surface tools without requiring prior knowledge.

## Information Architecture

**Navigation:** Flat, single-level — Home → Catalogue → Tool detail (optional) → Reservation form → Confirmation.

## User Flows

**Flow A: Borrower finds and reserves a tool**
1. Land on home → click "Browse tools"
2. View catalogue grid → filter by category or search by keyword
3. Click "Reserve" on a tool card → reservation form opens
4. Enter name, email, phone, date range → submit
5. See confirmation message with volunteer contact info and next steps

**Flow B: Volunteer updates tool status** — edit Airtable record directly; site reflects on next page load.

## Screen Inventory

| Screen | Key elements |
|--------|-------------|
| Home | Hero, three-column benefit callout, CTA button, footer |
| Catalogue | Sticky search bar, category filter pills, result count, tool card grid |
| Tool detail (optional) | Name, category, description, availability badge, reserve button |
| Reservation form | Six fields: name, email, phone, tool name, start date, end date; submit button |
| Confirmation | Success icon, message, request summary, return button |

## Components

Search bar, filter pill, tool card, availability badge, date picker (native HTML5), primary button, secondary button, text input, result count.

## Design Tokens

**Colours:**
- Primary action: `#2D7F2B`
- Available badge: `#4CAF50`
- Reserved badge: `#CCCCCC` / text `#555555`
- Background: `#FFFFFF`
- Surface: `#F5F5F5`
- Text primary: `#212121`
- Text secondary: `#666666`
- Focus outline: `2px solid #0056B3`
- Error: `#D32F2F`

**Typography:** system-ui, -apple-system, sans-serif (no custom fonts). Scale: 36/24/18/16/14/12px.

**Spacing:** 8px base — xs 4px, sm 8px, md 16px, lg 24px, xl 32px, xxl 48px.

## Accessibility

WCAG 2.2 AA throughout: persistent labels on all inputs, :focus-visible outlines, colour never used alone, required fields marked with `*`, errors in summary above form linked to fields.

## Key Design Decisions

- No accounts — volunteer overhead with no borrower benefit
- Native date picker — prevents invalid dates, mobile-friendly
- Filter pills over dropdown — all categories visible at once
- Single Airtable source of truth — no sync between two systems
- No custom fonts or images — system fonts load instantly

---

# Build
*Soren Vale, Distinguished Engineer*

## Delivered

`reports/tool-library/starter/index.html` — single HTML file, embedded CSS and JS, no external dependencies.

## Features

- Hero section with "Browse Tools" CTA
- Sticky search bar + category filter pills (Hand Tools, Power Tools, Garden, Ladders & Access, Measuring & Layout, Other)
- Responsive tool card grid (2 columns mobile / 3 columns desktop at 768px+)
- Real-time filtering by keyword and category
- Reserve button pre-fills tool name in reservation form
- Reserved tools: badge shown, button reads "Not available" and is disabled
- Client-side confirmation message on form submit
- All design tokens applied as CSS custom properties
- WCAG 2.2 AA: labels with for/id, :focus-visible outlines, text paired with colour

## Design Tokens Applied

`--primary-action: #2D7F2B`, `--available-badge: #4CAF50`, `--reserved-badge: #CCCCCC`, `--focus-outline: 2px solid #0056B3`, system-ui font stack, 8px spacing base, 6px border radius.

## Three Next Steps for Production

1. Wire form submit to Airtable webhook — this is a **launch blocker**, not a backlog item.
2. Add date validation: start date ≥ today, end date > start date, errors in `aria-describedby`.
3. Replace static tool data with a live Airtable API fetch; add loading state.
