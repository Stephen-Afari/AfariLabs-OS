# CLAUDE.md — AfariLabs-OS Operating Instructions

This file governs how Claude (and any other AI agent) must operate inside the **AfariLabs-OS** repository. AfariLabs-OS is the **control plane** of AfariLabs: it holds reusable agency intelligence — standards, skills, agents, commands, patterns, templates, governance and tool/MCP policy. It is separate from execution-plane repositories (e.g. `AfariLabs-PMRaid`, `AfariLabs-Desta-Cold-Store`) where client and product applications actually live.

Authoritative source: `AfariLabs AI Engineering & Delivery OS v1.1 — Desta Cold Store Pilot` (see `/Reference` alongside this repository). Where this file and the specification differ, the specification governs; raise the discrepancy rather than silently resolving it.

## What AfariLabs Is

AfariLabs is an AI-native digital solutions agency and product studio. Its durable asset is not a particular technology (n8n, Claude, React, Node.js) — it is the **agency capability system**: standards, reusable skills, controlled agents, proven patterns, delivery methods, commercial methods, knowledge and quality controls.

## Strategic Design Principles

- Capabilities first, technologies second.
- Business outcomes first, AI models second.
- Process transformation before automation selection.
- Controlled autonomy with explicit permissions and approval gates.
- Compounding knowledge: projects produce validated lessons and reusable patterns.
- Domain intelligence + technology knowledge + delivery knowledge = AfariLabs IP.
- Content is a first-class capability, not an afterthought.
- The agency OS is separate from individual applications.
- Human accountability for high-impact architecture, security and production actions.
- Production readiness includes monitoring, recovery and support — not deployment alone.
- AI solutions must be evaluated against measurable quality criteria before production.
- Build the smallest useful capability first; expand the OS only when real work exposes the need.

## Control Plane vs Execution Plane

- **Control Plane — AfariLabs-OS**: constitution, standards, skills, agents, commands, patterns, templates, governance, evaluation and tool/MCP policy.
- **Execution Plane**: separate project repositories for client or product applications. Substantial applications do not live inside AfariLabs-OS; they consume standards, skills and patterns from it.
- **Commercial & Client Plane**: lead generation through expansion/upsell (see `core/commercial` and `capabilities/client-success`).
- **Delivery & Operations Plane**: build, test, deploy, monitor, incident response, backup, recovery, support and continuous improvement.
- **Learning Engine**: project outcomes converted into lessons, patterns, standards and improved skills (see `knowledge/`).

## Claude Execution Rules

These rules apply to every AI agent operating in this repository:

1. Do not create the entire ecosystem in one step.
2. Before creating a new capability, check whether an existing skill, command, pattern or template already solves the problem.
3. Do not invent requirements, metrics, architecture decisions, credentials, integrations or client facts.
4. When information is missing, record the gap and ask for clarification where the missing information materially affects implementation.
5. Use the simplest architecture that satisfies the requirements.
6. Prefer deterministic workflows over agents when the process is predictable.
7. Use agents when dynamic reasoning, tool selection or context-dependent decisions provide clear value.
8. All high-impact writes, production actions and destructive operations require explicit human approval.
9. Never place secrets in source code, prompts, CLAUDE.md, workflow definitions or generated documentation.
10. Every completed pilot capability must leave an auditable artifact: decision, test, evaluation, implementation record or lesson.
11. Do not promote client-specific information into reusable AfariLabs knowledge unless it has been authorized and sanitized.
12. After each meaningful milestone, report what was created, what remains, what was learned and what should change in the OS.

## Strategic Guardrails

- Do not build technology merely because it is interesting.
- Do not add agents where deterministic workflows are sufficient.
- Do not add MCP integrations without a clear operational need.
- Do not introduce architectural complexity before scale or reliability requires it.
- Do not treat AI output as authoritative without validation where business impact warrants it.
- Do not expose client data across tenants or reusable knowledge without authorization.
- Do not build the AfariLabs Control Centre before the operating system has been proven through real projects.
- Do not turn AfariLabs-OS into a substitute for selling and delivering client work.
- Do not allow the OS to become a documentation exercise disconnected from actual delivery.

## Standard Project Lifecycle and Quality Gates

Every project governed by AfariLabs-OS moves through: **Discover → Define → Assess → Architect → Specify → Build → Validate → Test → Security Review → Human Acceptance → Demonstrate → Deploy → Monitor → Handover → Learn.**

A project does not advance past a gate until the corresponding condition is met:

- Business problem and success criteria defined.
- Process assessment completed.
- Requirements complete.
- Architecture approved.
- Security and data considerations addressed.
- Implementation validated.
- Tests passed.
- AI evaluation passed, where applicable.
- Human approval obtained.
- Deployment completed.
- Post-deployment verification completed.
- Monitoring and recovery procedures active.
- Handover accepted.

These gates are documentation-only at this stage — no automated enforcement exists. Recording whether a gate was met is currently a manual responsibility of whoever is running the project; see `core/standards/governance/README.md` for the open gap this leaves.

## Controlled Agent Architecture — Permission Levels

- **READ** — generally automatic.
- **WRITE** — controlled.
- **EXECUTE** — approval required for high-impact actions.
- **DESTRUCTIVE** — explicit human approval required.

Do not build the full orchestrator before a pilot demonstrates which orchestration is genuinely useful. Begin with controlled manual use of CLAUDE.md, skills and commands, then automate repeated work.

## Deliberately Deferred (do not build yet)

The following are named in the specification but are explicitly deferred until real usage justifies them:

- The full AfariLabs Orchestrator (multi-agent routing across Requirements, Architecture, Engineering, QA, Evaluation, Security agents).
- The AfariLabs Control Centre (project/quality/knowledge dashboard).
- The AfariLabs MCP (`search_patterns()`, `get_project_context()`, etc.).
- The Desta Cold Store application itself (the control plane may reference it as the planned OS validation pilot, but must not build it).

## Brand

All AfariLabs-facing visual assets must use the central AfariLabs Brand Kit under `brand/` rather than inventing new colors, logos or typography. The authoritative color palette is the one defined in `brand/colors/brand-colors.json` (Deep Navy `#0D1B3D`, Bright Cyan `#00B6D1`, Soft Mint `#C6F3E6`, Coral Accent `#FF7A59`, Light Neutral `#F2F4F7`, White `#FFFFFF`) — this supersedes the different palette described inline in the specification document (Section 28). See `brand/README.md` for details.

## Repository Map

See `README.md` for the full directory layout and the purpose of each top-level area.
