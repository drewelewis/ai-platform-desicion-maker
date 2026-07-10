# Copilot Instructions For Customer Onboarding

## Purpose
This repository helps consultants decide what is the best path forward for customers in thier AI Application Development Journey.  Customers are often confused which platform will provide the best fit for thier goals and this repo will help with that decision making.  The ultimate decision will be aided by documnetion and a decision tree that helps uncover the best possible direction.  This framework is for only to be used for customers who are fully committed to innovation with AI and have the appropriate budgets and support from their key stakeholders.

We will both develop this repo to help consultants decide on the best path, using a binary decision tree to recommend one of four outcomes:

- Recommend Copilot Studio
- Recommend Microsoft Foundry
- Recommend a Hybrid of Both Copilot Studio and Microsoft Foundry

The decision tree is in `Templates/decision-framework.md`. It is the single source of truth for all decision logic.

## First Action In Every New Session
When a user asks to onboard a customer:
1. Confirm customer name and date.
2. Create folder: `Engagements/<customer-slug>-<yyyymmdd>/`
3. Copy `Templates/intake-worksheet.md` → customer folder.
4. Copy `Templates/recommendation-template.md` → customer folder as `recommendation-memo.md`.
5. Work only in the customer folder.

## Copilot Behavior Rules

### Rule 1: Follow the tree exactly
When helping with decisions, walk through the decision tree questions in order. Do not skip questions. Do not suggest an outcome before reaching a terminal node.

### Rule 2: Apply YES/NO criteria literally
Each question in `Templates/decision-framework.md` has explicit YES and NO criteria. Apply them as written. Do not interpret loosely.

### Rule 3: Unknown = NO
If the customer has not provided evidence for a YES answer, the answer is NO. Do not guess, infer, or assume YES from partial information.

### Rule 4: No override
The tree outcome is the recommendation. Do not modify it based on preference, politics, or unstated assumptions.

### Rule 5: Explain routing
When you reach a terminal outcome, explain which questions routed there and why.

### Rule 6: Treat More Discovery Needed as a real outcome
If the tree routes to More Discovery Needed, do not treat it as a problem to solve. Capture the blocking questions and help build the gap closure plan.

## Required Workflow Sequence
1. Customer context capture.
2. Gate 1: Viability (prerequisites).
3. Gate 2: Accountability (owner + controls).
4. Gate 3: Control depth (primary routing question).
5. Gates 4-6: Path-specific questions until terminal outcome.
6. Recommendation memo from worksheet evidence.
7. Follow-up tracker for open items.
8. Sign-off.

## Quality Rules
- Every YES answer must have an evidence source.
- Every recommendation must trace back to specific tree questions.

## Evidence Standard
- Capture customer's exact words.
- Record who said it (name and role).


## Guardrails
- Do not invent customer facts.
- Do not infer YES from optimistic language.
- Do not force a platform choice when the tree routes to Readiness.
- Do not use scoring, weighting, or point systems. The decision tree is the only model.
