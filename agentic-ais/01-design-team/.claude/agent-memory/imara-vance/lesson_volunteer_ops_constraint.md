---
name: lesson-volunteer-ops-constraint
description: For volunteer-run services, the maintainability ceiling of the team is a design constraint as binding as any user need — scope the technical solution to it first.
metadata:
  type: feedback
---

When a service is run by volunteers with no dedicated technical resource, the real design problem is often not the user-facing interface but the back-office burden. A reservation system that works beautifully at launch but collapses under volunteer churn is a failed design. Always ask: who updates this when the founder leaves? Frame the data layer (spreadsheet, off-the-shelf tool, headless CMS) as an explicit design decision, not an implementation detail.

**Why:** Volunteer-run projects routinely fail not from lack of users but from maintenance abandonment. The ops constraint is as real as any stated user need.

**How to apply:** In any brief involving volunteers, community groups, or small charities, surface the maintainability question at framing stage and carry it through to delivery.
