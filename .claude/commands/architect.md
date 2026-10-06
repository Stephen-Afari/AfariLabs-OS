---
description: Run AfariLabs Solution Architecture — design the simplest viable architecture that satisfies confirmed requirements.
argument-hint: <project-id-or-name>
---

# /architect

Runs the **solution-architecture** skill for the **ARCHITECT** lifecycle stage. Human-supervised: drafts an architecture document for review. Does not write implementation code or provision any environment.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Locate `/define` and `/assess` output.
2. **Load the skill.** Invoke the Skill tool with `solution-architecture` and follow its Process.
3. **Check standards.** Read `../../core/standards/architecture/03-simplest-viable-architecture.md`, `../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`, and `../../core/standards/security/05-security-by-design.md`.
4. **Inspect existing context.** Check `../../knowledge/patterns/` and `../../knowledge/architectures/` for an existing validated approach before designing a new one.
5. **Produce structured output.** Use `../../templates/architecture/`. Write to `../../outputs/<project-id>/architect/` (or the project's own repo).
6. **Record decisions.** Any significant architectural choice (especially agent-vs-workflow, or added complexity) is recorded in `../../core/decision-records/` or `../../knowledge/decisions/` with its justification.
7. **Report back.** Summarize the proposed architecture, what pattern (if any) it reused, its security/data considerations, and anything requiring explicit human approval before `/specify`.

## Permission boundary
- READ: automatic.
- WRITE (the architecture document and any decision record): proceed, but show the user what was written.
- EXECUTE / DESTRUCTIVE: out of scope. This command never provisions infrastructure or deploys anything.

## Human approval
The "architecture approved" quality gate requires explicit human sign-off — this command produces the proposal, it does not grant the approval.

## Stops and asks when
- Requirements are incomplete or unconfirmed for this project.
- A component's complexity can't be justified against a stated requirement — flag it rather than including it unexplained.

## Related
- Skill: `../skills/solution-architecture/SKILL.md`
- Standards: `../../core/standards/architecture/03-simplest-viable-architecture.md`, `../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`, `../../core/standards/security/05-security-by-design.md`
- Template: `../../templates/architecture/`
- Previous: `/assess` · Next: `/specify`
