# User Interviews — Hospital Queue Management Platform

**Author:** Karani Njoroge
**Date:** June 2026
**Participants:** 6 (3 patients, 3 clinical staff)

---

## Interview 1 — Patient

**Participant:** Jane, 34, small business owner, Nairobi
**Facility:** Kenyatta National Hospital Outpatient
**Date:** June 2026

**Selected Excerpts:**

> "I arrived at 5:30am to make sure I was near the front. By 9am I still hadn't been called. No one tells you anything. You just sit there guessing."

> "I left once — I had to open my shop. I lost my whole day and didn't even see the doctor. I just bought medicine at the chemist and hoped for the best."

> "If someone told me 'you are number 47, estimated wait is 2 hours' — I would go get breakfast, come back. I would not leave. The problem is not waiting. It is not knowing."

**Key Observations:**
- Patient's core frustration is informational, not temporal
- She has a high-value use of time (business income) that makes uncertainty especially costly
- She has workarounds (chemist) that bypass the system entirely — a dangerous health behavior

---

## Interview 2 — Patient

**Participant:** Joseph, 58, retired civil servant, Kisumu
**Facility:** Jaramogi Oginga Odinga Teaching and Referral Hospital
**Date:** June 2026

**Selected Excerpts:**

> "The young ones push to the front. By the time they call my number I have been sitting for five hours. My legs hurt. There is nowhere to sit outside."

> "I bring my grandchild sometimes. There is nowhere clean for a child to wait. We sit on the floor."

> "I would not use a phone for this. I have a simple phone. My grandson has a smartphone. Maybe he could check for me."

**Key Observations:**
- Older patients face physical discomfort in long waits — ergonomic environment is part of the experience
- Digital proxy behavior (using a family member's smartphone) is a real pattern worth designing for
- SMS-based updates essential — not everyone has a smartphone

---

## Interview 3 — Patient

**Participant:** Amina, 26, university student, Mombasa
**Facility:** Coast General Hospital
**Date:** June 2026

**Selected Excerpts:**

> "I checked if there was an app. There wasn't. I just had to go and wait like everyone else."

> "My friend told me to go on a Tuesday — fewer people. So we all go on Tuesday now and it's just as bad."

> "If there was a way to book a slot — even just a rough slot — I would use it every time. I'd pay a small fee even."

**Key Observations:**
- Younger patients are actively looking for digital solutions and finding none
- Information asymmetry creates folk heuristics (go on Tuesday) that collapse the very advantage they seek
- Willingness to pay exists among younger segment — but monetization through patients creates equity issues

---

## Interview 4 — Clinical Staff

**Participant:** Nurse Mary, 41, triage nurse, 12 years experience
**Facility:** Pumwani Maternity Hospital (general outpatient)
**Date:** June 2026

**Selected Excerpts:**

> "Every morning is a fight. People argue about who arrived first. There is no proof. We have to manage that conflict ourselves."

> "By 8am I have already spent one hour just organizing the line. That is one hour I am not doing clinical work."

> "We tried a numbering system last year. It worked for two weeks. Then the machine broke and no one fixed it. We went back to the old way."

**Key Observations:**
- Staff have tried and experienced failed technology implementations — trust must be rebuilt through reliability
- Queue management consuming ~1 hour/day per staff member = significant recoverable time
- Manual conflict resolution is emotionally draining — a hidden cost not captured in throughput metrics

---

## Interview 5 — Clinical Staff

**Participant:** Registration Clerk Peter, 29, 3 years experience
**Facility:** Mbagathi District Hospital
**Date:** June 2026

**Selected Excerpts:**

> "The biggest problem is when patients leave and come back — they think they can rejoin at their original position. They fight with everyone."

> "I write names in a book. That's the system. If I lose the book, we start over. It has happened."

> "A digital system needs to work even when the internet is off. We lose connection often."

**Key Observations:**
- Re-entry problem (patient leaves and returns) is a significant unresolved workflow issue
- Paper-based systems have catastrophic failure modes (book loss)
- Offline functionality is not a nice-to-have — it is a launch blocker

---

## Interview 6 — Clinical Staff

**Participant:** Clinical Officer Dr. Wanjiku, 36, outpatient lead
**Facility:** Thika Level 5 Hospital
**Date:** June 2026

**Selected Excerpts:**

> "We see about 400 patients a day. Maybe 60 leave before being seen. That is 60 people whose condition we do not know."

> "The administration asks us for throughput numbers. But they never ask about abandonment. It's like it doesn't count if they left."

> "If I could see in real time how many are waiting, who has been waiting longest, and flag urgent cases — that would change how I manage the day."

**Key Observations:**
- Clinical leadership wants real-time visibility, not just patient-facing features
- Abandonment is systematically undercounted — creates false picture of capacity
- Priority flagging (urgent vs. standard) is a high-value feature for clinical staff
