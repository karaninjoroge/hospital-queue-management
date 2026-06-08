# MVP Definition — Hospital Queue Management Platform

**Author:** Karani Njoroge
**Date:** June 2026
**Version:** 1.0

---

## MVP Principle

The MVP must solve the core problem — uncertainty — for both patients and clinical staff, using the minimum functionality required to validate that information delivery reduces abandonment.

We are not building a full hospital management system. We are building a queue visibility and coordination layer.

---

## In Scope — MVP

**Patient Side:**
- SMS registration: patient texts a facility code to receive a queue number
- SMS position updates: automated messages when patient reaches position 10, 5, and "next"
- Re-entry grace window: patient who leaves can rejoin within 45 minutes without losing position

**Staff Side:**
- Web-based staff dashboard: real-time view of queue — number waiting, average wait time, position of each patient
- Manual override: staff can promote urgent patients or mark patients as served
- Abandonment tracking: patients marked absent after grace window counted as abandoned (not served)

**Admin Side:**
- Daily summary report: patients registered, served, abandoned, average wait time per day

---

## Out of Scope — MVP

- Appointment scheduling (future: reduces physical load)
- Payment integration
- EHR/patient record integration
- Native mobile app (SMS-first for v1)
- AI-based wait time prediction
- Multi-facility management
- USSD interface (v1.1 — validated demand first)
- Hardware ticket printers

---

## Why This Scope

The re-entry problem, the staff dashboard, and the abandonment tracking are all in MVP because they are prerequisites for staff adoption. If the system does not solve the most painful staff problem (queue conflict resolution), nurses will not trust or use it — and patient adoption becomes irrelevant.

The exclusions are all features that add value but require validation of the core problem first.

---

## MVP Success Definition

At the end of a 90-day pilot at one Level 4 facility:
- Patient abandonment rate falls by ≥ 20%
- Staff report spending < 30 minutes on queue management per morning (down from ~60)
- > 70% of patients who register via SMS report the information was useful
- Zero instances of system causing more confusion than it resolved (measured by staff feedback)
