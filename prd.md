# Product Requirements Document — Hospital Queue Management Platform

> **Version:** 0.1 (Draft) | **Status:** In Progress | **Author:** Dennis Karani Njoroge
> **Last updated:** 2024

---

## Executive Summary

Kenyan public hospital OPD queues average 4–6 hours of wait time per patient visit, driven by manual registration, 35%+ no-show rates, and zero real-time visibility for clinical staff. We are building a lightweight digital queue system with USSD fallback that reduces wait time to under 90 minutes, lowers no-show rates below 20%, and gives nurses real-time queue visibility — deployable at any Level 4+ facility with minimal hardware investment.

---

## Background

*(To be completed after primary research)*

---

## Problem Statement

Patients attending outpatient departments at Kenyan public hospitals lose an average of 4–6 hours per visit to queue management failures. Root causes: manual registration, no cancellation mechanism, no real-time staff visibility, and no appointment reminders.

---

## Goals

**In scope:**
- Digital check-in via smartphone app and USSD
- Automated SMS/USSD appointment reminders (24h + 2h before)
- Real-time queue dashboard for front-desk staff and nurses
- Simple cancellation and rescheduling via USSD
- Basic analytics for hospital administrators

**Out of scope (v1):**
- Payment integration
- Integration with NHIF claims system
- Electronic medical records
- Multi-facility coordination
- Prescription management

---

## User Stories

| As a... | I want to... | So that... | Priority |
|---|---|---|---|
| Patient | Join the queue from home via USSD | I don't need to arrive early just to secure a place | Must |
| Patient | Receive an SMS reminder with my estimated wait time | I can plan when to leave home | Must |
| Patient | Cancel or reschedule my appointment via USSD | The slot can be given to another patient | Must |
| Nurse | See the live queue on a tablet dashboard | I can manage patient flow without manual counting | Must |
| Nurse | Mark a patient as seen with one tap | The system updates in real time | Must |
| Administrator | See daily throughput and average wait times | I can identify bottlenecks and report to management | Should |
| Patient | Receive SMS updates when my turn is approaching | I can wait nearby rather than in the crowded waiting room | Should |

---

## Functional Requirements

**Must have (v1 launch blockers):**
- USSD registration flow (works on any Safaricom number)
- SMS confirmation and reminders
- Real-time queue dashboard (tablet, browser-based)
- Patient check-in on arrival (USSD or QR scan)
- Basic no-show handling (auto-advance queue after timeout)

**Should have (v1.1):**
- Admin analytics dashboard
- Multi-department routing
- Patient satisfaction survey (via SMS post-visit)

**Could have (v2):**
- Smartphone app (iOS + Android)
- NHIF integration
- Predictive wait time modelling

---

## Success Metrics

| Metric | Baseline | Target (90 days post-launch) |
|---|---|---|
| Average OPD wait time | ~240 min | < 90 min |
| No-show rate | ~35% | < 20% |
| Daily appointment utilisation | ~65% | > 85% |
| Staff time on manual queue management | ~2 hrs/day | < 30 min/day |
| Patient NPS | Unknown (baseline to be set) | +30 vs baseline |

**Guardrail metrics (must not degrade):**
- System uptime must be > 99% during facility hours
- USSD registration must complete in < 3 steps
- Patient data must remain within Kenya (data residency compliance)

---

## Technical Considerations

*(To be completed with engineering input)*
- USSD integration via Safaricom AfricasTalking API
- SMS via AfricasTalking or Twilio
- Offline-capable dashboard (connectivity at facilities is unreliable)
- Low-cost hardware: runs on existing tablets or donated devices

---

## Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Staff resistance to digital system | High | High | Co-design with staff from day 1; make staff job easier, not harder |
| USSD registration abandonment | Medium | High | Keep flow to 3 steps maximum; test with low-literacy users |
| Hospital IT policy barriers | Medium | High | Engage facility management early; design for BYOD (no new hardware required) |
| Low patient trust in digital queuing | Medium | Medium | Maintain physical fallback; launch with hybrid system |

---

## Rollout Plan

**Phase 1 — Pilot (Weeks 1–6):**
Single facility, OPD only, USSD + staff dashboard. Measure baseline vs. target metrics.

**Phase 2 — Iteration (Weeks 7–12):**
Incorporate feedback. Add multi-department routing. Begin second facility.

**Phase 3 — Scale (Month 4+):**
Expand to 5 facilities. Build admin analytics. Explore NHIF partnership.

---

## Open Questions

- [ ] Which facility will serve as the pilot? (Need facility management buy-in)
- [ ] Is AfricasTalking the right USSD provider for this context?
- [ ] What are the data residency and privacy requirements under Kenya's Data Protection Act?
- [ ] How do we handle patients who don't have a phone?

---

## Revision History

| Version | Date | Changes |
|---|---|---|
| 0.1 | 2024 | Initial draft — structure complete, research sections TBD |
