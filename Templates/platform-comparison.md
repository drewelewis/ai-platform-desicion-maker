# Platform Comparison — Copilot Studio vs Microsoft Foundry

> This document provides a direct capability comparison to help consultants and GitHub Copilot answer decision tree questions. Each row maps to a specific decision tree question or criterion.
>
> **Last refreshed: 2026-07-10**

## Side-by-Side Comparison

| Capability | Copilot Studio | Microsoft Foundry | Decision Tree Relevance |
|---|---|---|---|
| **Model selection** | Single model (platform-managed Azure OpenAI) | Extensive catalog: GPT-4.1, GPT-5 series, o1/o3/o4, DeepSeek, Meta, Mistral, model-router | Q3.1: Deep control |
| **Model evaluation** | Not available | Batch eval, custom graders, quality gates, continuous eval, AI Red Teaming Agent | Q3.1: Deep control |
| **Fine-tuning** | Not available | SFT, DPO, RFT with dataset curation from traces | Q3.1: Deep control |
| **Orchestration** | Generative orchestration (AI-selected tools/topics/agents) + classic topic designer | Code-level SDK orchestration (Python, C#, JS, Java) + MCP Server | Q3.1: Deep control |
| **Custom SLOs** | Platform-managed, no custom targets | Custom monitoring, alerting, autoscaling, PTU for guaranteed throughput | Q3.1: Deep control |
| **Multi-agent patterns** | Child/connected agents via generative orchestration (AI-selected) | Programmatic agent-to-agent delegation with custom routing logic | Q3.1: Deep control |
| **Private networking** | Not available (SaaS) | VNet integration, private endpoints | Q2.2: Day-1 controls |
| **Teams channel** | One-click publish | Requires Bot Framework integration | Q5.1: M365/Teams usage |
| **M365 Copilot extension** | Native declarative agent/plugin | Not native (API-based integration) | Q5.1: M365/Teams usage |
| **Business user authoring** | Yes (visual designer, no code) | No (requires developer skills) | Q5.2: Business ownership |
| **Change without engineering** | Yes (topic/knowledge/instruction edits) | No (code deployment required) | Q5.2: Business ownership |
| **Prebuilt connectors** | 1000+ Power Platform connectors | Custom tool code only | Integration complexity |
| **Knowledge sources** | SharePoint, Dataverse, OneDrive, Salesforce, Confluence, ServiceNow, Zendesk, files, websites (up to 500 sources) | Custom RAG pipelines + Foundry IQ | Knowledge architecture |
| **Time to first value** | Days to weeks | Weeks to months (Foundry Local enables faster prototyping) | Timeline assessment |
| **Ongoing operations owner** | Business team (admin model) | Engineering team (platform SRE model) | Q2.1: Named owner type |
| **RBAC** | Power Platform roles (Environment Maker, Admin) | Azure RBAC (granular resource-level) | Q2.2: Day-1 controls |
| **Audit logging** | Conversation transcripts, DLP, Microsoft Purview, Sentinel | Azure Monitor, custom telemetry, traces | Q2.2: Day-1 controls |
| **Data residency** | Geography-based (Microsoft-managed) | Region-specific deployment (30+ regions, sovereign clouds) | Q2.2: Day-1 controls |
| **Cost model** | Copilot Credits / message packs (predictable) | Per-token + compute + networking (variable); quota tiers auto-scale | Budget planning |
| **Prerequisite complexity** | M365 tenant + license | Azure subscription + RBAC + region/model availability | Q1.1: Prerequisites |
| **Local development** | Test chat panel only | Foundry Local (free on-device LLMs) + full SDK | Developer experience |
| **Batch processing** | Not available | Up to 100K requests/file, global and datazone batch | Scale patterns |

## Decision Tree Question Mapping

### Q1.1 — Prerequisites
- **Copilot Studio requires**: M365 tenant, Copilot Studio license, named business owner
- **Foundry requires**: Azure subscription, RBAC assignment capability, target region/model/feature availability, named engineering owner

### Q3.1 — Deep Control Mandatory?
If the customer needs ANY of these, the answer is YES (routes to Foundry):
- Choose or compare models → Foundry has model catalog with GPT-5 series, o3, DeepSeek, etc.; Copilot Studio does not
- Run evaluation before release → Foundry has eval framework + AI Red Teaming; Copilot Studio does not
- Imperative code-level orchestration → Foundry has SDK (4 languages) + MCP; Copilot Studio has AI-managed generative orchestration only
- Custom SLOs → Foundry supports custom monitoring + PTU; Copilot Studio does not
- Custom API tools beyond prebuilt connectors → Foundry requires code but supports arbitrary tools; Copilot Studio limited to connector ecosystem
- Fine-tune a model → Foundry supports SFT/DPO/RFT; Copilot Studio does not
- Programmatic multi-agent routing → Foundry supports code-controlled delegation; Copilot Studio only AI-selected child/connected agents

If the customer's needs are satisfied by ALL of these, the answer is NO (routes to Copilot):
- Generative answers over documents/sites
- AI-orchestrated tool and topic selection
- Child/connected agent composition (AI-selected)
- Standard connector integrations
- Business-owned content and instruction updates
- Teams/M365 channel delivery

### Q5.1 — 80% M365/Teams Usage
- Copilot Studio: native Teams publish, native M365 Copilot extension
- Foundry: requires Bot Framework integration for Teams, not native

### Q5.2 — Business Teams Own Changes
- Copilot Studio: visual designer, no code required, business admin model
- Foundry: all changes require code deployment, engineering team required

## Overlap Zone (Both Can Partially Address)

| Scenario | Copilot Studio Approach | Foundry Approach |
|---|---|---|
| Knowledge-grounded Q&A | Generative answers over SharePoint/OneDrive/Salesforce/files (up to 500 sources) | Custom RAG pipeline with Foundry IQ or custom retrieval |
| API integration | Power Automate flows / HTTP actions / plugins / Agent Flows | Custom tool functions in agent code |
| Multi-agent composition | Child/connected agents (AI-selected by description) | Programmatic agent-to-agent delegation (code-controlled) |
| Authentication | Entra ID SSO (built-in, including certificate auth) | Entra ID via managed identity (configured) |
| Content safety | Platform-managed filters | Configurable content safety filters per deployment |
| Conversation logging | Built-in transcripts + Purview + Sentinel | Custom telemetry via App Insights + traces |
| Autonomous actions | Event-triggered flows with generative orchestration | Custom agent loops with tool calls |
| Local testing | Test chat panel in authoring studio | Foundry Local (full model on device) |

In the overlap zone, the decision tree differentiates based on WHO OWNS IT (business vs engineering) and HOW MUCH CONTROL IS REQUIRED (platform-managed vs customer-configured).

## References
- Copilot Studio docs: https://learn.microsoft.com/en-us/microsoft-copilot-studio/
- Microsoft Foundry docs: https://learn.microsoft.com/en-us/azure/ai-foundry/
- Power Platform connectors: https://learn.microsoft.com/en-us/connectors/connector-reference/
- Bot Framework: https://learn.microsoft.com/en-us/azure/bot-service/
- Foundry quotas: https://learn.microsoft.com/en-us/azure/ai-services/openai/quotas-limits
- Copilot Studio quotas: https://learn.microsoft.com/en-us/microsoft-copilot-studio/requirements-quotas
