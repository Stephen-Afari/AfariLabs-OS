---
description: Run AfariLabs AI Evaluation — score an AI capability against a gold dataset before it is treated as production-ready.
argument-hint: <project-id-or-name>
---

# /evaluate

Runs the **ai-evaluation** skill. Applicable only when the solution includes an AI/LLM capability. Human-supervised: produces a scorecard and an Approve/Improve/Reject recommendation — does not itself authorize production use.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Confirm the solution includes an AI/LLM component; if not, report that this command doesn't apply and stop.
2. **Load the skill.** Invoke the Skill tool with `ai-evaluation` and follow its Process.
3. **Check standards.** Read `../../core/standards/quality/07-ai-evaluation.md` and `../../core/standards/quality/08-structured-outputs.md`.
4. **Inspect existing context.** Check whether a gold dataset already exists for this capability (`../../outputs/<project-id>/evaluate/` or the project's own repo); build one if not, rather than skipping evaluation for lack of one.
5. **Produce structured output.** Run the capability against the gold dataset, score the applicable metrics, and record a scorecard using `../../templates/evaluation/`. Write to `../../outputs/<project-id>/evaluate/` (or the project's own repo).
6. **Record decisions.** The Approve/Improve/Reject decision and its reasoning is recorded as part of the scorecard, per `../../core/standards/governance/09-auditability.md`.
7. **Report back.** Summarize per-metric results and the recommendation, and state explicitly whether thresholds used came from an actual project requirement.

## Permission boundary
- READ (capability, prior scorecards): automatic.
- WRITE (gold dataset additions, scorecard): proceed, but show the user what was written.
- EXECUTE: running the capability against the gold dataset is permitted only in a development/test context, never against live production traffic or data.
- DESTRUCTIVE: out of scope.

## Human approval
An "Approve" recommendation from this command is not itself the production-readiness decision — a human reviews the scorecard and confirms before the capability is treated as production-ready, consistent with `../../core/standards/governance/06-human-in-the-loop.md`.

## Stops and asks when
- The solution has no AI/LLM component (this command doesn't apply).
- A pass/fail threshold is needed but wasn't specified anywhere in the project's requirements — ask rather than inventing one.

## Related
- Skill: `../skills/ai-evaluation/SKILL.md`
- Standards: `../../core/standards/quality/07-ai-evaluation.md`, `../../core/standards/quality/08-structured-outputs.md`
- Template: `../../templates/evaluation/`
- Previous: `/test` · Next: `/security-review`
