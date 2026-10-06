---
name: testing-qa
description: Validate implementation against specification and run tests before a solution passes the VALIDATE/TEST lifecycle gates. Use after BUILD, before SECURITY REVIEW.
---

# Testing and QA

## Purpose
Validate that the implementation matches what was specified and that tests pass, as a required gate before SECURITY REVIEW and HUMAN ACCEPTANCE (spec §12).

## When to Use
- At the VALIDATE and TEST lifecycle stages, after BUILD (Automation/Application/AI Engineering) is complete.

## Inputs
- The built solution.
- The requirements document and architecture it was built against.

## Process
1. Validate: check the implementation against what was specified — does it do what the requirements and architecture said it would?
2. Test: execute tests covering the solution's core behavior, including realistic failure scenarios, not just the happy path.
3. For AI-involving solutions, confirm `../ai-evaluation/SKILL.md` has run separately — testing and AI evaluation are both required, neither substitutes for the other.
4. Record what was tested and the result as a durable artifact — not just a one-time local run.
5. Flag any deviation from the original requirements/architecture discovered during validation rather than silently accepting it.

## Outputs
- A validation record: does the implementation match the specification, with any deviations noted.
- Test results, recorded per `../../../templates/testing/`.

## Quality Criteria
- Tests cover realistic failure modes, not only the happy path.
- The validation record states explicitly whether the implementation matches specification.
- Results are recorded as an artifact, not just reported verbally.

## Failure Conditions
- A solution proceeds to SECURITY REVIEW without recorded test results.
- "Implementation validated" is claimed without actually checking against the specification.
- An AI feature's testing is treated as a substitute for `../ai-evaluation/SKILL.md`.

## Related AfariLabs Standards
- `../../../core/standards/quality/12-testing.md`
- `../../../core/standards/quality/07-ai-evaluation.md`
- `../../../core/standards/governance/09-auditability.md`

## Related Templates
- `../../../templates/testing/`
