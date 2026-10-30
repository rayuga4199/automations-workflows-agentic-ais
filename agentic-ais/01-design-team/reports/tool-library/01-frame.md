# Frame — Neighbourhood Tool Library

TYPE: website
BUILD: yes
AUDIENCE: Residents of one town who occasionally need a tool and are comfortable browsing a simple web page; secondary audience is the small volunteer team who must keep the catalogue and reservations up to date without technical support.
CHALLENGE: How might we give borrowers enough confidence to make a reservation without creating an administration burden the volunteer team cannot sustain?

ASSUMPTIONS:
1. The volunteer team has no dedicated web administrator; whoever updates the catalogue will do so via a simple back-end interface or spreadsheet, not code.
2. Reservation means "I want to collect this on a specific date" — not a real-time lock requiring payment or identity verification.
3. The catalogue is small enough (assumption: under 200 items) that search and filter are useful but a full database is not strictly necessary at launch.

---

## STRATEGIC DIRECTION

The brief states the goal clearly: show availability, accept reservations. But the real design problem sits one layer down. A tool library lives or dies on whether the catalogue stays accurate and whether volunteers can respond to reservations without burning out. This is a service design problem dressed as a web build. Every front-end decision — how reservations are confirmed, how overdue items are tracked, how the catalogue is updated — creates a downstream task for a volunteer. That is the constraint that must shape the entire build.

The reversible decisions (colour, layout, copy) can move fast. The irreversible decisions — data model for items, reservation flow, how confirmations are sent — need to be made carefully because changing them later means migrating data and retraining volunteers.

Recommended approach: start with the simplest reservation mechanism that does not require custom software to administer. A low-code platform (Airtable, Notion, or equivalent) as the catalogue back-end, surfaced through a lightweight public-facing site, keeps the maintainability ceiling within reach of the volunteer team. Custom-built reservation logic should only be introduced if a simple form-and-email loop demonstrably fails at the scale this town generates.

---

## SUCCESS CRITERIA

- A first-time visitor can find whether a specific tool is available and submit a reservation in under three minutes without assistance.
- A volunteer can update an item's status (available, borrowed, reserved) in under ninety seconds without reading a manual.
- The reservation process generates no ambiguity about collection date, item identity, or who to contact — measured by zero clarification emails needed per completed loan in a pilot month.

---

## KEY RISKS

1. **Catalogue rot.** If updating availability is even slightly inconvenient, volunteers will stop doing it. The site then shows tools as available that are not, borrowers arrive and find nothing, trust collapses. This is the single highest-probability failure mode.

2. **Reservation ambiguity.** Without a confirmed, two-way acknowledgement loop — borrower notified, volunteer notified — reservations become informal promises that get missed.

3. **Scope creep.** "Simple website" almost always expands when stakeholders see the first prototype. The volunteer team's ability to maintain features should be the ceiling.

---

## IRREVERSIBLE DECISIONS

- Choice of back-end / data store. Migrating catalogue data and reservation history later is painful.
- Reservation confirmation mechanism. If borrowers expect email, any future change requires re-educating users.
- Whether the site requires user accounts. Introducing accounts after launch is a significant trust and friction change.
