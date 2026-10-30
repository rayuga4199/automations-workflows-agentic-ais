# Service Design Brief: Community Library Smartphone Literacy Programme

**Framed by:** Dr. Imara Vance, Studio Director
**Date:** 2026-10-30
**TYPE:** Service
**BUILD:** No. The brief asks for service design artefacts only — service blueprint, journey map, volunteer onboarding flow, session structure, and touchpoint mapping. No software, application, or coded interface is required at any stage.

---

## 1. Core Problem

Older adults who want to use smartphones are caught between a product designed for people who already know how to use it and a support ecosystem — family, retail, call centres — that assumes a baseline of digital literacy they do not yet have. The real design problem is not teaching smartphone features. It is designing a service that lowers the emotional stakes of not knowing, sustains consistent support over multiple sessions, and survives the natural turnover of volunteer tutors without collapsing.

**How Might We** design a community-run learning service that lets older adults build genuine smartphone confidence without depending on the continued presence of any single volunteer or staff member?

---

## 2. Primary Users

**Who:** Adults aged 65 and over with little or no prior smartphone experience, attending sessions at a community library.

**Key characteristics:**

- Motivation is specific and personal: keeping in touch with family, using health apps, navigating independently. Rarely abstract curiosity about technology.
- High anxiety about public failure. Being seen to struggle in front of others is a significant deterrent to return attendance.
- Prior negative experience with technology support is common: retail staff who speak too fast, family members who take over the device rather than explain.
- Cognitive and physical variation is wide within this group: vision, fine motor control, hearing, and working memory differ substantially. The service must not assume a uniform capability profile.
- Trust is earned slowly. A single session that feels humiliating or confusing outweighs several positive ones.
- Goals are narrow and concrete: calling a grandchild on video, reading a text message, booking a GP appointment. The design must centre on these goals, not a curriculum of features.

**Assumption A1:** The majority of attendees will be self-referred or referred by family, not by a healthcare or social care pathway. This affects the tone of communications but not the session structure.

---

## 3. Secondary Users

**Who:** Volunteer tutors — likely retired adults, students on placement, or community volunteers with personal interest in digital inclusion. Managed loosely by a library coordinator.

**Key characteristics:**

- Variable technical knowledge. Some will be confident smartphone users; others will have modest skills and compensate with patience. The service cannot assume deep technical expertise.
- No formal teaching training in most cases. Session scripts and structured guides are not optional extras; they are the mechanism by which the service functions at all.
- Subject to churn. Volunteers leave without warning. Any knowledge or relationship held only in a volunteer's head is lost when they go.
- Their own confidence is load-bearing. Volunteers who feel unprepared will disengage silently rather than ask for help. Under-preparedness is the primary cause of volunteer drop-out in programmes of this type — not time constraints. (Assumption A2: based on pattern observed in comparable community services. Requires validation with this library's specific volunteer base.)
- They need explicit permission structures: what to do when they do not know the answer, how to handle distress, when to escalate to the library coordinator.

**Also secondary:** The library coordinator, who sets the schedule, manages room bookings, communicates with both groups, and holds institutional continuity. This person is the single point of failure for the whole service if their role is not designed for succession.

---

## 4. Key Constraints

**Volunteer ceiling (binding):** The service can only be as complex as a rotating volunteer team can operate without dedicated technical support. Every artefact — session guide, onboarding pack, booking confirmation — must be maintainable by a non-specialist. This is not a preference; it is a structural limit.

**Physical environment:** Community library spaces are shared, noisy, and not purpose-built for one-to-one coaching. Sessions likely occur at tables, with background noise. Audio and visual environment cannot be controlled.

**Device heterogeneity:** Participants will arrive with different smartphones — Android and iOS, different manufacturers, different operating system versions. The session structure must work across device types rather than assuming a single platform.

**No dedicated budget assumed:** The brief does not state a budget. Assumption A3: this is a low or zero-budget programme run within existing library resources, with no paid design, technology, or content production budget post-launch. All materials must be producible in standard office tools (word processor, simple graphics).

**Accessibility floor:** Primary users include people with reduced vision, hearing, and dexterity. Every touchpoint must be designed to this floor, not as an accessibility afterthought.

**Data and privacy:** If any participant data is recorded — attendance, progress, contact details — it must comply with applicable data protection requirements. The brief does not name a jurisdiction; assume UK GDPR as the most likely context given library services. This is not a code constraint; it is a data handling and consent design constraint.

---

## 5. Success Metrics

These are proposed metrics, not confirmed measurements. Real baselines require research with this specific library and its community.

| Metric | What it measures | How to observe |
|---|---|---|
| Session two attendance rate | Whether first-session experience was positive enough to return | Register comparison, weeks 1 vs. 2 |
| Learner-stated goal achievement | Whether participants accomplish their specific goal | End-of-programme self-report card |
| Volunteer retention at 3 months | Whether tutors feel prepared and supported | Coordinator log of volunteer tenure |
| Time to first unassisted task completion | Whether learners reach independence, not just supervised competence | Tutor observation note in session log |
| Coordinator burden per session cycle | Whether the service is genuinely sustainable | Time-log kept by coordinator for 4 weeks |

**What success is not:** Number of sessions delivered, number of devices set up, or number of participants registered. These are activity metrics, not outcome metrics.

---

## 6. Design Principles

**1. Confidence before features.**
Every session is designed around what the learner wants to do, not a syllabus of things they should know. A participant who leaves having successfully video-called their daughter has had a better session than one who completed a checklist of six features they have no immediate use for.

**2. No single point of failure.**
The service must function if any one volunteer does not show up, if the coordinator is on leave, or if the library changes its room allocation. Knowledge lives in materials, not in people.

**3. Distinguish the first session from all others.**
Session one is a distinct artefact. Its primary purpose is not instruction; it is establishing that this is a safe place to not know things. A learner who leaves session one feeling capable — however small the task accomplished — is far more likely to return than one who was given accurate but overwhelming information.

**4. Design for the volunteer's confidence as well as the learner's.**
Tutors who feel equipped stay. Tutors who feel exposed leave. Every volunteer-facing artefact must address the fear of not knowing the answer: scripts, fallback language, escalation routes.

**5. Legibility over completeness.**
A session guide that a volunteer reads in full is more valuable than a comprehensive manual no one opens. Ruthlessly edit all materials to the minimum a tutor needs to run a safe and useful session.

**6. Reversible before irreversible.**
Session structure, communication language, and printed materials are reversible — iterate them quickly from coordinator and tutor feedback. The volunteer onboarding flow and the service blueprint are higher-stakes and harder to change once the programme is running; invest more scrutiny there before first use.

---

## 7. Risks and Flags

**Risk 1 — Volunteer attrition collapses the service (High likelihood, High impact)**
If the onboarding flow does not build genuine tutor confidence, volunteers disengage within two to three months. The service blueprint must include an explicit volunteer retention loop, not just an initial recruitment and training step. Flag for the client: who owns volunteer welfare, and is that role resourced?

**Risk 2 — Session one drop-out before the programme demonstrates value (High likelihood, High impact)**
The emotional experience of session one is the single strongest predictor of continued attendance in community learning programmes. A generic "week one of the curriculum" approach will lose a proportion of participants before the service has had a chance to work. Session one must be designed as a separate, higher-priority artefact against emotional safety criteria.

**Risk 3 — Device variation makes session guides ambiguous (Medium likelihood, Medium impact)**
If guides are written for one device or operating system, tutors will face constant deviation from the script in real sessions. This erodes tutor confidence rapidly. Session materials must either be platform-agnostic or provide explicit branching notes for iOS vs. Android.

**Risk 4 — Library coordinator as single point of failure (Medium likelihood, High impact)**
If the coordinator holds all programme knowledge in their head — volunteer contacts, room bookings, participant records — the service collapses when they are absent. The service blueprint must make coordinator handover a designed step, not an emergency procedure.

**Risk 5 — Participant data handled informally (Lower likelihood if flagged early, High impact if not)**
Attendance registers and progress notes constitute personal data. If collected without a clear retention and deletion policy, the library risks a data protection breach. This needs a decision before the programme launches, not after.

**Flag for client:** The brief does not state how participants are recruited, how sessions are booked, or whether there is a waiting list. The booking and confirmation touchpoint is undefined. A no-show rate without a reminder mechanism will waste volunteer time. A simple SMS or phone reminder step should be assumed until evidence shows it is not needed.

---

## 8. Recommended Deliverable Sequence (and Why)

**Step 1 — User journey map (primary learner)**
Start here because every other deliverable is downstream of understanding what the learner actually experiences. This is also the artefact most likely to surface assumptions that need early challenge.

**Step 2 — Service blueprint**
Once the learner journey is defined, map the supporting layer: what the volunteer does, what the coordinator does, what materials exist at each stage, and where failures can occur.

**Step 3 — Volunteer onboarding flow**
Designed third because it must be coherent with the session structure it prepares volunteers to run, and the service blueprint reveals what volunteers actually need to know.

**Step 4 — Session structure**
Follows once the blueprint confirms what resources, materials, and time are available at session stage.

**Step 5 — Key touchpoints**
A synthesis artefact: consolidates the moments of highest risk and highest value identified across all four preceding deliverables.

---

## 9. BUILD

**BUILD: no.** All deliverables are service design artefacts. No code is required.

---

*Framed by Dr. Imara Vance. Assumptions are labelled A1–A3 and flagged inline. Nothing in this document is claimed as evidence; all figures and patterns are stated as assumptions requiring validation with real participants and coordinators from this specific programme.*
