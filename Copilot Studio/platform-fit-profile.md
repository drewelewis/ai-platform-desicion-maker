# Copilot Studio — Platform Reference

## Purpose
This document helps facilitators and GitHub Copilot answer decision tree questions accurately. It is not a decision document. The decision tree in `Templates/decision-framework.md` is the only decision authority.

**Last refreshed: 2026-07-10**

## Supporting Research
For detailed platform capabilities, constraints, and evidence sources, see:
- `Copilot Studio/research.md` — full capability inventory, technical limits, and use case patterns
- `Templates/platform-comparison.md` — side-by-side comparison with Microsoft Foundry

## What Copilot Studio Is
A low-code platform for building conversational and workflow AI experiences within Microsoft 365 channels. Owned and operated by business teams without engineering release processes.

## When The Decision Tree Routes Here
The tree routes to Copilot Studio when:
- Deep model/runtime/evaluation control is NOT mandatory in this phase (Q3.1 = NO).
- Primary usage is in M365/Teams channels (Q5.1 = YES).
- Business teams can own ongoing changes (Q5.2 = YES).
- Copilot Studio prerequisites are confirmed (Q1.1 = YES for Copilot path).

## Prerequisites (Used in Q1.1)
- M365 tenant aligned for target users.
- Copilot Studio licensing in place (Teams plan or standalone).
- Connector readiness for required integrations.
- Named business owner for support and change management.

## What "Deep Control" Looks Like That Copilot Studio Cannot Satisfy (Used in Q3.1)
- Custom model selection/comparison/switching.
- Structured evaluation pipelines with rollback.
- Imperative code-level orchestration logic (not AI-managed generative orchestration).
- Custom SLOs on model inference.
- API integration that cannot use prebuilt connectors.
- Programmatic multi-agent routing with custom delegation logic.

If a customer's "deep control" example falls into any of the above, Q3.1 = YES and the tree routes to Foundry track.

## What Copilot Studio CAN Satisfy
- Generative answers over grounded content (SharePoint, OneDrive, Dataverse, Salesforce, Confluence, ServiceNow, Zendesk, files, websites).
- AI-orchestrated tool and topic selection (generative orchestration).
- Child/connected agent composition (AI-selected by description).
- Standard connector integrations (SharePoint, Dataverse, HTTP, custom APIs via plugin).
- Agent Flows and Workflows for automation.
- Business-owned content and instruction updates without code deployment.
- Teams/M365 channel delivery.
- Basic analytics, conversation monitoring, Microsoft Purview audit logs.
- Event-triggered autonomous actions.

If a customer's examples fall entirely within this list, Q3.1 = NO.

## Caution Signals (For Facilitator Awareness, Not Decision Override)
- Customer mentions "enterprise scale" without specific targets.
- Customer cannot name a business owner.
- Integration requirements are vague or unvalidated.
- Security requirements exist but are undefined.

These signals do not change tree routing. They inform follow-up actions.

## Red Flags (Indicate Decision May Be Wrong)
- No named business owner for post-launch operations → Q2.1 should have routed to Readiness.
- Deep control example provided but dismissed → Q3.1 may have been answered incorrectly.
- M365 licensing is not confirmed → Q1.1 should have eliminated this path.

If a red flag is observed post-decision, the reviewer should challenge the specific worksheet answer.
