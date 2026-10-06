---
description: Run AfariLabs Specification — finalize the build-ready spec by combining approved requirements and architecture.
argument-hint: <project-id-or-name>
---

# /specify

Finalizes the build-ready specification for the **SPECIFY** lifecycle stage, combining `requirements-analysis` output with the approved `solution-architecture` output. Human-supervised: drafts the final spec for review. Does not begin BUILD.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Locate approved `/define` and `/architect` output — do not proceed if the architecture hasn't been approved (see Human approval below).
2. **Load the skills.** Invoke the Skill tool with `requirements-analysis` to refine any remaining ambiguity now that architecture is known, referencing `solution-architecture` output for consistency.
3. **Check standards.** Read `../../core/standards/governance/01-business-outcome-first.md`, `../../core/standards/architecture/03-simplest-viable-architecture.md`, `../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`, `../../core/standards/security/05-security-by-design.md`, and — if the solution involves AI output feeding other systems — `../../core/standards/quality/08-structured-outputs.md`.
4. **Inspect existing context.** Reconcile the requirements and architecture documents; flag any contradiction between them rather than silently resolving it.
5. **Produce structured output.** Combine into a single build-ready spec using `../../templates/requirements/` and `../../templates/architecture/` structures. Write to `../../outputs/<project-id>/specify/` (or the project's own repo).
6. **Record decisions.** Any change made to requirements or architecture during reconciliation is recorded per `../../core/standards/governance/09-auditability.md`.
7. **Report back.** Confirm the spec is internally consistent and ready to hand to the appropriate BUILD skill (`automation-engineering`, `application-engineering`, or `ai-engineering` — chosen manually by a human, not by this command).

## Permission boundary
- READ: automatic.
- WRITE (the finalized spec): proceed, but show the user what was written.
- EXECUTE / DESTRUCTIVE: out of scope. This command never starts BUILD itself.

## Human approval
This command assumes architecture has already been approved (per `/architect`'s gate). The finalized spec itself is a draft handoff artifact — a human decides when BUILD actually starts and which engineering skill/studio picks it up.

## Stops and asks when
- Architecture has not been approved yet for this project.
- Requirements and architecture contradict each other in a way that can't be resolved without a human decision.

## Related
- Skills: `../skills/requirements-analysis/SKILL.md`, `../skills/solution-architecture/SKILL.md`
- Standards: as listed above
- Templates: `../../templates/requirements/`, `../../templates/architecture/`
- Previous: `/architect` · Next: BUILD (manual — no command; then `/validate`)
