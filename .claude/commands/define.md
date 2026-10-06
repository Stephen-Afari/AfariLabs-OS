---
description: Run AfariLabs Requirements Definition — turn the discovery brief into complete, verifiable requirements.
argument-hint: <project-id-or-name>
---

# /define

Runs the **requirements-analysis** skill for the **DEFINE** lifecycle stage. Human-supervised: drafts a requirements document for review. Does not design architecture or write code.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Locate the discovery output from `/discover` (`../../outputs/<project-id>/discover/` or the project's own repo).
2. **Load the skill.** Invoke the Skill tool with `requirements-analysis` and follow its Process.
3. **Check standards.** Read `../../core/standards/governance/01-business-outcome-first.md` and `../../core/standards/governance/02-process-before-technology.md`.
4. **Inspect existing context.** Confirm a discovery brief exists; if not, stop and suggest running `/discover` first rather than inventing a business problem.
5. **Produce structured output.** Use `../../templates/requirements/`. Write to `../../outputs/<project-id>/define/` (or the project's own repo, if it exists).
6. **Record decisions.** Any scope decision (what's explicitly out of scope) is recorded as part of the requirements document itself, per `../../core/standards/governance/09-auditability.md`.
7. **Report back.** Summarize functional and non-functional requirements, scope boundaries, acceptance criteria, and any open questions blocking `/assess` or `/architect`.

## Permission boundary
- READ (discovery output, standards, skill): automatic.
- WRITE (the requirements document): proceed, but show the user what was written.
- EXECUTE / DESTRUCTIVE: out of scope.

## Human approval
Requirements are a draft until a human confirms them — per the spec's quality gate, "requirements complete" must be signed off before `/architect` treats them as final.

## Stops and asks when
- No discovery output exists for this project and the business problem/success criteria aren't otherwise stated.
- A requirement can't be made specific/verifiable without information only a human has.

## Related
- Skill: `../skills/requirements-analysis/SKILL.md`
- Standards: `../../core/standards/governance/01-business-outcome-first.md`, `../../core/standards/governance/02-process-before-technology.md`, `../../core/standards/governance/18-documentation.md`
- Template: `../../templates/requirements/`
- Previous: `/discover` · Next: `/assess`
