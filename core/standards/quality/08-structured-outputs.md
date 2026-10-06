# Standard: Structured Outputs

**Source:** OS spec §4 (AI Engineering: "structured outputs"), §13 ("Structured-output validity" as an evaluation metric)

## Principle
When an AI-generated output feeds another system — a workflow, a database write, a tool call, another agent — it must conform to a defined, validated schema. Free-text parsed ad hoc downstream is a reliability risk.

## Rule
1. Any LLM output consumed programmatically (not just displayed to a human) has an explicit schema (JSON schema, typed object, or equivalent).
2. Output is validated against that schema before being used; invalid output is treated as a failure to handle (retry, fallback, or human escalation), not silently coerced.
3. Structured-output validity is tracked as an evaluation metric (see `core/standards/quality/07-ai-evaluation.md`) for any feature relying on it.

## Claude Code must
- Define an explicit schema for any AI output that will be parsed or acted on programmatically, before generating it.
- Validate AI output against its schema and handle validation failure explicitly (don't assume the model always returns well-formed output).
- Prefer provider-native structured-output/tool-calling features over regex-parsing free text, when available.

## Claude Code must not
- Pass raw, unvalidated LLM text output directly into a downstream system write, tool call, or decision without a validation step.
- Treat a schema as optional because "the model usually gets it right" — usually isn't production-ready.

## Related
`core/standards/quality/07-ai-evaluation.md`, `capabilities/ai/`
