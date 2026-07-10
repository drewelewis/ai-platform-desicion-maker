# Copilot Studio — Platform Research

> This document is reference material for GitHub Copilot and consultants. It documents what Copilot Studio can and cannot do, based on public Microsoft documentation. It is used to answer decision tree questions accurately.
>
> **Last refreshed: 2026-07-10**

## What Copilot Studio Is

Microsoft Copilot Studio is a low-code platform for creating AI-powered conversational agents and automated flows. It enables business users and citizen developers to build, test, and deploy agents without writing code. Agents built in Copilot Studio can be published to Microsoft Teams, websites, mobile apps, Facebook, and other channels supported by Azure Bot Service. It also supports building standalone automation flows (Agent Flows and Workflows).

Source: https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio (updated 2026-05-07)

## Core Capabilities

### Conversational AI and Orchestration
- **Generative orchestration** (default for new agents) — agent uses AI to autonomously select tools, topics, child/connected agents, and knowledge sources to respond to user queries or event triggers
- **Classic orchestration** — topic-based dialog with trigger phrase matching (still available)
- Multi-intent query handling (agent can chain multiple tools/topics in sequence)
- Entity extraction and slot filling
- Multi-turn conversation with context retention
- Automatic question generation for missing tool/topic inputs
- Autonomous response to event triggers

### Knowledge Grounding
- SharePoint sites and pages (up to 25 site URLs with generative orchestration; modern pages only)
- Dataverse tables (up to 2 sources, 15 tables per source)
- Public websites (crawled)
- Uploaded files (Word, PDF, PowerPoint, Excel — up to 512 MB per file, 500 files)
- OneDrive files and folders (up to 1,000 files per source)
- Salesforce and Confluence articles
- ServiceNow and Zendesk articles
- Custom data via connectors
- Up to 500 knowledge sources per agent (across all types)
- Sensitivity label visibility for SharePoint sources

### Agent Composition
- Child agents (agent-to-agent delegation within generative orchestration)
- Connected agents (invoke other published agents)
- Agent selection based on description matching via generative orchestration

### Tools and Actions
- Power Automate cloud flows (triggered from conversation)
- Agent Flows (native flow authoring within Copilot Studio)
- Workflows (new visual designer format, public preview)
- HTTP request actions (call external APIs)
- Connector actions (1000+ prebuilt Power Platform connectors)
- Plugin actions (OpenAI-compatible plugin format)
- Custom tools with description-based selection
- Up to 100 skills per agent
- Adaptive Cards for rich UI responses

### Channels
- Microsoft Teams
- Microsoft 365 Copilot (as a declarative agent / plugin)
- Web chat (embeddable widget)
- Facebook Messenger
- Custom channels via Direct Line API
- Mobile apps via Direct Line
- Dynamics 365 Omnichannel (via ACS channel)

### Security and Governance
- Microsoft Entra ID authentication (including certificate provider)
- Data Loss Prevention (DLP) policies via Power Platform admin center
- Environment-level isolation and environment routing
- Role-based access (Environment Maker, System Administrator)
- Conversation transcript logging
- Customer Managed Keys (CMK) for data at rest
- Audit logs in Microsoft Purview
- Microsoft Sentinel monitoring and alerting
- Customer Lockbox support
- Sensitivity labels for SharePoint knowledge sources
- Security scan before publishing (maker security warnings)
- Autonomous agent governance via data policies (triggers)
- Maker welcome messages for compliance

### Analytics
- Built-in analytics dashboard (sessions, resolution rate, escalation rate, CSAT)
- Topic-level performance metrics
- Conversation transcripts for review
- Power BI integration for custom reporting
- Application Insights integration (configurable via data policy)

## Licensing

| Plan | Billing Model | Key Differences |
|---|---|---|
| Copilot Studio (standalone) | Copilot Credits (message packs); pay-as-you-go also available | Full authoring, all channels, generative AI, all connectors |
| Microsoft 365 Copilot (includes Copilot Studio) | Usage-based within M365 Copilot allocation | Agents published to Teams and M365 Copilot contexts |
| Copilot Studio for Teams plan | Included in select M365 subscriptions | Classic orchestration only, Teams channel only, no premium connectors |
| Pay-as-you-go | Metered per message | No upfront commitment |

Note: Licensing now uses **Copilot Credits** model. Use the [Microsoft Copilot Studio agent usage estimator](https://microsoft.github.io/copilot-studio-estimator/) to forecast consumption.

Source: https://learn.microsoft.com/en-us/microsoft-copilot-studio/requirements-licensing-subscriptions (updated 2026-05-15)

## Technical Constraints (Hard Limits)

| Constraint | Limit | Source |
|---|---|---|
| Knowledge sources per agent | 500 (across all types) | Platform limit |
| Topics per agent | 1,000 (Dataverse environments) | Platform limit |
| Topics per agent (Teams/Dataverse for Teams) | 250 | Platform limit |
| Skills per agent | 100 | Platform limit |
| Trigger phrases per topic | 200 | Platform limit |
| Files uploaded per agent | 500 | Platform limit |
| File upload size | 512 MB per file | Platform limit |
| SharePoint sites (generative orchestration) | 25 site URLs per agent | Platform limit |
| SharePoint lists | Up to 15 lists, 35,000 rows each, 120,000 total | Platform limit |
| Dataverse sources per agent | 2 sources, 15 tables per source | Platform limit |
| OneDrive per source | 1,000 files, 50 folders, 10 subfolder levels | Platform limit |
| Connector payload | 5 MB (450 KB for GCC) | Platform limit |
| Instructions for M365 Copilot agent | 8,000 characters | Platform limit |
| Messages to agent quota | 8,000 RPM per Dataverse environment | Quota (paid plan) |
| Generative AI messages quota | 50–100 RPM / 1,000–2,000 RPH (varies by message packs) | Quota (paid plan) |
| Generative AI messages (M365 Copilot users) | 100 RPM / 2,000 RPH | Quota |
| Generative AI messages (trial/developer) | 10 RPM / 200 RPH | Quota |
| Power Platform requests | 250,000 per 24 hours (standard); 6,000 (Teams plan) | Subscription limit |
| Sessions (Teams plan) | 10 sessions per user per 24 hours across all agents | Platform limit |
| Agents per team (Teams) | 50 | Platform limit |
| Omnichannel message size | 28 KB (ACS channel limit) | Channel limit |
| Supported languages | 20+ languages for authoring; generative orchestration language support per docs | Platform |

Source: https://learn.microsoft.com/en-us/microsoft-copilot-studio/requirements-quotas (updated 2026-07-08)

## What Copilot Studio Cannot Do

These are capabilities that are NOT available in Copilot Studio and require Microsoft Foundry or custom engineering:

1. **Model selection or switching** — You cannot choose between different foundation models. Copilot Studio uses the Azure OpenAI models configured by Microsoft for generative answers and orchestration. (Note: the "Choice of language models" mentioned in docs refers to pro-dev custom solutions built outside the standard Copilot Studio experience.)

2. **Structured evaluation pipelines** — There is no built-in mechanism to run evaluation datasets against the agent before release, compare model outputs, or enforce quality gates on model behavior.

3. **Imperative code-level orchestration** — While generative orchestration uses AI to select tools/topics/agents, you cannot write custom imperative orchestration code that controls how the agent reasons, plans, or sequences tool calls. The orchestration logic is AI-managed, not developer-authored.

4. **Custom SLOs on inference** — You cannot set or enforce specific latency, throughput, or error-rate targets on the underlying model inference. Performance is governed by the platform quotas.

5. **Fine-tuning** — You cannot fine-tune the underlying model. Knowledge grounding, prompt engineering (instructions), and tool descriptions are the available customization mechanisms.

6. **Custom observability** — Platform provides built-in analytics and optional Application Insights integration. You cannot instrument custom telemetry pipelines over raw inference traces or build fully custom monitoring dashboards over model reasoning behavior.

7. **Private networking** — Copilot Studio is a SaaS service. It does not support VNet integration, private endpoints, or customer-managed network isolation at the agent runtime level.

8. **Complex multi-agent orchestration with custom routing** — While Copilot Studio now supports child agents and connected agents via generative orchestration, you cannot build complex multi-agent patterns with custom routing logic, agent-to-agent negotiation, or programmatic delegation decisions. The agent composition is AI-selected based on descriptions, not code-controlled.

## Ideal Use Case Patterns

| Pattern | Why Copilot Studio Fits |
|---|---|
| Employee FAQ / HR assistant | Knowledge grounding over SharePoint/OneDrive, Teams delivery, business-owned updates |
| IT helpdesk triage | Generative orchestration selects appropriate tools/topics, Power Automate ticket creation, Teams channel |
| Customer service front-door | Web chat widget, generative answers, escalation to human agent, Omnichannel integration |
| Sales enablement assistant | CRM connector (Dynamics/Salesforce), conversational data lookup |
| Internal process automation | Agent Flows and Power Automate flows triggered by conversation or events, approval workflows |
| M365 Copilot extension | Declarative agent/plugin extending Microsoft 365 Copilot with domain knowledge |
| Multi-source knowledge agent | Combines SharePoint, Dataverse, ServiceNow, Confluence sources in one agent |
| Autonomous task agent | Event-triggered flows with generative orchestration handling multi-step tool chains |

## When Copilot Studio Is Not The Right Fit

| Signal | Why It Doesn't Fit |
|---|---|
| Customer requires model comparison/selection | Not available — single model, platform-managed |
| Customer requires evaluation pipelines | Not available — no structured eval framework |
| Customer requires imperative code-level orchestration | Generative orchestration is AI-managed — no custom code runtime for orchestration logic |
| Customer requires private networking | SaaS only — no VNet/private endpoint support |
| Customer requires custom SLOs | Platform-managed performance — no custom targets |
| Customer requires complex programmatic multi-agent patterns | Child/connected agents available but AI-selected — no code-controlled routing |
| Customer requires fine-tuning | Not available — prompt engineering and grounding only |
| Customer requires custom model inference monitoring | Built-in analytics and AppInsights only — no raw trace export |

## References
- Product overview: https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio
- Licensing: https://learn.microsoft.com/en-us/microsoft-copilot-studio/requirements-licensing-subscriptions
- Quotas and limits: https://learn.microsoft.com/en-us/microsoft-copilot-studio/requirements-quotas
- Security and governance: https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-and-governance
- Generative orchestration: https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-generative-actions
- Knowledge sources: https://learn.microsoft.com/en-us/microsoft-copilot-studio/knowledge-copilot-studio
- Tools: https://learn.microsoft.com/en-us/microsoft-copilot-studio/add-tools-custom-agent
- Agent usage estimator: https://microsoft.github.io/copilot-studio-estimator/
