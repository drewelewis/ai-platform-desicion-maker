# Customer Intake Worksheet

## Instructions
This worksheet captures evidence for each decision tree question. Fill it in order during the workshop. Do not skip sections. Every answer must include who said it and what evidence backs it.

---

## Customer Context
- Customer name:
- Account owner:
- Date:
- Primary business objective:
- Target launch window:
- Primary sponsor (name and role):
- Decision owner (name and role):

---

## Gate 1: Viability

### Question 1.1: Prerequisites

| Prerequisite | Status (Active / <=10 days / Not ready) | Owner (name) | Evidence source | Target date (if <=10 days) |
|---|---|---|---|---|
| Azure subscription for Foundry |  |  |  |  |
| Foundry RBAC assignable |  |  |  |  |
| Foundry target region/model/features |  |  |  |  |
| M365 tenant aligned |  |  |  |  |
| Copilot Studio licensing |  |  |  |  |

**Decision: Are all required prerequisites for at least one path confirmed?**
- [ ] YES â€” both paths viable
- [ ] YES â€” Copilot path only (Foundry eliminated)
- [ ] YES â€” Foundry path only (Copilot eliminated)
- [ ] NO â€” both paths failed â†’ **OUTCOME: More Discovery Needed**

If More Discovery Needed, skip to More Discovery Needed Plan section.

---

## Gate 2: Accountability

### Question 2.1: Post-launch owner

- Named owner:
- Role:
- Has this person confirmed acceptance? (Yes/No):
- Escalation path documented? (Yes/No):
- Evidence source (who confirmed, when):

**Decision:**
- [ ] YES â€” named owner confirmed with escalation path
- [ ] NO â†’ **OUTCOME: More Discovery Needed**

---

### Question 2.2: Day-1 mandatory controls

| Control requirement | Implementation approach | Owner (name) | Evidence source |
|---|---|---|---|
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

**Decision: Are day-1 controls named, approached, and owned?**
- [ ] YES
- [ ] NO â†’ **OUTCOME: More Discovery Needed**

---

## Gate 3: Control Depth

### Question 3.1: Deep model/runtime/evaluation control mandatory now?

Customer's concrete example of control they must exercise:
>

Can this example be satisfied by Copilot Studio built-in capabilities?
- [ ] Yes â€” it can be satisfied by Copilot Studio
- [ ] No â€” it requires Foundry-level control

**Decision:**
- [ ] Deep control is mandatory â†’ proceed to **Gate 4 (Foundry track)**
- [ ] Deep control is NOT mandatory â†’ proceed to **Gate 5 (Copilot track)**

---

## Gate 4: Foundry Track

### Question 4.1: Engineering owner for platform operations

- Named engineering owner:
- Confirmed capacity? (Yes/No):
- On-call/support model defined? (Yes/No):
- Evidence source:

**Decision:**
- [ ] YES â€” engineering owner confirmed
- [ ] NO â†’ **OUTCOME: More Discovery Needed**

---

### Question 4.2: Also need business copilots this phase?

Business-facing use cases identified for same delivery phase:
>

Are these use cases business-team owned (not engineering)? (Yes/No):

**Decision:**
- [ ] YES â€” concurrent business copilot need exists â†’ proceed to Q4.3
- [ ] NO â†’ **OUTCOME: Recommend Microsoft Foundry**

---

### Question 4.3: Can fund and staff split ownership?

- Budget for both workstreams confirmed? (Yes/No):
- Named owner for Copilot workstream:
- Named owner for Foundry workstream:
- Coordination/governance model defined? (Yes/No):
- Evidence source:

**Decision:**
- [ ] YES â†’ **OUTCOME: Recommend a Hybrid of Both Copilot Studio and Microsoft Foundry**
- [ ] NO â†’ **OUTCOME: More Discovery Needed**

---

## Gate 5: Copilot Track

### Question 5.1: >=80% usage in M365/Teams?

- Primary channel(s) named by customer:
- Customer confirmation that >=80% of interactions will be in these channels? (Yes/No):
- Evidence source:

**Decision:**
- [ ] YES â€” M365/Teams dominant â†’ proceed to Q5.2
- [ ] NO â†’ proceed to **Gate 6**

---

### Question 5.2: Business teams own changes?

- Named business owner for post-launch changes:
- Skills or training plan in place? (Yes/No):
- Changes require engineering releases? (Yes/No):
- Evidence source:

**Decision:**
- [ ] YES â€” business ownership confirmed â†’ **OUTCOME: Recommend Copilot Studio**
- [ ] NO â†’ proceed to **Gate 6**

---

## Gate 6: Ambiguous Path Resolution

### Question 6.1: Need both business copilots + platform depth this phase?

Business-workflow use cases (low-code, business-owned):
>

Platform-engineering use cases (custom model control, orchestration, evaluation):
>

Both scoped for same delivery phase? (Yes/No):

**Decision:**
- [ ] YES â€” both types needed now â†’ proceed to Q6.2
- [ ] NO â†’ proceed to Q6.3

---

### Question 6.2: Can fund and staff split ownership?

(Same as Q4.3 â€” if already answered, reference that answer.)

**Decision:**
- [ ] YES â†’ **OUTCOME: Recommend a Hybrid of Both Copilot Studio and Microsoft Foundry**
- [ ] NO â†’ **OUTCOME: More Discovery Needed**

---

### Question 6.3: Primary need engineering-led?

Dominant use case requires:
- [ ] Code-level orchestration
- [ ] Model selection/evaluation control
- [ ] Enforced SLOs or custom observability
- [ ] None of the above (workflow automation, knowledge retrieval, conversational assistance)

**Decision:**
- [ ] Engineering-led â†’ **OUTCOME: Recommend Microsoft Foundry**
- [ ] Not engineering-led â†’ **OUTCOME: Recommend Copilot Studio**

---

## Final Outcome

- **Decision tree outcome:**
- **Confidence level:** High / Medium / Low
- **Blocking question(s) (if Readiness):**

---

## More Discovery Needed Plan (complete only if Readiness selected)

| Blocking question | What must change | Owner | Due date | Validation method | Status |
|---|---|---|---|---|---|
|  |  |  |  |  | Open |
|  |  |  |  |  | Open |
|  |  |  |  |  | Open |

- Reassessment date:
- Reassessment facilitator:

---

## Follow-up Tracker

| Item | Owner | Due date | Status |
|---|---|---|---|
|  |  |  | Open |
|  |  |  | Open |
|  |  |  | Open |

---

## Sign-off

- Facilitator (name/date):
- Reviewer (name/date):
- Decision owner (name/date):
