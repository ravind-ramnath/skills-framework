# Discovery: Platform Foundation and Control Plane

**Status:** Clarified — awaiting review and approval
**Created:** 2026-10-27
**Approved by:** Pending
**Author:** Copilot

## Problem Statement

There is no dedicated platform team, platform, or governance process/framework for creating and overseeing artificial intelligence (AI) and agent workloads. Business engineers therefore cannot build these workloads safely and at scale to optimise business functions and delivery. There is no process or framework to audit agents being built, no platform telemetry or observability, and no controls to measure platform effectiveness or agent delivery. The current workarounds and measurable business cost have not yet been established.

## Who It Affects

**Primary persona — Engineer in an engineering squad:** Tries to build AI and agent workloads to improve business functions and delivery, but lacks a safe, governed platform and cannot establish the expected controls or audit evidence. The resulting impact is reduced or delayed business value and delivery; its scale is not yet measured.

## Why Now

The bank wants to evolve by bringing new products to market ahead of competitors and delivering new functionality faster without sacrificing safety. The absence of a platform foundation, governance, auditability, and observability is a constraint on achieving that ambition at scale.

## Minimum Viable Product (MVP) Scope

The first release is a safe, hardened, governed sandbox that gives engineering teams secure access and supports the full agent lifecycle: build agents with Copilot Studio, Azure AI Foundry, or AWS Bedrock; onboard and govern them through this platform's control plane; test and evaluate them; and promote them to higher environments through an application lifecycle management and continuous integration/continuous delivery process. The agents continue to execute in their provider-managed runtimes; this platform is not a shared agent execution runtime.

The mandatory first-release control baseline is identity and least privilege; named agent ownership and inventory; environment, network, and data boundaries; and audit records and telemetry for every in-scope agent. The control plane must show each agent's owner, provider/model/version, environment, deployment and lifecycle status, health, and usage/cost signals, and record invocation traces, agent decisions/actions, tool/data access, and policy/evaluation outcomes. This does not imply capturing or retaining prompts, responses, or other payloads; payload capture, access, and retention policy require a separate decision before production. The platform must also provide the AI gateway, inference, automation, and integrations needed for the lifecycle; a pre-implementation provider-access and integration-feasibility spike will validate access and establish the provider-specific integration boundaries. Additional control classes raised earlier — dedicated safety evaluation, drift/misuse monitoring, emergency shutdown, token budgets, and resource allocation — are deferred to later phases of the Platform workstream, not mandatory first-release controls. Selection of initial business use cases is outside this workstream's scope; the accountable owner is not yet identified.

## Out of Scope

- Selecting and prioritising business use cases — this workstream provides the platform foundation; business-use-case selection is outside its remit, and the accountable owner is not yet identified.
- Defining and approving Identity and Access Management (IAM), Cyber security, AI risk, and Governance frameworks or policies — those responsibilities belong to the IAM, Cyber, Risk, and Governance workstreams; Platform implements the resulting approved controls.

## Assumptions and Risks

The control and integration design has not yet been validated. The following planning assumption and delivery validation are explicit:

- [PLANNING ASSUMPTION] Provider access is available for planning against Copilot Studio, Azure AI Foundry, and AWS Bedrock; a feasibility spike must validate access and integration surfaces before implementation.
- [CONFIRMED ARCHITECTURE] Agents execute in provider-managed runtimes; the platform provides the common control plane for inventory, governance, observability, and lifecycle promotion.
- [DELIVERY VALIDATION] The required signal set is the target. A feasibility spike must validate signal availability and collection across providers without assuming payload capture. Payload capture, access, and retention policy must be decided separately before production.

The programme is a learning and planning model; no real regulatory obligations or policy frameworks have been asserted.

## Directional Success Indicators

- **Secure agent build-to-execution path:** Baseline: [UNKNOWN BASELINE] — the platform does not yet exist. Target: an engineer can securely sign in to the sandbox, build and deploy an in-scope agent, and execute it. Measured by: a recorded end-to-end verification run.
- **Control-plane visibility and observability:** Baseline: [UNKNOWN BASELINE] — no platform telemetry or control plane exists. Target: every in-scope deployed agent is visible with its owner, provider/model/version, environment, deployment/lifecycle status, health, and usage/cost signals, plus invocation traces, decisions/actions, tool/data access, and policy/evaluation outcomes. Measured by: reconciling the deployed-agent inventory and checking representative trace records against the required signal set; payload capture and retention are not implied.

## Constraints

- The programme target runs from 2026-11-01 to 2027-05-31; phase and workstream milestone dates remain TBD.
- The practice scenario names Copilot Studio, Azure AI Foundry, and AWS Bedrock; provider-specific integration dependencies remain undefined.
- Payload retention, access, and retention-period policy are not yet defined.
- No additional workstream-specific budget, technical, data-handling, or team-capability constraints have been identified.
- This is a learning and planning model. No real bank regulatory obligations, business-data constraints, or approval authorities are asserted; the repository's product context describes the Skills Framework and is not treated as an initiative-specific requirement.

## Contributors

- Ravind Ramnath — Platform Owner — 2026-10-27
- Mo Alwani — Technical Lead — 2026-10-27
- Scott Ford — Product Owner — 2026-10-27
- Debbie Dickson — Business Analyst — 2026-10-27
- Ash Ali — Platform Engineer — 2026-10-27
- Chao Hou — Platform Engineer — 2026-10-27
- Eddie Walsh — Platform Engineer — 2026-10-27
- Tim Broadhurst — Platform Engineer — 2026-10-27
- Will Rumble — Platform Engineer — 2026-10-27
- Rajesh Keshawarni — Quality Engineer — 2026-10-27
- Haritha Ravella — Quality Engineer — 2026-10-27

## Reviewers

- None yet — review is pending.

## Approved By

- Pending — a named individual approval is required before progression to `/benefit-metric`.

---

## /clarify Recommendation

## Clarification log

[2026-10-27] Clarified via /clarify:
- Q: Which controls are mandatory for the first release? A: Identity and least privilege; ownership and inventory; environment, network, and data boundaries; and audit and telemetry.
- Q: Where do agents execute, and what is the platform's role? A: Agents remain in provider-managed runtimes; the platform supplies the common governance and control plane.
- Q: What minimum audit and telemetry signals are required? A: Inventory and action-audit signals, elaborated into the target signal set above and confirmed by the operator.
- Q: Does the target signal set accurately describe visibility and audit requirements without implying payload capture or retention? A: Yes.
- Q: Where should dedicated safety evaluation, drift/misuse monitoring, emergency shutdown, token budgets, and resource allocation be handled? A: Later phases of the Platform workstream.
- Q: How should provider access and integration uncertainty be handled for this planning model? A: Assume access for planning and add a provider-access/integration feasibility spike before implementation.
- Q: How should telemetry feasibility and payload policy be handled? A: The signal set is the target; a spike validates collection across providers without assuming payload capture; payload capture, access, and retention policy are separate decisions before production.
