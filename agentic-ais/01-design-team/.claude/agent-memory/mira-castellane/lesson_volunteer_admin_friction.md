---
name: volunteer-admin-friction
description: Volunteer-run services fail when admin overhead exceeds volunteer capacity; minimize custom UI and decision rules
metadata:
  type: feedback
---

Volunteer systems succeed or fail on administration friction, not borrower experience.

**Why:** Borrower-facing features are nice; volunteer-facing complexity is fatal. A tool library with five beautiful reservation features but a backend that requires re-training will accumulate stale data, lose volunteer trust, and fail within months. Catalogue rot is the documented top failure mode in community tool libraries — not borrower hesitation.

**How to apply:** When designing for volunteer-operated systems:
- Default to existing low-code platforms (Airtable, Google Sheets, Typeform) rather than custom UIs, even if less pretty. A volunteer can update Airtable in 30 seconds; they may avoid custom software entirely.
- Push complexity to the borrower-facing side, not the volunteer side. Borrowers should tolerate email, simple forms, and manual confirmation; volunteers should not.
- Test every proposed admin workflow with an actual volunteer before building. What sounds reasonable to a product person takes 10 minutes; what takes a volunteer 45 minutes will be skipped.
- Catalogue rot is a leading cause of failure — minimize the friction between "tool status changed" and "system is updated." If weekly updates require re-learning software, it won't happen.
