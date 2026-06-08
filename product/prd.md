# Product Requirements Document
## Hospital Queue Management Platform

**Author:** Karani Njoroge
**Date:** June 2026
**Version:** 1.0
**Status:** Draft

---

## 1. Problem Statement

Public outpatient departments in Kenyan hospitals operate on manual, first-come-first-served physical queues. Patients wait 3–6 hours with no visibility into their position or expected wait time. Between 15–30% abandon care before being seen. Clinical staff spend 1–2 hours daily managing queue logistics instead of delivering clinical care.

The root cause is not insufficient capacity — it is the absence of information. Patients who know their wait abandon at lower rates. Staff who have real-time queue visibility spend less time on conflict resolution.

---

## 2. Goals and Success Metrics

| Goal | Metric | Baseline | Target | Timeframe |
|---|---|---|---|---|
| Reduce patient abandonment | % patients who leave before being seen | ~25% | ≤ 15% | 90 days post-launch |
| Recover clinical staff time | Minutes/day spent on queue management | ~60 min | ≤ 30 min | 90 days post-launch |
| Patient information satisfaction | % who found SMS updates useful | 0% | ≥ 70% | 90 days post-launch |
| System reliability | % of mornings system operated without failure | N/A | ≥ 95% | First 90 days |

---

## 3. Non-Goals (v1)

- Appointment pre-scheduling
- Integration with electronic health records
- Payment processing
- Native mobile application
- Multi-facility centralized management
- AI-powered wait time prediction
- Hardware ticket dispensers

---

## 4. User Personas

**Primary User 1 — Patient (Mama Jane)**
34-year-old small business owner. Feature phone user. Visits public outpatient 3–4 times per year. Core need: know her position and when to return without losing income.

**Primary User 2 — Clinical Staff (Nurse Mary)**
41-year-old triage nurse, 12 years experience. Core need: real-time queue visibility, conflict resolution tool, and abandonment data.

*See [personas.md](../research/personas.md) for full profiles.*

---

## 5. User Stories

### Patient Stories

| Priority | User Story | Acceptance Criteria |
|---|---|---|
| P0 | As a patient, I want to register for a queue via SMS so I can get a queue number without a smartphone | Patient texts facility code → receives queue number + estimated wait in <30 seconds |
| P0 | As a patient, I want to receive SMS updates on my position so I can leave briefly without anxiety | Automated SMS at position 10, position 5, and "next" |
| P0 | As a patient, I want a grace window if I leave so I can step out without losing my place permanently | Patient who leaves can rejoin within 45 minutes at original position |
| P1 | As a patient, I want to check my current position by SMS so I always have accurate information | Patient texts "STATUS [queue number]" → receives current position reply |

### Staff Stories

| Priority | User Story | Acceptance Criteria |
|---|---|---|
| P0 | As a nurse, I want a real-time dashboard so I can see the full queue without a paper ledger | Dashboard shows: queue length, each patient's name/number/wait time, updated every 60 seconds |
| P0 | As a nurse, I want to mark patients as served or absent so the queue reflects reality | One-click actions on dashboard; auto-marks absent after grace window |
| P0 | As a nurse, I want automatic abandonment tracking so I have data to show administration | Abandoned patients counted separately from served; shown in daily report |
| P1 | As a nurse, I want to promote urgent patients so clinical priority overrides queue order | Manual priority flag moves patient to top of queue; SMS sent to patient |

### Admin Stories

| Priority | User Story | Acceptance Criteria |
|---|---|---|
| P1 | As a facility administrator, I want a daily summary report so I can track operational performance | Report auto-generated at end of day: registered, served, abandoned, average wait |

---

## 6. Functional Requirements

### SMS Registration System
- Patient sends: `[FACILITY CODE]` to shortcode
- System responds: `Queue #[NUMBER]. Estimated wait: [X] minutes. We will SMS you when you are close.`
- All registration timestamped automatically
- Queue number persists across session (patient can query status)

### Position Update Engine
- Triggers: patient reaches position 10, position 5, position 1 (next)
- SMS format: `KNH Queue Update: You are #[N] in line. Estimated wait: [X] minutes.`
- Grace window trigger: SMS sent when patient is called but not present — 45 minutes to return

### Staff Dashboard
- Real-time queue table: columns = queue number, name, time registered, current wait, status
- Status options: Waiting / Called / Served / Absent / Urgent
- Offline mode: local data stored, syncs when connection restores
- Works on any browser — no installation required

### Abandonment Module
- Patient auto-marked Absent if not checked in after grace window
- Absent patients counted in abandonment total, not served total
- Daily abandonment rate surfaced in summary report

---

## 7. Non-Functional Requirements

| Requirement | Specification |
|---|---|
| Offline capability | Core staff dashboard must function without internet; syncs when connection available |
| SMS delivery | 95% delivery rate target via Safaricom/Africas Talking API |
| Response time | SMS registration confirmation in < 30 seconds |
| Uptime | 99% during facility operating hours (6am–6pm) |
| Feature phone support | All patient interactions via SMS only (no data required) |
| Browser support | Staff dashboard works on Chrome, Firefox, any modern mobile browser |

---

## 8. Assumptions

- Facilities have at least one device (tablet/computer) capable of running a web browser for the staff dashboard
- Safaricom SMS shortcode can be provisioned for health facility use
- Patients have access to SMS (M-Pesa penetration confirms this is near-universal in Kenya)
- Facility administration will provide a single staff champion to lead rollout

---

## 9. Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Intermittent internet at facility | High | High | Offline-first architecture with sync |
| Staff resistance to adoption | Medium | High | Co-design with nurses; start with one champion |
| Low patient SMS literacy | Medium | Medium | Visual instructions at registration desk; community health worker training |
| Safaricom shortcode delays | Low | High | Begin provisioning 3 months before launch |
| Patients don't register (walk in instead) | Medium | High | Registration desk staff guide patients to SMS during onboarding period |

---

## 10. Open Questions

- [ ] Can Safaricom provision a health-specific shortcode within our timeline?
- [ ] What is the NHIF or county government procurement process for piloting software?
- [ ] How do we handle patients without phones at all — estimated 5–10% of patient population?
- [ ] Does the grace window need to vary by facility (45 min may be too long for small facilities)?

---

## 11. Launch Plan Summary

Pilot at one Level 4 urban facility for 90 days. Measure abandonment rate, staff time savings, and patient satisfaction. Decision point at day 60 to expand or iterate.

*See [launch-plan.md](../launch/launch-plan.md) for full detail.*

---

## 12. Revision History

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | June 2026 | Karani Njoroge | Initial draft |
