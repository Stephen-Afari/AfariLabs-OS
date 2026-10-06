---
description: Run AfariLabs Validation — check the built implementation against the approved specification.
argument-hint: <project-id-or-name>
---

# /validate

Runs the **testing-qa** skill's Validate step for the **VALIDATE** lifecycle stage: does the implementation actually match what was specified? Human-supervised: produces a validation record. Does not modify the implementation or any environment.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Locate the `/specify` output and the built implementation (project's own repo).
2. **Load the skill.** Invoke the Skill tool with `testing-qa` and follow the Validate portion of its Process.
3. **Check standards.** Read `../../core/standards/quality/12-testing.md` and `../../core/standards/governance/09-auditability.md`.
4. **Inspect existing context.** Compare the actual implementation against the finalized spec from `/specify` — read the real code/workflow/config, not just the spec's description of intent.
5. **Produce structured output.** Record findings using `../../templates/testing/`. Write to `../../outputs/<project-id>/validate/` (or the project's own repo).
6. **Record decisions.** Any deviation found between implementation and spec is recorded explicitly — do not silently accept or silently "fix" it as part of this command.
7. **Report back.** State plainly whether the implementation matches the specification, and list every deviation found.

## Permission boundary
- READ (implementation, spec): automatic.
- WRITE (the validation record): proceed, but show the user what was written.
- EXECUTE / DESTRUCTIVE: out of scope. This command never edits the implementation it's validating and never touches staging/production.

## Human approval
A deviation found here is reported, not auto-resolved — a human decides whether to accept it, send it back to BUILD, or update the spec.

## Stops and asks when
- No finalized spec exists to validate against.
- The implementation can't be located (wrong path, project not yet built).

## Related
- Skill: `../skills/testing-qa/SKILL.md`
- Standards: `../../core/standards/quality/12-testing.md`, `../../core/standards/governance/09-auditability.md`
- Template: `../../templates/testing/`
- Previous: BUILD (manual) · Next: `/test`
