# Sample Scenario 02: Microsoft Foundry Outcome

## Customer Context
- Customer: Woodgrove Financial
- Objective: Deploy a custom fraud detection agent with model evaluation pipeline and strict SLOs
- Sponsor: CTO
- Decision owner: VP of Engineering

## Decision Tree Walkthrough

### Q1.1: Prerequisites
- Azure subscription: Active (production subscription confirmed)
- Foundry RBAC: Active (admin confirmed assignment capability)
- Foundry region/model: Active (East US 2, GPT-4o available)
- M365 tenant: Active
- Copilot Studio licensing: Active

**Answer: YES â€” both paths viable.**

### Q2.1: Named post-launch owner
- Named owner: Marcus Rivera, Platform Engineering Lead
- Confirmed acceptance: Yes (written confirmation in project charter)
- Escalation path: Marcus â†’ VP Engineering â†’ CTO

**Answer: YES.**

### Q2.2: Day-1 controls
- Private networking: VNet integration required, approach defined, Owner: Network team lead
- RBAC separation: Custom roles defined, Owner: Identity team
- Audit logging: Azure Monitor + custom pipeline, Owner: Marcus Rivera

**Answer: YES.**

### Q3.1: Deep control mandatory?
- Customer's example: "We must evaluate model accuracy against labeled fraud datasets before every release. We need to compare GPT-4o vs fine-tuned models and enforce p95 latency under 2 seconds."
- Can Copilot Studio satisfy this? NO â€” requires structured evaluation pipelines, model comparison, and custom SLO enforcement.

**Answer: YES â€” deep control mandatory. Route to Foundry track.**

### Q4.1: Engineering owner confirmed?
- Named engineering owner: Marcus Rivera
- Confirmed capacity: Yes (team of 4 platform engineers allocated)
- On-call model: PagerDuty rotation defined

**Answer: YES.**

### Q4.2: Also need business copilots this phase?
- Customer: "No. This phase is purely the fraud detection platform. Business-facing tools are phase 2."

**Answer: NO.**

## Outcome: Recommend Microsoft Foundry
- Path: Q1.1(YES) â†’ Q2.1(YES) â†’ Q2.2(YES) â†’ Q3.1(YES) â†’ Q4.1(YES) â†’ Q4.2(NO)
- Confidence: High
