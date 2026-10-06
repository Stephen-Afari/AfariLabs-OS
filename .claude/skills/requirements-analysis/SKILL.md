---
name: requirements-analysis
description: Turn a stated business problem into complete, verifiable requirements before architecture or build begins. Use during the DEFINE/SPECIFY lifecycle stages.
---

# Requirements Analysis

## Purpose
Convert a stated business problem and success criteria into complete, specific, verifiable requirements that architecture and build can be based on.

## When to Use
- At the DEFINE and SPECIFY stages of the project lifecycle (spec §12), after the business problem has been confirmed (see `../../../core/standards/governance/01-business-outcome-first.md`).
- Whenever a request arrives as a vague feature ask ("build X") and needs to be turned into something buildable before design starts.

## Inputs
- The stated business problem and success criteria.
- Any process-assessment output already available (`../process-assessment/SKILL.md`).
- Stakeholder/user input — direct, or via existing documents (emails, notes, prior tickets).
- Constraints: budget, timeline, existing systems to integrate with.

## Process
1. Confirm the business outcome and success criteria are stated (do not proceed without them — ask if missing).
2. Decompose the ask into functional requirements (what the system must do) and non-functional requirements (performance, security, availability, compliance).
3. Identify what's explicitly out of scope, not just what's in.
4. Define acceptance criteria for each requirement — how it will be verified as met.
5. Flag ambiguous or missing information as an open question rather than assuming an answer (`../../../core/standards/governance/02-process-before-technology.md` — don't assume a process/need you haven't confirmed).
6. Record the requirements using `../../../templates/requirements/`.

## Outputs
- A requirements document (per `../../../templates/requirements/`) with functional requirements, non-functional requirements, scope boundaries, and acceptance criteria.
- A list of open questions/gaps requiring stakeholder clarification, if any remain.

## Quality Criteria
- Every requirement is specific enough to be verifiably true or false once built.
- Every requirement traces back to the stated business outcome.
- No requirement was invented to fill a gap — gaps are listed as open questions instead.

## Failure Conditions
- Requirements proceed to architecture while materially ambiguous or unconfirmed.
- A requirement exists that doesn't trace to any business outcome.
- Scope boundaries are undefined, leading to scope ambiguity downstream.

## Related AfariLabs Standards
- `../../../core/standards/governance/01-business-outcome-first.md`
- `../../../core/standards/governance/02-process-before-technology.md`
- `../../../core/standards/governance/18-documentation.md`

## Related Templates
- `../../../templates/requirements/`
