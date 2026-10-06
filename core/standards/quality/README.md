# Quality Standards

Holds AfariLabs' agreed quality standards, including AI evaluation criteria and conventional testing gates.

## Standards

- [`07-ai-evaluation.md`](07-ai-evaluation.md) — AI evaluation is a formal production gate: gold dataset → automated evaluation → human/LLM-as-judge review → scorecard → approve/improve/reject.
- [`08-structured-outputs.md`](08-structured-outputs.md) — any AI output consumed programmatically must conform to a validated schema, not be parsed ad hoc from free text.
- [`12-testing.md`](12-testing.md) — implementation is validated and tests pass before advancing past the VALIDATE/TEST lifecycle gates.

Related: `templates/evaluation/`, `templates/testing/`, `knowledge/patterns/`.
