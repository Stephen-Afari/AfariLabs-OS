# Standard: Testing

**Source:** OS spec §12 (Standard Project Lifecycle — TEST stage, quality gate "tests passed"; "implementation validated" at VALIDATE)

## Principle
Implementation is validated and tests pass before a solution advances past the VALIDATE/TEST lifecycle gates toward deployment. The spec does not prescribe a specific methodology, coverage number, or framework — those are project-specific decisions, not invented here.

## Rule
1. Every project passes through VALIDATE (implementation checked against what was specified) and TEST (tests executed, results recorded) before SECURITY REVIEW and HUMAN ACCEPTANCE.
2. Test results are a recorded artifact (see `core/standards/governance/09-auditability.md`), not just a one-time local run.
3. AI-involving features are additionally evaluated per `core/standards/quality/07-ai-evaluation.md` — conventional testing and AI evaluation are both required where applicable, not substitutes for each other.

## Claude Code must
- Treat "implementation validated" and "tests passed" as distinct, required lifecycle gates, not implicitly satisfied by code compiling or running once.
- Record what was tested and the result, not just report "tests pass" without an artifact.
- Ask what testing approach/coverage a project actually requires rather than assuming a default (e.g. a specific coverage percentage) that the spec does not define.

## Claude Code must not
- Skip the TEST gate for an AI feature on the grounds that "evaluation already covers it" — evaluation (§13) and testing (§12) check different things.
- Invent a specific testing standard (coverage threshold, required framework) and present it as an AfariLabs standard when it isn't defined in the spec.

## Related
`templates/testing/`, `core/standards/quality/07-ai-evaluation.md`, `CLAUDE.md` (Standard Project Lifecycle and Quality Gates)
