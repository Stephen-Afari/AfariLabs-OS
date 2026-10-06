---
description: Run AfariLabs Discovery — capture the stated business problem and an initial process picture before any solution is proposed.
argument-hint: <project-id-or-name> [brief context]
---

# /discover

Runs the **process-assessment** skill (initial pass) for the **DISCOVER** lifecycle stage. Human-supervised: drafts a discovery brief for review. Does not propose a solution, does not touch any environment.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. If no match, ask whether this is a new project (and whether to register it in the registry) or an informal/internal exploration — do not silently register a project without confirming.
2. **Load the skill.** Invoke the Skill tool with `process-assessment` and follow its Process for an initial, lightweight pass (full process mapping belongs to `/assess`).
3. **Check standards.** Read `../../core/standards/governance/01-business-outcome-first.md` and `../../core/standards/governance/02-process-before-technology.md` — do not proceed past confirming the stated business problem if it's missing.
4. **Inspect existing context.** Check `../../outputs/<project-id>/` for any prior discovery work, and `../../knowledge/domains/` and `../../knowledge/patterns/` for relevant prior AfariLabs knowledge, before starting fresh.
5. **Produce structured output.** Use `../../templates/discovery/` as the structure. Write to `../../outputs/<project-id>/discover/` (control-plane staging area) unless the project already has its own execution-plane repository, in which case write there and say so.
6. **Record decisions.** If discovery surfaces a significant decision (e.g. "not pursuing this"), record it per `../../core/standards/governance/09-auditability.md`.
7. **Report back.** Summarize the stated business problem, what's known about current process, open questions, and whether `/define` is ready to run next.

## Permission boundary
- READ (registry, standards, skill, existing artifacts): automatic.
- WRITE (the discovery brief): proceed, but show the user what was written.
- EXECUTE / DESTRUCTIVE: out of scope. This command never deploys, never modifies a staging or production environment, never deletes existing artifacts.

## Human approval
The discovery brief is a draft for review — it does not itself authorize moving to `/define`. The business problem and success criteria it captures should be confirmed by a human before requirements work begins.

## Stops and asks when
- `$ARGUMENTS` doesn't identify a project or business problem and it can't be reasonably inferred.
- The business problem is stated only as a technology request ("build me an agent for X") with no underlying outcome given.

## Related
- Skill: `../skills/process-assessment/SKILL.md`
- Standards: `../../core/standards/governance/01-business-outcome-first.md`, `../../core/standards/governance/02-process-before-technology.md`
- Template: `../../templates/discovery/`
- Next: `/define`
