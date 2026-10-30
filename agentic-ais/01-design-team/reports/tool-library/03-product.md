# Product Plan — Town Tool Library Website

## PROBLEM
Volunteers managing a community tool library have no way to show residents what's available or process reservations without manual email threads and phone calls, leading to out-of-date inventory and unsustainable workload.

## TARGET USER
**Primary:** Volunteer librarian (curator and reservation processor). Secondarily, borrower searching for and requesting a specific tool.

## MVP SCOPE

- **Public tool catalogue:** searchable, filterable view of all available tools with title, category, brief description, and current availability status (available / reserved).
- **Simple search + filter:** by keyword and category. Show result count.
- **Reservation form:** borrower enters name, email, phone, tool name, requested date range. No login required.
- **Volunteer back-end:** Google Forms responses feed into Airtable or shared spreadsheet; volunteer reviews daily, sends confirmation or denial via email within 24 hours.
- **Static site:** HTML/CSS front-end with zero database custom logic; catalogue pulled from Airtable API once per deploy or refresh.
- **Mobile responsive:** works on phone browsers.

## CUT / DEFER

- User accounts and logins — no borrower accounts; status communicated by email only
- Real-time availability updates — catalogue reflects state at last volunteer update
- Custom admin dashboard for volunteers — use native Airtable UI
- Automated confirmation emails — volunteer sends manually
- Tool images, condition logs, or borrower reviews — text description only
- Multi-branch support — one physical location
- Waitlists or queueing
- Analytics or reporting dashboards

## SUCCESS METRICS

1. **Catalogue freshness:** Volunteer updates reflect actual tool status within 7 days of change.
2. **Reservation completion rate:** Ratio of submitted forms to confirmed reservations. If >20% go unanswered, admin burden is unsustainable.
3. **Borrower site visits vs. phone calls:** Reduction in "what tools do you have?" calls signals the site is working.

## TECHNOLOGY RECOMMENDATION

**Stack:** Airtable (catalogue + form back-end) + Netlify / GitHub Pages (static HTML/CSS site) + serverless function or n8n webhook for form submission.

**Why:**
- Airtable: volunteers can update tool records directly without touching code. Familiar spreadsheet UX.
- Static HTML/CSS: no server to manage, no auth layer to break, fast deploys.
- Google Forms → Airtable webhook: accessible from phones, familiar to everyone, shareable with new volunteers.
- Serverless function: captures form submission, posts to Airtable, sends borrower a confirmation email. No rate-limiting or session management needed.

**Avoid:** Lend Engine or MyTurn (overkill for one small town), custom Node.js + database (maintenance burden shifts to you), real-time booking (explicitly out of scope).

## OPEN QUESTIONS (resolve before launch)

1. **Catalogue governance:** Who owns data entry? How is training documented so new volunteers can take over?
2. **Response SLA:** What is acceptable turnaround for volunteer confirmation? 24 hours? 48?
3. **Reservation duration:** How long can a tool be checked out?
4. **Tool status values:** Beyond "available" and "reserved," do you need "broken," "missing," "in maintenance"?
5. **URL and hosting:** Approved domain? Budget for Netlify or free GitHub Pages?
6. **Pilot volunteer:** Will one actual volunteer test the Airtable workflow before launch?
