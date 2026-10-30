# Studio Review — Neighbourhood Tool Library

**Reviewer:** Imara Vance, Studio Director

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
