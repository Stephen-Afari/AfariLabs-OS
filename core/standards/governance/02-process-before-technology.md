# Standard: Process Before Technology

**Source:** OS spec §2 ("Process transformation before automation selection"), §11 (map current process, identify bottlenecks, assess feasibility before selecting a solution)

## Principle
Understand and map the current process before selecting automation or AI. Automating a broken process produces a faster broken process.

## Rule
1. Before proposing an automation/AI solution, the current process must be understood well enough to name: the steps involved, where the bottleneck or repetitive work actually is, and who/what is affected.
2. Prefer fixing or simplifying a process over automating it as-is, when both are viable.
3. Process understanding doesn't need to be a formal document for small internal tasks — but for anything feeding a project (see `templates/process-assessment/`), it must be captured, not assumed.

## Claude Code must
- When asked to automate or add AI to a workflow, first ask (or verify from existing artifacts) what the current process actually is, not just what the desired automated end-state looks like.
- Surface it explicitly if the "automation" being requested would just encode an inefficient process faster.

## Claude Code must not
- Jump directly to solution design from a one-line automation request without any process context, when that context materially affects the design.
- Assume a process based on how a similar process usually works elsewhere — verify or ask.

## Related
`templates/process-assessment/`, `core/standards/governance/01-business-outcome-first.md`
