# Metrics — Hospital Queue Management Platform

**Author:** Karani Njoroge
**Date:** June 2026

---

## North Star Metric

**Patients served per day who registered via SMS**

This metric captures product adoption AND clinical throughput improvement simultaneously. It goes up only when patients are using the system AND being seen — not just signing up.

---

## Why This North Star

Alternative considered: Abandonment rate reduction
Rejected because: Abandonment is a lagging indicator. It tells us what happened, not what the product is driving.

Alternative considered: SMS registrations per day
Rejected because: Registrations without completions (being served) means the system is not solving the problem — patients still abandoning.

---

## Supporting Metrics

| Metric | What It Measures | Target |
|---|---|---|
| Daily abandonment rate | % patients who leave before being seen | ≤ 15% (from ~25%) |
| Staff queue management time | Minutes/day spent on manual queue tasks | ≤ 30 min (from ~60) |
| SMS delivery rate | % of queue update SMS successfully delivered | ≥ 95% |
| Patient satisfaction with updates | % rating SMS updates as "useful" or "very useful" | ≥ 70% |
| System uptime | % of operating hours with functional dashboard | ≥ 99% |
| Re-entry usage rate | % of patients who use grace window and return | Baseline → track |

---

## Counter Metrics (What We Monitor to Prevent Gaming)

| Counter Metric | Risk It Guards Against |
|---|---|
| Patients registered but never served | Gaming registration numbers without clinical value |
| Staff-initiated queue clears | Staff bypassing system to reset counts |
| Complaint rate | System causing confusion or new conflict |

---

## Measurement Plan

- Abandonment rate: captured automatically by system (absent vs. served)
- Staff time: self-reported weekly survey (2 questions, 2 minutes)
- Patient satisfaction: SMS survey sent after visit ("Did our SMS updates help? Reply Y or N")
- Delivery rate: Africa's Talking API dashboard
- System uptime: server monitoring logs

---

## 90-Day Review Framework

**Day 30:** Is adoption happening? Are staff using dashboard? Are patients texting in?
**Day 60:** Is abandonment rate moving? Is staff time recovering? Decision point: expand or iterate.
**Day 90:** Full pilot assessment. Present to facility administration with data.
