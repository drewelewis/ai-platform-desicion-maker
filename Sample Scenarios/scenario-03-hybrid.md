# Sample Scenario 03: Hybrid Outcome

## Customer Context
- Customer: Fabrikam Manufacturing
- Objective: Deploy a quality-inspection AI platform (engineering-led) AND a frontline worker copilot for shift handoff in Teams (business-led), same phase
- Sponsor: COO
- Decision owner: VP of Digital Operations

## Decision Tree Walkthrough

### Q1.1: Prerequisites
- Azure subscription: Active
- Foundry RBAC: Active
- Foundry region/model: Active (West US 2, GPT-4o + custom vision model)
- M365 tenant: Active
- Copilot Studio licensing: Active (Teams plan)

**Answer: YES â€” both paths viable.**

### Q2.1: Named post-launch owner
- Named owner: Two owners identified:
  - Engineering platform: James Park, Senior ML Engineer
  - Business copilot: Diana Torres, Operations Manager
- Both confirmed acceptance: Yes
- Escalation: James â†’ VP Engineering; Diana â†’ VP Operations â†’ COO

**Answer: YES.**

### Q2.2: Day-1 controls
- Data residency: US-only, approach defined, Owner: Compliance lead
- RBAC: Separate workspaces for platform vs copilot, Owner: Identity team
- Audit: Centralized logging, Owner: James Park

**Answer: YES.**

### Q3.1: Deep control mandatory?
- Customer's example: "The quality-inspection model requires custom evaluation against labeled defect datasets, and we need to enforce 99.5% uptime SLO on the inference endpoint. We also need model versioning and rollback."
- Can Copilot Studio satisfy this? NO.

**Answer: YES â€” deep control mandatory. Route to Foundry track.**

### Q4.1: Engineering owner confirmed?
- Named: James Park
- Capacity: Confirmed (dedicated ML platform team of 3)
- On-call: Defined rotation

**Answer: YES.**

### Q4.2: Also need business copilots this phase?
- Customer: "Yes. The frontline shift-handoff copilot must launch in the same quarter. Operations team will own it. It runs in Teams."
- Business-team owned: Yes (Diana Torres)
- Same delivery timeline: Yes (Q3 2026)

**Answer: YES â€” both needs exist in same phase. Route to Q4.3.**

### Q4.3: Can fund and staff split ownership?
- Budget: Confirmed for both (separate cost centers approved by CFO)
- Named Copilot owner: Diana Torres
- Named Foundry owner: James Park
- Governance model: Monthly cross-workstream sync, shared risk register, unified escalation to COO

**Answer: YES.**

## Outcome: Recommend a Hybrid of Both Copilot Studio and Microsoft Foundry
- Path: Q1.1(YES) â†’ Q2.1(YES) â†’ Q2.2(YES) â†’ Q3.1(YES) â†’ Q4.1(YES) â†’ Q4.2(YES) â†’ Q4.3(YES)
- Confidence: High
