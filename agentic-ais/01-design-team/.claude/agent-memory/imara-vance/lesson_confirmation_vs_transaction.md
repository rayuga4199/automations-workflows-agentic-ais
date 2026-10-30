---
name: lesson-confirmation-vs-transaction
description: A UI confirmation message is not evidence that data was saved — distinguish front-end feedback from a real back-end transaction in design reviews.
metadata:
  type: feedback
---

A confirmation screen that fires on form submit without a real back-end call creates a false sense of completeness. The borrower believes the reservation is logged; the volunteer never receives it. This is a silent failure mode that erodes trust faster than a visible error would.

**Why:** In the tool library build, Soren delivered a working UI with a client-side confirmation that pre-empts Airtable wiring. The design looks done; the system is not. Reviewers must distinguish "the interface behaves correctly" from "the data pipeline exists."

**How to apply:** In any review where a form or submission flow is shown, explicitly check whether the submission actually reaches a data store or notification channel. If it does not, flag it as a live risk, not a styling note. A confirmation that lies to the user is worse than no confirmation.

See also: [[lesson-volunteer-ops-constraint]]
