---
description: Run AfariLabs Process & AI Opportunity Assessment — map the current process fully and prioritize automation/AI opportunities.
argument-hint: <project-id-or-name>
---

# /assess

Runs the **process-assessment** skill (completion) and the **ai-opportunity-assessment** skill for the **ASSESS** lifecycle stage. Human-supervised: drafts a prioritized opportunity roadmap for review. Does not select a final architecture.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Locate `/discover` and `/define` output.
2. **Load the skills.** Invoke the Skill tool with `process-assessment` to complete the full process map, then `ai-opportunity-assessment` to identify, assess and prioritize opportunities — follow each skill's Process in order.
3. **Check standards.** Read `../../core/standards/governance/01-business-outcome-first.md`, `../../core/standards/governance/02-process-before-technology.md`, and `../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md` (for the deterministic-vs-agent framing used when assessing feasibility).
4. **Inspect existing context.** Check `../../knowledge/patterns/` and `../../knowledge/domains/` for comparable prior assessments before starting from scratch.
5. **Produce structured output.** Use `../../templates/process-assessment/`. Write to `../../outputs/<project-id>/assess/` (or the project's own repo).
6. **Record decisions.** The prioritization decision (what's recommended first, and why) is recorded per `../../core/standards/governance/09-auditability.md`.
7. **Report back.** Summarize the process map, the ranked opportunity list with feasibility/risk/value, and the recommended next step.

## Permission boundary
- READ: automatic.
- WRITE (the assessment document): proceed, but show the user what was written.
- EXECUTE / DESTRUCTIVE: out of scope. This command never implements any opportunity it identifies.

## Human approval
The "process assessment completed" quality gate requires human sign-off before `/architect` proceeds. Prioritization is a recommendation, not a committed decision, until confirmed.

## Stops and asks when
- No requirements/discovery context exists for this project.
- A value estimate would require data the assessment doesn't have — flag as an open question rather than inventing a number.

## Related
- Skills: `../skills/process-assessment/SKILL.md`, `../skills/ai-opportunity-assessment/SKILL.md`
- Standards: `../../core/standards/governance/01-business-outcome-first.md`, `../../core/standards/governance/02-process-before-technology.md`, `../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`
- Template: `../../templates/process-assessment/`
- Previous: `/define` · Next: `/architect`
