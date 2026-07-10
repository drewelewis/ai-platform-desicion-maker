# Microsoft Foundry — Platform Reference

## Purpose
This document helps facilitators and GitHub Copilot answer decision tree questions accurately. It is not a decision document. The decision tree in `Templates/decision-framework.md` is the only decision authority.

**Last refreshed: 2026-07-10**

## Supporting Research
For detailed platform capabilities, constraints, and evidence sources, see:
- `Microsoft Foundry/research.md` — full capability inventory, technical limits, and use case patterns
- `Templates/platform-comparison.md` — side-by-side comparison with Copilot Studio

## What Microsoft Foundry Is
An engineering-grade AI platform for building, evaluating, deploying, and operating custom AI agents and models. Owned and operated by engineering teams with structured release governance.

## When The Decision Tree Routes Here
The tree routes to Microsoft Foundry when:
- Deep model/runtime/evaluation control IS mandatory in this phase (Q3.1 = YES).
- A named engineering owner is confirmed for platform operations (Q4.1 = YES).
- The organization does NOT also need business-facing copilots in the same phase (Q4.2 = NO).
- Foundry prerequisites are confirmed (Q1.1 = YES for Foundry path).

OR via Gate 6:
- Primary need is engineering-led with custom orchestration (Q6.3 = YES).

## Prerequisites (Used in Q1.1)
- Azure subscription exists and is accessible.
- Foundry RBAC is assignable.
- Target region, model, and features are available (verify via region support docs and quota portal).
- Named engineering owner for post-launch operations.
- Baseline governance and security plan exists.

## What "Deep Control" Looks Like That Routes Here (Used in Q3.1)
- Customer must select, compare, or switch between foundation models (GPT-5 series, o3, DeepSeek, etc.).
- Customer must run structured evaluation pipelines before model release (batch eval, graders, AI Red Teaming).
- Customer must control orchestration logic at code level (SDK in Python/C#/JS/Java, MCP).
- Customer must enforce custom SLOs on model inference (latency, throughput, error rates, PTU).
- Customer must implement custom tool/API integration that cannot use prebuilt connectors.
- Customer must have programmatic multi-agent routing with custom delegation logic.

If the customer provides a concrete example matching any of the above, Q3.1 = YES.

## What Foundry Provides
- Model catalog with selection and deployment control (Global Standard, DataZone Standard, Provisioned).
- Evaluation framework with datasets, graders, quality gates, and AI Red Teaming Agent.
- Custom agent orchestration with tool integration (128 tools max).
- Foundry IQ for managed knowledge retrieval.
- Observability: tracing, monitoring dashboards, and production trace export.
- RBAC, networking (VNet/private endpoints), and audit controls.
- Fine-tuning pipelines (SFT, DPO, RFT) with dataset curation from traces.
- Structured release governance.
- Foundry Control Plane for managing agents at scale and enforcing token limits.
- Foundry Local for free on-device development.
- MCP Server integration for tool interoperability.
- 30+ regions including sovereign clouds.

## Caution Signals (For Facilitator Awareness, Not Decision Override)
- No named engineering owner despite deep control claims.
- Customer cannot provide a concrete deep-control example.
- Timeline requires immediate broad rollout with limited engineering staffing.
- Organization has no prior platform engineering capacity.

These signals do not change tree routing. They inform follow-up actions.

## Red Flags (Indicate Decision May Be Wrong)
- Engineering owner named but has not confirmed capacity → Q4.1 may have been answered incorrectly.
- Customer's deep control example is actually satisfiable by Copilot Studio → Q3.1 may have been answered incorrectly.
- Azure subscription does not exist → Q1.1 should have eliminated this path.

If a red flag is observed post-decision, the reviewer should challenge the specific worksheet answer.
