---
name: ai-evaluation
description: Run an AI capability through the gold-dataset evaluation pipeline and produce a scorecard before it is treated as production-ready. Use before any AI feature ships.
---

# AI Evaluation

## Purpose
Evaluate an AI capability against measurable quality criteria before it is treated as production-ready — a formal gate, not an optional check (spec §13).

## When to Use
- Before any AI/LLM-driven capability built via `../ai-engineering/SKILL.md` is considered production-ready.
- Whenever a prompt, model, or workflow version changes materially, to re-evaluate.

## Inputs
- The AI capability (prompt/model/workflow version) to evaluate.
- A gold dataset — representative inputs with known-correct or acceptable outputs. If none exists, building one is the first step, not an optional extra.

## Process
1. Identify which metrics from `../../../core/standards/quality/07-ai-evaluation.md` apply: accuracy, grounding, hallucination rate, structured-output validity, tool-call accuracy, prompt stability, confidence calibration, task completion rate, reasoning trajectory coherence, latency, failure rate, human override rate, cost per execution.
2. Run the capability against the gold dataset; record results per metric.
3. Run human or LLM-as-judge review for anything automated scoring can't fully capture (tone, correctness nuance).
4. Produce a scorecard summarizing results against each applicable metric.
5. Decide: Approve / Improve / Reject — with the reasoning recorded, not just the verdict.
6. Record using `../../../templates/evaluation/`.

## Outputs
- A gold dataset (new or reused).
- A scorecard with per-metric results.
- An Approve/Improve/Reject decision with reasoning.

## Quality Criteria
- The gold dataset is representative of real expected inputs, not a handful of easy cases.
- Pass/fail thresholds used are ones that came from an actual project requirement, not invented generically (`../../../core/standards/quality/07-ai-evaluation.md`).
- The scorecard is a durable artifact, not a verbal "it looked good."

## Failure Conditions
- A capability is marked production-ready based on informal spot-checking instead of a scorecard.
- A threshold is invented without grounding in a real requirement.
- Evaluation is skipped because the capability "already passed testing" — testing and evaluation check different things (`../testing-qa/SKILL.md`).

## Related AfariLabs Standards
- `../../../core/standards/quality/07-ai-evaluation.md`
- `../../../core/standards/quality/08-structured-outputs.md`

## Related Templates
- `../../../templates/evaluation/`
