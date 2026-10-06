---
name: solution-architecture
description: Design the simplest viable solution architecture that satisfies confirmed requirements, choosing deterministic workflows over agents unless justified. Use at the ARCHITECT lifecycle stage.
---

# Solution Architecture

## Purpose
Design the simplest architecture that satisfies the confirmed requirements, with security and data considerations addressed from the start.

## When to Use
- At the ARCHITECT lifecycle stage (spec §12), after Requirements Analysis (and, where applicable, Process Assessment / AI Opportunity Assessment) are complete.

## Inputs
- Completed requirements document (`../requirements-analysis/SKILL.md` output).
- Any existing relevant pattern from `../../../knowledge/patterns/` or `../../../knowledge/architectures/`.
- Constraints: existing systems, budget, timeline, team capability.

## Process
1. Check `../../../knowledge/patterns/` and `../../../knowledge/architectures/` for an existing validated approach before designing a new one.
2. For each component, decide: deterministic workflow or agent — justify any agent choice explicitly (`../../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`).
3. Choose the simplest architecture that satisfies the stated requirements; name why any added complexity is necessary (`../../../core/standards/architecture/03-simplest-viable-architecture.md`).
4. Address identity, data, AI security, application security and operations explicitly (`../../../core/standards/security/05-security-by-design.md`).
5. Identify which production studio(s) this falls under (Automation / Application / AI / Experience) and which capability skill picks it up next.
6. Record the architecture using `../../../templates/architecture/`.

## Outputs
- An architecture document (per `../../../templates/architecture/`): components, data flow, technology choices, security considerations, and justification for any complexity or agent use.
- A decision record for any significant architectural choice (`../../../core/decision-records/`).

## Quality Criteria
- Every component's complexity is justified against a stated requirement.
- Security and data considerations are addressed, not deferred.
- The design doesn't duplicate an existing validated pattern without reason.

## Failure Conditions
- Architecture includes an agent or orchestration layer without a stated dynamic-reasoning justification.
- Security/data handling is left unaddressed pending a later "security review."
- The design was approved without reference to confirmed requirements.

## Related AfariLabs Standards
- `../../../core/standards/architecture/03-simplest-viable-architecture.md`
- `../../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`
- `../../../core/standards/security/05-security-by-design.md`

## Related Templates
- `../../../templates/architecture/`
