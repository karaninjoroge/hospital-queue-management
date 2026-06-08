# Interview Synthesis — Hospital Queue Management Platform

**Author:** Karani Njoroge
**Date:** June 2026

---

## Core Finding

**The problem is not wait time. It is uncertainty.**

Across all patient interviews, the dominant emotional driver of dissatisfaction and abandonment is not the length of the wait — it is the complete absence of information about position, progress, and expected time. Patients who know they have 2 hours to wait make productive decisions (leave, return). Patients who do not know tolerate extreme discomfort rather than risk losing their place.

This reframes the product: we are not building a speed solution. We are building a visibility and information solution.

---

## Pattern Summary

| Theme | Patient Evidence | Staff Evidence |
|---|---|---|
| Uncertainty as core pain | "The problem is not waiting. It is not knowing." | — |
| Technology skepticism (staff) | — | "It worked for two weeks. Then broke." |
| Re-entry conflict | "I left once — I lost my place." | "They think they can rejoin. They fight." |
| Offline requirement | — | "We lose connection often. It must work offline." |
| Digital proxy behavior | "My grandson could check for me." | — |
| SMS as equalizer | "I have a simple phone." | — |
| Clinical visibility gap | — | "I want to see in real time how many are waiting." |
| Abandonment undercounting | — | "They never ask about abandonment." |

---

## Validated Hypotheses

✅ Uncertainty, not wait time, drives abandonment
✅ SMS-first design is essential (not everyone has smartphones)
✅ Offline functionality is non-negotiable
✅ Re-entry workflow is a real and underserved problem
✅ Clinical staff want a dashboard, not just a patient-facing tool

---

## Invalidated Assumptions

❌ We assumed patients primarily wanted faster service — they primarily want information
❌ We assumed a mobile app was the right delivery mechanism — SMS and USSD are essential layers
❌ We assumed the primary user was the patient — clinical staff are equally important users

---

## Design Implications

1. Build a real-time queue position update system via SMS as the core product
2. Offline-first architecture — local state syncs when connection returns
3. Re-entry protocol — patients who leave get a grace window to rejoin
4. Staff dashboard — real-time view of queue, wait times, and flags
5. Abandonment tracking — capture and report patients who leave, not just patients served
