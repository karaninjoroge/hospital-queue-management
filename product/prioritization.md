# Prioritization — Hospital Queue Management Platform

**Author:** Karani Njoroge
**Date:** June 2026
**Framework:** RICE (Reach, Impact, Confidence, Effort)

---

## RICE Scoring Guide

- **Reach:** Number of users affected per week (at a 400-patient/day facility)
- **Impact:** 1 = minimal, 2 = low, 3 = medium, 5 = high, 10 = massive
- **Confidence:** % confidence in our estimates (based on research)
- **Effort:** Person-weeks to build

**RICE Score = (Reach × Impact × Confidence) / Effort**

---

## Feature Prioritization Table

| Feature | Reach | Impact | Confidence | Effort | RICE Score | Priority |
|---|---|---|---|---|---|---|
| SMS queue registration | 2,000/wk | 10 | 90% | 3 | 6,000 | P0 |
| SMS position updates | 2,000/wk | 10 | 85% | 2 | 8,500 | P0 |
| Staff dashboard | 10/wk | 10 | 90% | 4 | 225 | P0 |
| Abandonment tracking | 10/wk | 8 | 80% | 2 | 320 | P0 |
| Re-entry grace window | 400/wk | 8 | 75% | 2 | 1,200 | P0 |
| Daily summary report | 5/wk | 5 | 80% | 1 | 200 | P1 |
| USSD fallback | 500/wk | 7 | 70% | 5 | 490 | P1 |
| Priority flagging (urgent) | 10/wk | 8 | 85% | 2 | 340 | P1 |
| Appointment scheduling | 2,000/wk | 8 | 50% | 10 | 800 | P2 |
| Native mobile app | 500/wk | 5 | 60% | 12 | 125 | P2 |
| EHR integration | 10/wk | 6 | 40% | 15 | 16 | P3 |
| AI wait time prediction | 2,000/wk | 4 | 40% | 8 | 400 | P3 |

---

## Prioritization Decisions

**Why SMS updates ranked higher than SMS registration:** Registration is a prerequisite, but updates are where the uncertainty problem is actually solved. A patient who registers but receives no updates is only marginally better off than before.

**Why staff dashboard is P0 despite low reach:** Staff adoption is a prerequisite for system functioning. Without nurse buy-in, the patient-facing features have no operational context to run within.

**Why appointment scheduling is P2 despite high reach:** Confidence is low (50%) because we have not validated that patients will actually pre-plan appointments rather than walk in. We build this after the core queue system proves its value.
