---
name: automation-engineering
description: Build event-driven automation and integration solutions (APIs, webhooks, n8n workflows) from an approved architecture. Use at the BUILD stage for Automation Engineering studio work.
---

# Automation Engineering

## Purpose
Build reliable, monitored automation: APIs, webhooks, n8n workflows, integrations and event-driven automation (spec §4, Automation Engineering studio).

## When to Use
- At the BUILD lifecycle stage, for work architected as automation (deterministic workflows, integrations, triggers) rather than an application or AI capability.

## Inputs
- Approved architecture (`../solution-architecture/SKILL.md` output).
- Target systems/APIs and their credentials (via the secrets convention, never inline).

## Process
1. Confirm the architecture called for a deterministic workflow, not an agent (`../../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`).
2. Build the integration/workflow against the approved design; keep credentials out of workflow definitions (`../../../core/standards/security/10-secrets-management.md`).
3. Build in reliability: retries, error handling, and failure visibility — not just the happy path.
4. Build in monitoring hooks appropriate to the solution (`../../../core/standards/delivery/14-monitoring.md`).
5. Test the workflow against realistic inputs and failure scenarios (`../testing-qa/SKILL.md`).

## Outputs
- A working automation/integration matching the approved architecture.
- Test results for the workflow (happy path + failure handling).
- Monitoring/alerting configuration appropriate to the solution's production-readiness needs.

## Quality Criteria
- The workflow handles failure explicitly (retries, dead-letter handling, alerting) rather than failing silently.
- No credential is hardcoded into the workflow definition.
- Behavior matches the approved architecture; deviations are flagged, not silently introduced.

## Failure Conditions
- A workflow is deployed without error handling for predictable failure modes (API timeout, bad input, rate limiting).
- A secret is embedded directly in a workflow definition or node configuration.
- Monitoring is deferred to "add later" for a production-bound workflow.

## Related AfariLabs Standards
- `../../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`
- `../../../core/standards/security/10-secrets-management.md`
- `../../../core/standards/delivery/14-monitoring.md`
- `../../../core/standards/quality/12-testing.md`

## Related Templates
- `../../../templates/architecture/`
- `../../../templates/testing/`
