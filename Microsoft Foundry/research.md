# Microsoft Foundry — Platform Research

> This document is reference material for GitHub Copilot and consultants. It documents what Microsoft Foundry (formerly Azure AI Foundry) can and cannot do, based on public Microsoft documentation. It is used to answer decision tree questions accurately.
>
> **Last refreshed: 2026-07-10**

## What Microsoft Foundry Is

Microsoft Foundry is "the AI app and agent factory" — an enterprise platform for building, optimizing, deploying, and governing custom AI agents and models at scale. It provides engineering teams with full control over model selection, evaluation pipelines, orchestration logic, and production operations. It is accessed via the Foundry portal (ai.azure.com), Microsoft Foundry SDKs (Python, C#, JavaScript, Java), Azure Developer CLI (azd), and VS Code extension.

Source: https://learn.microsoft.com/en-us/azure/ai-foundry/ (updated 2026-06-16)

## Core Capabilities

### Model Catalog and Selection (Foundry Models)
- Access to extensive model catalog from Microsoft/OpenAI, Meta, Mistral, Cohere, DeepSeek, and open-source providers
- Models include GPT-4.1, GPT-5 through GPT-5.6 variants, o1, o3, o3-pro, o4-mini, codex-mini, model-router, image models, audio/realtime models
- Model comparison and benchmarking tools
- Serverless API deployment (pay-per-token, no infrastructure management)
- Managed compute deployment (dedicated capacity, custom scaling)
- Provisioned Throughput Units (PTU) for guaranteed capacity
- Deployment types: Global Standard, DataZone Standard, Standard, Provisioned
- Model versioning and lifecycle management
- Foundry Models sold directly by Azure vs. Models from partners and community

### Agent Development (Foundry Agent Service)
- Hosted agent runtime (Azure-managed execution environment)
- Prompt agents (quick creation via portal)
- Agent definition via agent.yaml configuration
- Custom tool integration (function calling, API tools, code interpreter, file search)
- Multi-turn conversation with state management
- Prompt management and versioning
- Agent Optimizer for automated instruction tuning
- Deploy and share agents at scale
- Up to 128 tools per agent
- Up to 10,000 files per assistant/thread

### Foundry IQ
- Knowledge base service for agents
- Connect knowledge bases to agents for grounded responses
- Managed retrieval and indexing

### Evaluation and Observability
- Batch evaluation with custom datasets
- Built-in graders (relevance, coherence, groundedness, fluency, safety)
- Custom grader authoring
- Continuous evaluation (production monitoring with automated quality checks)
- A/B comparison between model versions or configurations
- Evaluation history and regression tracking
- AI Red Teaming Agent (preview) for adversarial testing
- Tracing for multi-step agent executions
- Azure Monitor integration with dashboards
- Custom telemetry via Application Insights
- Token usage tracking and cost attribution
- Inference latency monitoring
- Production trace export for evaluation dataset curation

### Fine-Tuning
- Supervised Fine-Tuning (SFT)
- Direct Preference Optimization (DPO)
- Reinforcement Fine-Tuning (RFT)
- Dataset curation from production traces
- Training job management and monitoring (up to 3 concurrent standard jobs, 5 developer jobs)
- Fine-tuned model deployment and versioning
- Maximum training job size: 2 billion tokens
- Maximum file size: 512 MB (API) / 200 MB (portal)
- Up to 100 training jobs per resource, 100 files per resource, 1 GB total

### Orchestration
- Code-level orchestration via Microsoft Foundry SDK (Python, C#, JavaScript, Java)
- Custom tool/function definitions
- Multi-agent patterns (agent-to-agent delegation)
- Semantic Kernel integration
- LangChain integration
- Custom reasoning and planning logic
- MCP Server integration (Model Context Protocol)
- Azure Developer CLI (azd) for agent development lifecycle
- Foundry Skill for coding agents (VS Code)

### Foundry Control Plane
- Manage agents at scale
- Enforce token limits for models
- Quota management and monitoring
- Trustworthy AI governance
- Content Safety integration (configurable filters)

### Security and Governance
- Azure RBAC (role-based access control at project/resource level)
- Virtual network integration and private endpoints
- Customer Managed Keys (CMK)
- Content safety filters (configurable per deployment)
- Azure Policy integration
- Audit logging via Azure Monitor
- Data residency controls (region-specific deployment)
- Managed identity for service-to-service auth
- Available in 30+ regions globally including sovereign clouds (US Gov Virginia, US Gov Arizona)

### Foundry Local
- Run LLMs on local devices for free
- Integrate with apps via inference SDKs
- Run HuggingFace models locally
- Development and testing without cloud costs

### Deployment and Operations
- Azure Developer CLI (azd) integration for CI/CD
- Bicep/ARM template support
- Blue-green deployment patterns
- Autoscaling (managed compute)
- SLA-backed uptime (dependent on deployment type and SKU)
- Multi-region deployment
- Batch processing (up to 100K requests per file, 200 MB per file, 1 GB with BYOS)
- Global batch and DataZone batch options

## Licensing and Pricing

| Component | Pricing Model |
|---|---|
| Serverless API (pay-per-token) | Per 1K input/output tokens, varies by model |
| Managed compute | Per-hour compute cost (VM-based) |
| Provisioned Throughput Units (PTU) | Reserved capacity, per-unit pricing |
| Fine-tuning | Per-hour training compute + hosted model cost |
| Evaluation | Included in compute/token costs for eval runs |
| Storage | Standard Azure Storage rates for datasets/artifacts |
| Networking | Standard Azure networking rates for VNet/private endpoints |
| Foundry Local | Free (runs on local hardware) |

**Quota Tiers:** 7 tiers (Free/Tier 0 through Tier 6) with automatic upgrades based on consumption. Enterprise Agreement (EA/MCA-E) customers are assigned higher tiers. Customers can opt out of auto-upgrades. Example Tier 1 quotas: GPT-5 GlobalStandard = 10,000 RPM / 1M TPM; GPT-4.1-mini GlobalStandard = 5,000 RPM / 5M TPM.

Source: https://azure.microsoft.com/en-us/pricing/details/ai-foundry/

## Technical Constraints (Hard Limits)

| Constraint | Limit | Source |
|---|---|---|
| Azure OpenAI resources per region per subscription | 30 | Platform limit |
| Maximum standard deployments per resource | 32 | Platform limit |
| Maximum fine-tuned model deployments | 10 | Platform limit |
| Agent tools per agent | 128 tools maximum | Platform limit |
| Files per assistant or thread | 10,000 | Platform limit |
| File size (API / Portal) | 512 MB / 200 MB | Platform limit |
| Total uploaded files for assistants | 200 GB | Platform limit |
| Assistants token limit | 2,000,000 tokens | Platform limit |
| Chat completions messages | 2,048 | Platform limit |
| Chat completions tools | 128 | Platform limit |
| Embeddings inputs per request | 2,048 | Platform limit |
| Embeddings tokens per request | 300,000 | Platform limit |
| Training jobs per resource | 100 | Platform limit |
| Concurrent training jobs | 3 (standard/global) / 5 (developer) | Platform limit |
| Training files per resource | 100 (max 1 GB total) | Platform limit |
| Max training job time | 720 hours | Platform limit |
| Max training job size | 2 billion tokens | Platform limit |
| Batch input file size | 200 MB (1 GB with BYOS) | Platform limit |
| Batch requests per file | 100,000 | Platform limit |
| GPT-4o images per request | 50 | Platform limit |
| Message character limit | 1,048,576 | Platform limit |
| Quota tiers | Free (Tier 0) through Tier 6; auto-upgrades based on consumption | Subscription level |
| Tokens per minute (example) | GPT-5 GlobalStandard Tier 1: 1M TPM; Tier 6: 45M TPM | Quota tier dependent |
| Private endpoint provisioning | Standard Azure networking provisioning time | Azure infrastructure |

Source: https://learn.microsoft.com/en-us/azure/ai-services/openai/quotas-limits (updated 2026-06-05)

## What Microsoft Foundry Cannot Do

These are capabilities that are NOT available in Foundry and may require Copilot Studio or other solutions:

1. **Low-code visual agent authoring** — There is no drag-and-drop visual conversation designer. Agent logic is defined in code (SDK) or configuration (agent.yaml). Business users without development skills cannot author or modify agents independently.

2. **Native M365/Teams channel publishing** — Foundry agents are accessed via API endpoints. Publishing to Teams as a native bot requires additional integration work (Bot Framework, Azure Bot Service). It is not a one-click publish like Copilot Studio.

3. **Prebuilt Power Platform connectors** — Foundry does not have access to the 1000+ Power Platform connectors. API integrations must be built as custom tools using code.

4. **Business-user self-service updates** — Content and configuration changes require engineering deployment cycles. There is no self-service portal for non-technical users to update agent behavior, knowledge, or instructions.

5. **Built-in conversation analytics** — There is no prebuilt analytics dashboard for conversation metrics (resolution rate, CSAT, etc.). Monitoring requires custom instrumentation via Azure Monitor/Application Insights.

6. **Zero-infrastructure getting started** — Foundry requires Azure subscription setup, resource provisioning, RBAC configuration, and (for production) networking setup. It is not a turnkey SaaS experience. (Note: Foundry Local allows free local development but production still requires Azure infrastructure.)

## Ideal Use Case Patterns

| Pattern | Why Foundry Fits |
|---|---|
| Custom AI agent with tool use | Full control over tools, orchestration logic, and model behavior |
| Model evaluation and release governance | Batch eval, graders, quality gates, AI Red Teaming before production release |
| Multi-model comparison and selection | Extensive model catalog, benchmarking, A/B testing, model-router |
| RAG with custom retrieval pipeline | Full control over embedding, indexing, retrieval, and ranking logic (plus Foundry IQ) |
| Production AI with strict SLOs | Custom monitoring, autoscaling, PTU for guaranteed capacity, private networking, SLA-backed |
| Fine-tuned domain models | SFT/DPO/RFT pipelines, dataset curation from traces |
| Multi-agent orchestration | Agent-to-agent delegation, custom planning/reasoning, MCP integration |
| Enterprise AI with compliance requirements | VNet isolation, CMK, audit logging, data residency, sovereign clouds |
| High-scale batch processing | Global batch up to 100K requests/file with BYOS support |
| Local development and prototyping | Foundry Local for free on-device LLM development |

## When Microsoft Foundry Is Not The Right Fit

| Signal | Why It Doesn't Fit |
|---|---|
| Business teams must own day-2 changes | No self-service authoring for non-developers |
| Primary channel is Teams with one-click deploy | Requires Bot Framework integration, not native |
| Use case needs only prebuilt connectors | Must build custom tool integrations in code |
| Timeline requires production in 2-4 weeks | Infrastructure setup + engineering build takes longer |
| No engineering team available post-launch | Platform requires ongoing engineering operations |
| Budget does not support platform engineering | Compute, networking, and engineering costs are material |

## References
- Product overview: https://learn.microsoft.com/en-us/azure/ai-foundry/
- What is Foundry: https://learn.microsoft.com/en-us/azure/ai-foundry/what-is-foundry
- Agent development: https://learn.microsoft.com/en-us/azure/ai-foundry/agents/
- Foundry IQ: https://learn.microsoft.com/en-us/azure/ai-foundry/agents/concepts/what-is-foundry-iq
- Evaluation: https://learn.microsoft.com/en-us/azure/ai-foundry/observability/how-to/evaluate-agent
- Fine-tuning: https://learn.microsoft.com/en-us/azure/ai-foundry/openai/how-to/fine-tuning
- Foundry Control Plane: https://learn.microsoft.com/en-us/azure/ai-foundry/control-plane/overview
- Security: https://learn.microsoft.com/en-us/azure/ai-foundry/security/
- Quotas and limits: https://learn.microsoft.com/en-us/azure/ai-services/openai/quotas-limits
- Region support: https://learn.microsoft.com/en-us/azure/ai-foundry/reference/region-support
- Foundry Local: https://learn.microsoft.com/en-us/azure/foundry-local/get-started
- MCP Server: https://learn.microsoft.com/en-us/azure/ai-foundry/mcp/get-started
- SDKs: https://learn.microsoft.com/en-us/azure/ai-foundry/how-to/develop/sdk-overview
- Pricing: https://azure.microsoft.com/en-us/pricing/details/ai-foundry/
- azd integration: https://learn.microsoft.com/en-us/azure/developer/azure-developer-cli/
