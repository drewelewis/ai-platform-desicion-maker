# Sample Scenario 01: Copilot Studio Outcome

## Customer Context
- Customer: Contoso HR
- Objective: Automate employee FAQ and benefits enrollment in Teams
- Sponsor: VP of HR Operations
- Decision owner: Director of HR Technology

## Decision Tree Walkthrough

### Q1.1: Prerequisites
- Azure subscription: Active (confirmed by IT admin, portal verified)
- Foundry RBAC: Active
- Foundry region/model: Active
- M365 tenant: Active (confirmed by M365 admin)
- Copilot Studio licensing: Active (standalone license purchased)

**Answer: YES â€” both paths viable.**

### Q2.1: Named post-launch owner
- Named owner: Sarah Chen, HR Technology Lead
- Confirmed acceptance: Yes (stated in kickoff meeting)
- Escalation path: Sarah â†’ Director of HR Tech â†’ CIO

**Answer: YES.**

### Q2.2: Day-1 controls
- DLP policy on HR data: Approach defined (Purview policy), Owner: InfoSec lead
- Authentication: Entra ID SSO, Owner: Identity team lead

**Answer: YES.**

### Q3.1: Deep control mandatory?
- Customer's example: "We need the bot to answer benefits questions using our SharePoint knowledge base and route complex cases to a human agent."
- Can Copilot Studio satisfy this? YES â€” generative answers over SharePoint + topic escalation.

**Answer: NO â€” deep control not mandatory. Route to Copilot track.**

### Q5.1: >=80% usage in M365/Teams?
- Customer: "All 12,000 employees use Teams daily. This will be a Teams app."

**Answer: YES.**

### Q5.2: Business teams own changes?
- Named business owner for post-launch: Sarah Chen
- Skills: Completed Copilot Studio training
- Engineering releases required: No

**Answer: YES.**

## Outcome: Recommend Copilot Studio
- Path: Q1.1(YES) â†’ Q2.1(YES) â†’ Q2.2(YES) â†’ Q3.1(NO) â†’ Q5.1(YES) â†’ Q5.2(YES)
- Confidence: High
