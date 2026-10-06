---
name: documentation
description: Produce accurate documentation (technical docs, READMEs, handover material) that reflects actual state and is built from verified artifacts. Use throughout the lifecycle and at HANDOVER.
---

# Documentation

## Purpose
Produce documentation that accurately reflects actual state and is built from verified project artifacts — never invented claims (spec §18, §24).

## When to Use
- Whenever a directory, capability, or project reaches a state that needs explaining (ongoing, not just at the end).
- At the HANDOVER lifecycle stage specifically, for handover documentation.

## Inputs
- The actual current state of the thing being documented (code, architecture, decisions, test/evaluation results).
- The audience: internal (control-plane README), technical (architecture doc), or client-facing (handover doc).

## Process
1. Identify what's actually true right now — don't describe a planned or aspirational state as current.
2. Cite the specific verified artifact behind any factual or technical claim (a test result, an evaluation scorecard, a decision record).
3. Say "not yet built" / "empty by design" plainly where applicable, rather than writing around an absence (`../../../core/standards/governance/18-documentation.md`).
4. Match documentation depth to actual need — don't over-document a capability that doesn't exist yet "in case it's useful."
5. For handover specifically, use `../../../templates/handover/` and ensure the client/recipient can actually operate the solution from what's written.

## Outputs
- Accurate documentation appropriate to the audience and lifecycle stage.
- For handover: a complete handover package per `../../../templates/handover/`.

## Quality Criteria
- Every factual/technical claim traces to a verified artifact.
- Documentation reflects current state, not intended or past state, unless explicitly labeled as such.
- A reader unfamiliar with the work can act on the documentation (especially for handover).

## Failure Conditions
- A README or doc describes a capability as built when it's only planned.
- A technical claim or metric appears in documentation without a verifiable source.
- Handover documentation is incomplete and the recipient can't actually operate the solution.

## Related AfariLabs Standards
- `../../../core/standards/governance/18-documentation.md`
- `../../../core/standards/governance/09-auditability.md`

## Related Templates
- `../../../templates/handover/`
- `../../../templates/content/`
