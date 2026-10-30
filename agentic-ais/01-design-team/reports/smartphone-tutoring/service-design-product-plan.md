# Product Plan: Community Library Digital Skills Service

## Executive Summary

This service design project delivers five interrelated artefacts to operate a volunteer-led smartphone training programme for older adults (65+) in community libraries. The core challenge is not feature design but operational resilience: sustaining engagement through volunteer turnover, managing session efficacy under physical constraints, and designing confidence-building workflows that reduce emotional barriers to learning.

The plan prioritises delivery of a distinct, emotionally safe first session architecture; volunteer onboarding flows that reduce one-and-done attrition; and a coordinator toolkit that prevents single points of failure. Deliverables are grounded in evidence from Age UK's Digital Champion Programme, AbilityNet's one-to-one model, and international research on volunteer-integrated services. No digital product is built; all artefacts are operational and instructional.

---

## 1. What We Are Building (and What We Are Not)

### Deliverable 1: Service Blueprint

**Definition:** A systems diagram showing all actors (learner, tutor, coordinator, library), touchpoints (phone booking, SMS reminder, in-library signage, session materials), and data flows (attendance tracking, feedback loops, progression records).

**Why it matters:** The brief names volunteer turnover (39% annually) as a known risk. A service blueprint makes invisible failure modes visible: what happens when a tutor drops out mid-learner journey? Where does knowledge live? Who contacts the learner? A blueprint forces explicit answers before the service runs.

**Minimum viable version:** One diagram covering: learner entry → session one → session two+ → progression or dropout. Actors in swim lanes. Touchpoints marked. One failure path (tutor churn) explicitly resolved.

**What to cut:** Do not include aspirational elements like automated SMS or learner app tracking. Focus on what the coordinator can actually operate: phone calls, printed handouts, volunteer scheduling spreadsheets. No system integrations. No GDPR consent flows at this stage (see Open Decisions, below).

---

### Deliverable 2: User Journey Map

**Definition:** Narrative journey for the primary learner persona (high anxiety, concrete goal like "video call with grandchild" or "NHS appointment booking") through discovery, enrolment, first session, and three follow-up sessions.

**Why it matters:** Research shows dropout peaks between session one and two. A journey map identifies the emotional inflection points: the moment a learner feels unheard (when they're told "we'll start with email"), the moment they succeed ("I texted my daughter"), the moment a tutor absence threatens confidence. Mapping these moments guides the session structure design (Deliverable 4) and the volunteer training (Deliverable 3).

**Minimum viable version:** Four moments across four sessions. For each: what the learner wants (concrete), what anxieties are present (implicit), what the tutor must do (explicit), what success feels like (observable).

**What to cut:** Do not create separate journey maps for secondary personas (volunteer tutors, coordinator). One primary user journey is load-bearing; secondary personas get workflows instead (Deliverables 3 and 5). Do not include aspirational "ideal path" scenarios; focus on the likeliest path and the most common failure mode (session-one cognitive overload).

---

### Deliverable 3: Volunteer Onboarding Flow

**Definition:** A documented workflow covering tutor recruitment, matching with learners, training, session preparation, session execution, feedback, and retention touchpoints.

**Why it matters:** Research shows volunteer attrition is 39% and "one-and-done" mentality is a key driver. The Digital Champion Programme (Age UK) found that training + continuous support significantly reduced churn. A scripted onboarding flow ensures every tutor has the same entry experience, knows what to expect, has clear success criteria for session one, and receives structured touchpoints (check-in after session one, feedback before session two) that sustain engagement.

**Minimum viable version:** Five sections: (1) recruitment message (phone/email/volunteer fair), (2) intake questionnaire (what skills do you have? are you patient?), (3) one-session training (learner psychology, session structure, common problems, emergency escalation), (4) session prep checklist (device type, learner goal, materials), (5) post-session debrief (quick feedback form, recognition, next scheduling).

**What to cut:** Do not build a tutor vetting process. Do not create a test or certification scheme. Do not require background checks (unless coordinator legal advice demands it; not in scope here). Do not create a competency framework. Accept that tutors will be highly variable. The design must work with volunteers as they are, not train them to a standard they'll never meet.

---

### Deliverable 4: Session Structure (First Session and Follow-Up Template)

**Definition:** A scripted, time-boxed session design for Session One (approx. 3 hours, goal-focused, confidence-centric) and a repeatable template for Sessions Two onwards (1.5–2 hours, skill-progressive, problem-focused).

**Why it matters:** Research from effective programmes shows first sessions are structurally distinct: longer, slower, emotionally safe, concrete goal-driven, and designed to deliver a small, visible win. This is not the same as follow-on sessions. The brief identified this as a core design principle: "session one is a distinct artefact." Session One failure (tutor talks too fast, learner feels patronised, goal is unclear) directly predicts dropout before Session Two.

**Minimum viable version:** Session One: (1) welcome and goal clarification (15 min), (2) device setup and safety (45 min, hands-on), (3) first task (video call or SMS, learner-driven, tutor mirrors), (4) reflection and planning (15 min). Session Two+: (1) recap of last session and review of home practice (20 min), (2) one new task (tutor-led demo, then learner-led practice), (3) independent practice (learner alone, tutor available), (4) plan next steps (5 min).

**What to cut:** Do not design for classroom delivery to multiple learners. Sessions are one-to-one (or tutor + coordinator facilitating a pair). Do not create progression curricula (email → browsing → apps → messaging → payments). The learner's goal drives the curriculum, not a pre-set sequence. Do not include accessibility adaptations for each session (see Constraint and Deliverable 5). Do not mandate specific devices or operating systems; the session template must work for iPhone, Android, low-literacy, shaking hands, hearing loss—see Open Decisions, below.

---

### Deliverable 5: Key Touchpoints and Coordinator Toolkit

**Definition:** Documented, repeatable protocols for five critical interaction points outside scheduled sessions: pre-session booking confirmation, session reminder, post-session follow-up, learner absence handling, and tutor feedback loops.

**Why it matters:** Research emphasises that booking and reminder touchpoints (phone, SMS, printed invitation) significantly affect attendance. The coordinator is often a single point of failure (brief names this as a constraint). A toolkit of simple, low-tech protocols—phone call scripts, printed postcard templates, SMS reminder wording, absence follow-up decision tree—distributes this load and ensures consistency even if the coordinator changes.

**Minimum viable version:** Five one-page protocols: (1) booking confirmation (phone call, what to say, write the goal and date on a printed postcard, send same day); (2) reminder (phone call or SMS, 48 hours before, confirm the learner still wants to attend); (3) post-session note (thank you card, mention the win, preview next session); (4) absence (phone call within 48 hours, non-judgmental, ask what got in the way, reschedule); (5) tutor feedback (5-question form, tutor completes in 5 minutes, feeds into retention decision).

**What to cut:** Do not create a CRM or database system. Do not automate these touchpoints. Do not mandate specific tools (Whatsapp, SMS, phone). Accept that the coordinator may track learner data in a spreadsheet or on paper. Design for low-literacy coordinator input and high legibility output. Do not require data entry for every learner interaction. Do not build a learner app or tutor app; all communication is human-to-human with printed or spoken backup.

---

## 2. Build Order and Rationale

| Order | Deliverable | Dependency | Why This Position |
|-------|-------------|------------|-------------------|
| 1 | Service Blueprint | None | Maps the system before operations design. Reveals failure modes (tutor churn, coordinator overload) that shape the next four artefacts. Cannot skip. |
| 2 | User Journey Map (Learner) | Service Blueprint (actors and touchpoints identified) | Grounds all downstream design in learner psychology and emotional progression. Session structure and tutor training must follow this journey, not precede it. |
| 3 | Volunteer Onboarding Flow | User Journey Map (learner needs are known) + Service Blueprint (tutor actor identified) | Tutors must understand the learner journey to deliver it. Onboarding flow is informed by session-one requirements (from journey map) and failure recovery (from blueprint). |
| 4 | Session Structure | Volunteer Onboarding Flow (tutor capabilities and training are known) + User Journey Map (learner emotional progression is mapped) | Session design is the execution core: it materialises the journey and uses the tutor's training. Cannot be designed in isolation. Informs what tutors must know (flows back to #3 for refinement). |
| 5 | Key Touchpoints and Coordinator Toolkit | All prior four | Coordinator protocols bind the other four artefacts: they pre-emptively remind (keeping learners in the journey), manage absences (journey interruption), and feedback tutors (sustainable onboarding). Last because it's integrative, not foundational. |

---

## 3. The Must-Nail Moment

### The Single Highest-Leverage Design Decision: Session One is Emotionally Safe, Goal-Driven, and Structurally Distinct

**What it is:** The design of the first session—its opening words, pacing, device handling, tutor posture, success definition, and closing ritual—is the single highest-leverage design decision in this service. Everything downstream depends on it.

**Why this one:** Research identifies dropout peaking between Session One and Two. The brief highlights "lower emotional stakes of not knowing" as a core problem: older adults learning digital skills are often anxious, sometimes ashamed, sometimes angry at technology. Session One is the moment when a tutor either builds emotional safety (learner feels heard, not rushed, not stupid) or erodes it (tutor assumes knowledge, goes too fast, pivots to tutor's agenda, uses jargon). Emotional safety in Session One predicts return. Failure at Session One is operationally expensive: lost learner, time sunk, volunteer confidence shaken, coordinator has to re-recruit.

**What failure looks like:**
- Tutor begins with "Let's start with the basics" (learner feels patronised, disengages).
- Tutor demonstrates email, learner watches passively (learner doesn't hold the device, doesn't move).
- Learner hasn't texted anyone by end of session (session happened to the learner, not for the learner; learner has no proof of progress).
- Learner leaves with no written confirmation of next session or tutor contact (learner feels abandoned; absence of next session is indistinguishable from service withdrawal).

The session structure (Deliverable 4) must be designed around this moment. The tutor training (Deliverable 3) must rehearse this moment. The journey map (Deliverable 2) must highlight the emotional vulnerabilities this moment must address. The service blueprint (Deliverable 1) must show what happens if Session One fails and how the coordinator recovers.

---

## 4. Hard Cuts

### Cut 1: No Learner Assessment or Progress Tracking System

The brief mentions "wide physical/cognitive variation" and "no single point of failure," yet a tempting design error is to create a progress tracker: levels (Bronze, Silver, Gold), pre-tests, post-tests, skill checklists. This is wrong for two reasons.

**First, operationally:** A progress tracking system requires the coordinator (already a single point of failure) or each tutor to maintain accurate data. Learners with low confidence may feel surveilled or judged by tests. Inconsistent data entry (one tutor logs videos watched, another doesn't) creates garbage that misleads the coordinator. Tracking becomes busywork that displaces the actual work: building confidence and drilling concrete skills.

**Second, psychologically:** Older adults learning digital skills often have prior negative school experiences. Assessment language (passing, failing, levels) retriggered that anxiety. The service is designed to build confidence, not assign grades. Progress is visible and felt by the learner (you video-called your daughter), not captured in a system. Trust that if Session One worked, the learner will show up to Session Two.

**What we do instead:** Tutors complete a 5-question post-session form (part of Deliverable 5): "Did the learner achieve their goal?" (yes/no), "How confident did they seem at the end?" (observed, not tested), "What will we do next session?" (next step, not level). The coordinator uses these forms to spot learners who missed their goal (check-in call) and tutors who are struggling (offer peer matching or end the pairing). No scoring, no levels, no learner-facing assessment.

---

### Cut 2: No App or Digital Tracking Platform

The brief permits "zero/low budget," and research shows that Age UK's successful Digital Champion Programme operated with phone calls and paper records. Resist the impulse to build a learner app (booking, progress, message the tutor), a tutor app (confirm availability, log hours), or a coordinator dashboard (see all learners in one place).

**Why this cut matters:** An app requires device compatibility support (iOS vs Android, OS versions, permissions), creates a second technical barrier for anxious learners (they're already struggling with smartphones; asking them to install an app adds friction), requires ongoing maintenance and security updates, and makes the service dependent on a third party (app store changes, payment processing, server uptime). A missing app update can silently break the service for learners mid-programme.

**What we do instead:** The coordinator maintains a simple spreadsheet or paper ledger: learner name, phone number, goal, tutor assigned, session dates, notes. The tutor texts or calls the learner 48 hours before a session. The learner confirms by phone call to the coordinator or tutor. No app. No data silo. Everything is human-readable and human-operable.

---

### Cut 3: No Formal Volunteer Competency Framework or Certification

The brief states "variable skill, no teaching training" as a given for volunteers. A plausible design error is to create a tutor certification: complete a 2-day training, pass a teaching skills assessment, get a badge. This over-formalises the role and excludes the volunteers most likely to succeed.

**Why this cut matters:** Older adult volunteers (who, research shows, have lower dropout rates than younger cohorts) often resist formal training. Framing tutoring as a taught skill requiring certification creates barrier to entry. Moreover, the best tutors for older learners are not professional educators; they're patient, tech-competent people who remember what it felt like to not understand something. A 2-day formal training selected for teaching technique, not empathy.

**What we do instead:** One 2–3 hour in-person training session covering: (1) how older learners think (psychology, not pedagogy), (2) the session structure they'll use (walkthrough), (3) the learner's goal (why it matters, how to keep focus on it), (4) common pitfalls and how to recover, (5) who to call if things go wrong (coordinator escalation). No test. No grading. Simple takeaway materials (one-page tutor checklists for each session type). Tutors learn by doing.

---

### Cut 4: No Device-Specific Curriculum or Hardware Loan Programme

The brief mentions "device heterogeneity (iOS + Android)" as a constraint, and research shows AbilityNet's successful model offers one-to-one training that adapts to the learner's device. A tempting design is to loan devices (library has 20 iPads, learners borrow them for sessions and home practice) or create separate curricula (iOS pathway, Android pathway, web pathway).

**Why this cut matters:** Device lending creates inventory management (tracking loans, device resets, damage), liability (learner damages device), and false equivalence (a loaned iPad is not the learner's phone; muscle memory and confidence don't transfer). Separate curricula doubles design and tutor training work, and forces learners into a device bin (you're Android; go with Android tutor). The principle is: tutors work with learners' own devices, no exceptions.

**What we do instead:** Tutors are trained to work with any device the learner brings. Session One includes 15 minutes of "device orientation" (where are settings? how do you unlock this? what's that button?). The session structure is device-agnostic: "We're going to send a text message" works identically on iPhone and Android; the buttons are in different places, but the task is the same. Tutors carry printed visual guides (iOS screenshots, Android screenshots, side by side) for common tasks.

---

### Cut 5: No Accessibility Adaptation per Learner or Session-Specific Accommodations Workflow

The brief identifies "accessibility floor" as a constraint and notes "wide physical/cognitive variation." A design temptation is to create an accessibility intake (hearing loss? poor eyesight? tremor?) and adaptive materials (large-print handouts, audio instructions, simplified language variants). While well-intentioned, this creates coordinator burden and stigmatises learners (filling in an accessibility form feels like special education).

**Why this cut matters:** Individual accommodation requests create a matrix of versions (large-print + audio, large-print + simplified, etc.) that the coordinator tracks and tutors prepare. One missing variant creates frustration. Tutors don't know which accommodation their learner needs until session day. Better to build universally legible materials that work for everyone: large text by default (20pt minimum, high contrast), short sentences, plain language, printed materials plus verbal walkthrough, hands-on practice (not lecture), clear buttons and short labels on screen, no jargon.

**What we do instead:** All materials (printed handouts, session plans, tutor checklists) are designed for high legibility by default: large type, high contrast, simple layout. Session One includes tutor asking "What helps you learn best? Do you prefer I show you, or we do it together? Do you like to take notes?" The tutor adapts in the moment, not from a pre-filled form. Accessibility is built in, not bolted on.

---

## 5. Open Decisions for the Design Director (Kenji Aldaine)

### Decision 1: Learner Data Storage and GDPR Compliance Model

**The question:** How does the coordinator store learner data (name, phone, goal, session notes) while meeting UK GDPR obligations? Specifically: where is the data stored (paper, spreadsheet, cloud service)? Who has access? When is it deleted? What happens if a learner drops out?

**Option A: Paper ledger + coordinator's laptop (no cloud)**
- **Upside:** No third-party data controller. Data stays physical (library). Coordinator has full control. No subscription costs. Simple.
- **Downside:** If coordinator leaves, data leaves (single point of failure). No backup if fire. Hard to report on numbers of learners served (useful for funding). Requires explicit GDPR documentation for anyone handling the paper (includes volunteers).
- **Tradeoff:** Maximises data minimalism, minimises tech burden, but creates organisational risk.

**Option B: Shared spreadsheet (Excel, Google Sheets, OneDrive) with explicit access control**
- **Upside:** Data is backed up automatically. Multiple people can access it (reduces single point of failure if coordinator sick). Easy to count learners and measure programme reach. Searchable.
- **Downside:** Cloud service (Microsoft, Google) is a third-party data processor; library must have a Data Processing Agreement (DPA) in place. Requires training for all users (tutors, coordinator) on not sharing login credentials. Requires a deletion protocol: when learner data is removed, old versions are still in cloud backup for 30 days.
- **Tradeoff:** Adds operational resilience (backup, multi-user access) but introduces compliance overhead (DPA, training, deletion audits).

**Option C: Standalone database or CRM tool (Airtable, Zoho, Pipedrive)**
- **Upside:** Purpose-built for data management. Role-based access (tutor sees only their learner; coordinator sees all). Built-in reporting. Can generate reports for funding applications.
- **Downside:** Subscription cost (library budget constraint). Requires vendor security audit (does vendor meet library's data protection standards?). Tutor and coordinator training required. If vendor goes down or charges prices up, library is locked in.
- **Tradeoff:** Maximises features and audit trails, but creates cost and vendor dependency.

**Recommendation for Kenji:** Start with Option B (shared spreadsheet + DPA). It's pragmatic: costs nothing, works today, and data remains in the UK (library's OneDrive or Google Workspace account). Require the library to sign a one-page DPA with the cloud provider (template exists; it's boilerplate). Train all users on the deletion protocol (data deleted after learner completes or drops out; deleted rows are purged when the coordinator does a quarterly clean). If the programme grows (100+ learners), revisit Option C. Do not start with Option C.

---

### Decision 2: Volunteer Matching Model (Trained Pool vs. Ad Hoc Tutor-Learner Pairing)

**The question:** Does the library maintain a roster of trained tutors, match learners to tutors, and sustain the pairing across multiple sessions? Or does each learner get whoever volunteers show up on the day they book?

**Option A: Trained roster with fixed pairings**
- **Upside:** Learner sees the same tutor across sessions (builds relationship, trust, continuity). Tutor knows the learner's goal progression (session one to three is a journey). Easier to onboard tutors (train once, use repeatedly). Tutor feels accountable.
- **Downside:** Volunteer absence (tutor gets sick, takes holiday) forces coordinator to find a substitute or reschedule learner. Building a roster requires identifying, training, and retaining 4–8 tutors per library (high recruitment bar). One tutor dropout can strand learners mid-journey.
- **Tradeoff:** Maximises continuity and relationship, but requires higher volunteer commitment and recruitment effort.

**Option B: Ad hoc pool; match on first available tutor**
- **Upside:** Flexible. Learner books a session; whoever volunteers that day is available. Easy to scale: add more tutors to the pool as demand increases. No learner stranded if one tutor quits. Low tutor commitment barrier (show up when you can).
- **Downside:** Learner meets different tutor each session (no continuity; has to re-explain goal). Tutor doesn't know learner's progress (session two tutor doesn't know what session one covered). Knowledge lives in learner's head, not in handover notes. Learner feels less invested if tutor changes. Harder to train: tutors trained once, never reinforced, one-and-done attrition likely.
- **Tradeoff:** Maximises tutor flexibility, minimises retention risk, but sacrifices continuity and learner experience.

**Option C: Hybrid—fixed primary tutor + trained backup**
- **Upside:** Learner has one assigned tutor for continuity. If assigned tutor unavailable, a trained backup covers (learner sees same backup twice, consistency). Reduces single tutor dependency. Builds a small roster (2–3 tutors per learner cohort) without scaling to 8.
- **Downside:** Requires explicit handover protocol between primary and backup (session notes, learner's goal, home practice feedback). More admin for coordinator to track. Backup tutor must be trained to the same standard as primary.
- **Tradeoff:** Balanced approach; requires clear documentation (Deliverable 5) and discipline.

**Recommendation for Kenji:** Implement Option C (fixed primary + trained backup). It's robust: learner gets continuity but service survives tutor absence. Handover is simple (one-page session note that backup reads before arriving). The backup arrangement also gives tutors a peer relationship (primary tutor and backup coordinate, reducing isolation). Document the handover protocol in Deliverable 5 as a specific touchpoint.

---

### Decision 3: Session Venue and Noise/Privacy Management

**The question:** All sessions happen in the library's shared space (noisy, public, interruptions) or is a quiet room reserved? What if no quiet room is available?

**Option A: Dedicated quiet room for every session**
- **Upside:** No background noise (learner hears instructions clearly). Privacy (older adults sometimes feel embarrassed learning tech; closed door reduces peer observation). Tutor can use speaker or earbuds for video call demo without disturbing others. Consistent environment across learners.
- **Downside:** Requires library to reserve a meeting room per session (may not be available, especially busy libraries). Learner may feel isolated or under surveillance in a closed room. Coordinator must manage a room booking system (another point of failure). If room not available, session is postponed (disrupts learner momentum).
- **Tradeoff:** Maximises privacy and acoustics, but creates scheduling complexity and learner isolation risk.

**Option B: Open library space, but structured session "pod" (designated table, printed signage)**
- **Upside:** No room reservation needed. Session is visible (library staff and other users can see there's a learning event; normalises digital learning). Learner is in the public space where they'd normally use the library (familiarity). Low coordination overhead.
- **Downside:** Background noise (group study, children's area, printing). If learner is on a video call, others hear the caller. Other users may interrupt (ask questions, sit down). Tutor and learner may feel exposed. Hard to focus on details (small text, quiet instructions).
- **Tradeoff:** Maximises operational simplicity, but sacrifices learner focus and emotional safety.

**Option C: Hybrid—Book a quiet room if available; otherwise, use a designated library area with noise-dampening protocol**
- **Upside:** Preferred: quiet room. Fallback: in-library space with tutor and learner agreeing on a non-disruptive area (corner table, away from printers), tutor speaking clearly, learner holding device at eye level so others don't see the screen. Flexibility.
- **Downside:** Requires tutor and learner to collaborate on managing a less-than-ideal space. Requires a fallback plan (what do tutors do to focus a learner if there's noise?).
- **Tradeoff:** Balanced; acknowledges library reality (no dedicated rooms) while still optimising when possible.

**Recommendation for Kenji:** Implement Option C (book quiet room if available; fallback to designated area with protocol). Document the fallback protocol in Deliverable 5: tutor talks at normal volume (not loud, not whispered; clear), learner chooses whether to use speaker for video calls or earbuds, session materials are printed (not on-screen only, to reduce glare and light-reading difficulty), first 5 minutes of session is a focus ritual (tutor and learner agree to put phones away except the learning device, check time for next appointment). The fallback is not ideal, but it's explicit and prepared for, not improvised.

---

### Decision 4: Tutor Recruitment and "One-and-Done" Attrition Prevention

**The question:** How does the library identify and recruit volunteer tutors? And what distinguishes a tutor who returns for multiple sessions vs. one who tutors once and disappears (the 39% attrition risk)?

**Option A: Recruit from existing library volunteers + local tech companies (corporate volunteer days)**
- **Upside:** Library volunteers are already trained in library systems and values. Tech company employees have strong device skills. Both groups may have time (retirees volunteer regularly; companies allocate paid volunteer time). Low barrier to get people in the door.
- **Downside:** Existing library volunteers may not be tech-confident. Tech company volunteers are transactional (one day, corporate requirement, then gone). Neither group has chosen to commit to ongoing tutor role. High one-and-done risk.
- **Tradeoff:** Easy recruitment, but weak retention.

**Option B: Recruit specifically for long-term commitment; emphasise "ongoing role" in messaging**
- **Upside:** Self-selects for tutors who want to tutor (not just comply with employer requirement). Messaging is explicit: "We're looking for tutors who commit to 6+ learners over 6 months." Attracts people drawn to sustained mentoring.
- **Downside:** Smaller recruitment pool (not everyone wants to commit). Takes longer to build roster. Requires explicit commitment conversation (increases friction for casual interest).
- **Tradeoff:** Smaller pool, but higher retention likelihood and stronger tutor-learner relationships.

**Option C: Recruit flexibly; build retention through structured touchpoints (post-session feedback, peer community, recognition)**
- **Upside:** Low entry barrier (show up when you can). Retention is designed in, not recruited in. Even tutors with light availability (one session per month) are valuable. Post-session feedback and recognition rituals (thank-you card, peer celebration) reward tutor contribution. Peer community (tutors know each other, share problems) reduces isolation and one-and-done impulse.
- **Downside:** Requires deliberate retention design (Deliverable 5 must include tutor feedback and recognition touchpoints). Doesn't guarantee ongoing commitment; tutors may still fade. Coordinator must actively reach out to tutors between sessions (more coordinator load).
- **Tradeoff:** Maximises accessibility and volunteer autonomy, but requires ongoing relationship tending.

**Recommendation for Kenji:** Implement Option C (flexible recruitment + structured retention). The research is clear: 39% attrition is not solved by recruitment messaging; it's solved by making tutors feel part of a supported community. Design into Deliverable 5 a tutor feedback loop (post-session form that tutor completes, coordinator reads it and sends a thank-you note or a "we matched you with another learner!" message within 48 hours). A tutor who gets positive feedback after Session One is far more likely to return than one who tutors once and hears nothing. Create a tutor email list or WhatsApp group so tutors can ask peers for advice ("How do I explain WiFi?"). Celebrate wins: "This week, 5 learners sent their first text message; thanks to you." Small recognition, sustained contact, peer community—these prevent one-and-done.

---

### Decision 5: Session Location Accessibility (Accessibility of the Library Building and Transport)

**The question:** How do we ensure learners with mobility issues, visual impairments, or hearing loss can physically attend sessions? Is this a library problem or a programme design problem?

**Option A: Design assumes the library is accessible (lever, accessible parking, disabled toilet, lift); out-of-scope for this project**
- **Upside:** Focuses design effort on the service (sessions, tutoring) not the building. Library accessibility is already mandated by building regulations (Equality Act 2010).
- **Downside:** If the library is not accessible, learners are excluded before they even arrive. Tutor cannot overcome a flight of stairs. No recourse in the service design.
- **Tradeoff:** Shifts responsibility to library management; service design assumes the foundation is sound.

**Option B: Conduct an accessibility audit of the library (parking, entry, corridors, toilets, room access) and include findings and recommendations in Deliverable 1 (Service Blueprint)**
- **Upside:** Surface the issue explicitly. If library is not accessible, it's documented. Library can decide whether to improve the building or offer alternative arrangements (home visits, video sessions). Service design is informed by building reality, not assumption.
- **Downside:** Adds scope (building audit is outside service design). May uncover expensive findings (no accessible parking; learners with mobility issues cannot attend). Creates tension between service ambition and building constraint.
- **Tradeoff:** Honest assessment of barriers; increases scope and potential conflict.

**Option C: Design transport and in-home backup options into the service**
- **Upside:** Maximises reach. If learner cannot get to library (mobility, transport anxiety, no driver's license), offer home visits (tutor visits learner) or video sessions (tutor and learner on video call, learner at home, tutor in library). Learner choice: attend in-person or remote.
- **Downside:** Home visits require tutor vetting (safeguarding, DBS check) and additional training (working in a home vs. library). Video sessions require learner to have internet access, a camera-enabled device, and enough confidence to use video (not always present for anxious learners). Coordinator must match learner to delivery mode (another decision point).
- **Tradeoff:** Maximises inclusion, but adds complexity and safeguarding overhead.

**Recommendation for Kenji:** Implement Option B + C hybrid. Include in Deliverable 1 (Service Blueprint) a brief accessibility audit: check the library's disability access (parking, entry, accessible toilet, quiet space availability). If accessible, assume learners arrive in-person. If not accessible (common in older UK libraries), document this. Then design transport support into Deliverable 5: provide tutor with public transport links and cost (learner can ask library or tutor for help getting there), and offer an alternative delivery mode for learners who cannot travel (home visit by tutor, or video session if learner has internet). Require home-visit tutors to do a 30-minute safeguarding briefing (how to take notes without making learner feel surveilled, what boundaries to maintain). This balances service ambition with practical constraint.

---

## 6. Success Signals

Success signals are observable behaviours that tell us the service is working. They are not targets (invented numbers), but behavioural evidence.

### Signal 1: Learner Returns After Session One

**Observable behaviour:** A learner who completes Session One shows up for Session Two (or calls the coordinator to reschedule, not disappears).

**Why this matters:** Dropout between Session One and Two is the single biggest risk the service faces. If Session One fails emotionally (tutor talks at learner, learner feels stupid, or learner's goal is unclear), learner doesn't return—and this service has failed its core function. If learner returns to Session Two without prompting (no desperate coordinator calls), it means Session One worked: emotional safety was real, goal was clear, learner had a small win (sent a text, made a call). This signals service efficacy at the hardest moment.

**How we'll know:** Attendance tracking (Deliverable 5 coordinator toolkit includes a simple log: Session One attendance, Session Two attendance, did learner show up or cancel?). Target: no invented number. Signal: if 60%+ of Session One learners also attend Session Two, service design is working. If fewer than 40%, Session One design has failed; design must be reworked.

---

### Signal 2: Tutor Completes at Least Two Sessions with the Same Learner

**Observable behaviour:** A tutor is matched with a learner for Session One, and the tutor shows up again for Session Two with the same learner (or explicitly asks to continue with a different learner, indicating they want to tutor at all).

**Why this matters:** Research identifies "one-and-done" tutors (39% annual attrition) as a key failure mode. If a tutor attends one session and never returns or never volunteers again, the service is consuming tutors without sustaining them. If a tutor completes two sessions with the same learner, it signals: (1) the tutor felt capable and supported (not abandoned after Session One), (2) the learner benefited enough that tutor wants to continue the relationship, or (3) tutor understands continuity matters (same learner is better than different learner each week). Any of these is a signal that tutor retention design (onboarding, feedback, recognition, peer community) is working.

**How we'll know:** Tutor attendance log (part of Deliverable 5 toolkit) tracks tutor name, learner name, session number. A tutor who appears twice with the same learner (or explicitly opts into a different learner) signals retention. No invented target. Signal: if fewer than 50% of tutors complete two sessions with any learner, tutor retention design has failed; onboarding or support touchpoints need rework.

---

### Signal 3: Learner Achieves Their Stated Goal (Concrete, Observable)

**Observable behaviour:** A learner states a goal in Session One (e.g., "I want to video call my granddaughter," "I want to book a GP appointment online," "I want to text my son"), and by Session Three or Four, the tutor observes the learner doing this goal independently (learner demonstrates the task, or learner reports they have done it at home).

**Why this matters:** The service exists to serve concrete learner goals, not to teach "digital skills" in the abstract. If a learner shows up but never achieves their goal, the service has failed—attendance is just activity, not outcome. If a learner independently executes their stated goal (video calls daughter without tutor present, or books an appointment without calling the tutor for help), it signals: (1) service transferred knowledge and confidence from tutor to learner, (2) learner is no longer anxious about this task (confidence is visible in independent action), (3) learner will likely use this skill at home (behaviour change is durable).

**How we'll know:** Post-session tutor feedback form (Deliverable 5) includes a simple question: "Did the learner achieve their goal today or make progress toward it?" (yes/no). By Session Three, coordinator reviews feedback: if learner has achieved goal, note it (learner has a win; tutor knows it). If learner has not achieved goal by Session Three, coordinator calls learner (check-in: what's in the way?) and tutor (extra support?). No invented target. Signal: if 70%+ of learners achieve their stated goal within four sessions, service design is working. If fewer than 50% achieve goals, either goal-setting in Session One is unclear, or session structure is not supporting transfer to independent practice.

---

## Implementation Notes

This plan assumes the following:

1. **Library has a coordinator** (paid staff, single person or job-shared) who owns the service, books sessions, recruits tutors, maintains records, and escalates problems. The service design assumes this person exists and is supported; it does not create a system that works without one.

2. **Library has a quiet or semi-quiet space** available, booked per session. If not available, the fallback protocol (Deliverable 5, Decision 3) applies.

3. **Library does not have existing digital skills programming** that this service must integrate with. If it does, service design should align with existing library policies (GDPR, volunteer vetting, booking systems).

4. **Volunteer tutors are recruited locally** (via word of mouth, volunteer centres, employer networks, community boards). The service design does not create a recruitment campaign; coordinator handles recruitment as part of their role, supported by Deliverable 3 (onboarding flow) to make retention easier.

5. **Learners contact the library by phone or in-person** to book sessions. No online booking, no app, no website form (acknowledges that many older learners lack confidence with online booking).

6. **All documentation is printed** (not PDF-only) and available in large type, high contrast, plain language. Digital versions are available but not required.

7. **Success is measured by observation and simple tracking**, not complex data analysis. Coordinator logs attendance, feedback, and goal achievement on a spreadsheet; no analytics platform needed.

---

## Deliverable Dependencies and Timeline Assumptions

Assuming Kenji (Design Director) has full-time availability:

- **Weeks 1–2:** Service Blueprint (Deliverable 1). Workshop with library coordinator, volunteer sample, learner interviews (if available). Output: systems diagram, actor flows, failure mode recovery paths.

- **Weeks 2–3:** User Journey Map (Deliverable 2). Synthesise from research, blueprint, and learner interviews (if conducted). Output: 4–5 journey moments, emotional inflection points, tutor actions per moment.

- **Weeks 3–4:** Volunteer Onboarding Flow (Deliverable 3) and Session Structure (Deliverable 4) in parallel. Both feed from journey map. Output: one full 3-hour Session One script with tutor narration, learner checklist, printed materials. Onboarding flow with 5 clear stages (recruit → train → match → execute → debrief).

- **Weeks 4–5:** Key Touchpoints and Coordinator Toolkit (Deliverable 5). Integrate the prior four. Output: five one-page coordinator protocols (booking, reminder, post-session, absence, tutor feedback).

- **Week 5:** Review, refinement, and decisions (Kenji resolves the five open design decisions). Minor iterations.

Total timeline: **5–6 weeks** for all five deliverables in draft + refined form.

---

## What Happens After Delivery

This plan specifies design outputs (blueprints, journeys, scripts, protocols), not implementation. After delivery:

1. **Library coordinator trains** with the onboarding flow and session structure. Coordinator rehearses recruiting tutors, running Session One, handling an absence. Issues and fixes are fed back to design (one revision round expected).

2. **First cohort of tutors and learners** pilot the service. Expected: 4–8 tutors, 8–12 learners over 12 weeks.

3. **Coordinator logs attendance, feedback, and learner goal achievement** (Deliverable 5 toolkit). By week 12, review success signals (Learner return rate, tutor repeat rate, goal achievement). Expected: one or more signals will highlight a design gap (e.g., Session One is too long, or tutor feedback form is too tedious to complete).

4. **Minor iteration on the design** based on pilot feedback. Revise the session structure, onboarding, or protocols if needed. Do not redesign from scratch.

5. **Scale or sustain:** If pilot is successful, expand to a second cohort with the same design. Coordinator stays in role and recruits more tutors. No new design is needed unless the library context changes (e.g., library closure, new coordinator, shift to remote delivery).

---

## Conclusion

This product plan is built around one core insight: **the service's success or failure is determined by Session One and tutor retention, not by feature scope or technology**. Every deliverable is designed to support these two moments. The service blueprint makes failure modes visible so they can be designed out. The user journey identifies the emotional vulnerabilities Session One must address. The tutor onboarding ensures every tutor has the knowledge and confidence to deliver Session One safely. The session structure is the detailed script for that moment. The coordinator toolkit ensures that the service survives tutor absence, learner anxiety, and forgetfulness. Nothing is aspirational; everything is operationally achievable by a coordinator, four to eight tutors, and a quiet corner of a library.

Success is not measured by user engagement metrics, app retention, or learning level completions. Success is measured by observable behaviour: learners return after Session One, tutors return after Session One, learners independently achieve their goals. These three signals tell us the service is working.
