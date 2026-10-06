# Standard: AI Evaluation

**Source:** OS spec §13 (AI Evaluation & Quality Engineering) — "AI evaluation is a formal production gate, not merely a development activity."

## Principle
An AI-driven feature does not reach production without being evaluated against measurable quality criteria first. Evaluation is a gate, not an optional nicety.

## Rule
1. Before an AI feature (a prompt, model, agent, or workflow involving an LLM) is deployed, it goes through: Gold Dataset → Prompt/Model/Workflow Version → Automated Evaluation → Human/LLM-as-Judge Review → Scorecard → Approve/Improve/Reject.
2. The relevant metrics from this set are measured, as applicable to the feature: accuracy, grounding/citation correctness, hallucination rate, structured-output validity, tool-call accuracy, prompt stability, confidence calibration, task completion rate, reasoning trajectory coherence, latency, failure rate, human override rate, cost per execution.
3. Specific pass/fail thresholds for these metrics are not defined by this standard or the spec — they must be set per-project against that project's actual requirements, not invented generically.

## Claude Code must
- Identify which of the above metrics are applicable before building an AI feature, and plan how each will be measured.
- Require a gold dataset (even a small one) and a scorecard before recommending an AI feature as production-ready.
- Flag an AI feature as not production-ready if it has not been evaluated, rather than assuming a passing vibe check is sufficient.

## Claude Code must not
- Invent a specific pass/fail threshold (e.g. "95% accuracy") without that number coming from an actual project requirement or stakeholder decision.
- Treat a model or prompt's good performance on a handful of ad hoc manual tests as equivalent to a gold-dataset evaluation.

## Related
`templates/evaluation/`, `core/standards/quality/08-structured-outputs.md`, `core/standards/quality/12-testing.md`
