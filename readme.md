# AI Platform Decision Playbook

This repository helps consultants decide the best path forward for customers in their AI Application Development Journey. Customers are often confused which platform will provide the best fit for their goals and this repo helps with that decision making.

This framework is only to be used for customers who are fully committed to innovation with AI and have the appropriate budgets and support from their key stakeholders.

The decision tree recommends one of four outcomes:
- **Recommend Copilot Studio**
- **Recommend Microsoft Foundry**
- **Recommend a Hybrid of Both Copilot Studio and Microsoft Foundry**
- **More Discovery Needed**

## How The Decision Works
The framework is a binary decision tree. Each question has explicit YES/NO criteria. If the customer has not provided evidence for a YES answer, the answer is NO. There is no scoring, no weighting, and no facilitator judgment on outcome selection.

The tree terminates at one outcome. That outcome is the recommendation.

## Repository Structure
- `Templates/decision-framework.md` — the decision tree (source of truth for all decision logic)
- `Templates/intake-worksheet.md` — evidence capture form aligned to tree questions
- `Templates/recommendation-template.md` — output memo template
- `Templates/platform-comparison.md` — side-by-side capability comparison mapped to tree questions
- `Copilot Studio/platform-fit-profile.md` — quick reference for Copilot Studio fit/not-fit signals
- `Copilot Studio/research.md` — detailed platform research (capabilities, constraints, use cases)
- `Microsoft Foundry/platform-fit-profile.md` — quick reference for Foundry fit/not-fit signals
- `Microsoft Foundry/research.md` — detailed platform research (capabilities, constraints, use cases)
- `Sample Scenarios/` — calibration examples
- `Engagements/` — customer-specific working folders
- `.github/copilot-instructions.md` — assistant behavior contract

## Per-Customer Workflow

### Setup
1. Create folder: `Engagements/<customer-slug>-<yyyymmdd>/`
2. Copy templates:
```
copy Templates\intake-worksheet.md Engagements\<customer-slug>-<yyyymmdd>\intake-worksheet.md
copy Templates\recommendation-template.md Engagements\<customer-slug>-<yyyymmdd>\recommendation-memo.md
```

### Workshop (60 minutes)
1. **0-5 min** — Context: customer name, objective, sponsor, decision owner, delivery owner.
2. **5-15 min** — Gate 1: Viability. Fill prerequisite table.
3. **15-25 min** — Gate 2: Accountability. Confirm owner and controls.
4. **25-40 min** — Gate 3-6: Route through decision tree questions.
5. **40-50 min** — Capture outcome, confidence, and any Readiness gaps.
6. **50-60 min** — Complete recommendation memo, assign follow-ups, sign off.

### Roles
- **Facilitator**: asks questions exactly as written, controls timebox.
- **Recorder**: captures exact customer statements and evidence sources.
- **Reviewer**: validates YES/NO criteria are correctly applied.

Do not run a workshop without all three roles assigned.

### Done Criteria
- Worksheet is complete (every gate answered or terminal outcome reached).
- Recommendation memo is complete.
- If Readiness: gap register has owner/date for every blocking item.
- Sign-off fields are filled.

## Workshop Operating Rules

### Rule 1: Follow the tree
Ask questions in the order specified by `Templates/decision-framework.md`. Do not skip. Do not reorder.

### Rule 2: Apply criteria literally
Each question has explicit YES/NO criteria. Apply them as written. If the customer's answer does not clearly meet YES criteria, the answer is NO.

### Rule 3: Unknown = NO
If the customer cannot provide evidence for a YES answer, record NO. Do not infer YES from intent, optimism, or partial information.

### Rule 4: No override
The tree outcome is the recommendation. Sponsor preference, facilitator opinion, and organizational politics do not change the outcome. If stakeholders disagree with the outcome, document the disagreement and escalate — do not change the worksheet answers.

### Rule 5: Readiness is not failure
More Discovery Needed means the evidence is not yet strong enough to commit resources to a platform. It requires structured gap closure with a maximum 30-day reassessment cycle.

## Quality Gates

### Completeness
- Every question in the worksheet is answered or the tree terminated before reaching it.
- Every YES answer has an evidence source.
- Every NO answer that blocked a path is documented in the Readiness plan (if applicable).

### Evidence Integrity
- No YES answer is based on "we think" or "probably."
- Every verbal confirmation is flagged for written follow-up.

### Decision Integrity
- The recorded outcome matches the tree routing for the recorded answers.
- Reviewer has verified this independently.

## Escalation
Escalate to architecture board when:
- Stakeholders reject the tree outcome without new evidence.
- More Discovery Needed exceeds 30 days without resolution.
- Both platform paths remain eliminated after reassessment.

## New Team Member Onboarding
1. Read `Templates/decision-framework.md` end-to-end.
2. Walk one sample scenario from `Sample Scenarios/`.
3. Pair with a reviewer for first customer workshop.
4. Practice: given sample answers, can you route to the correct outcome independently?
