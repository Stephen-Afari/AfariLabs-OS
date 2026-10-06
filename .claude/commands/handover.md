---
description: Run AfariLabs Handover — produce complete, accurate handover documentation for the delivered solution.
argument-hint: <project-id-or-name>
---

# /handover

Runs the **documentation** skill for the **HANDOVER** lifecycle stage. Human-supervised: produces a handover package for review. Does not transfer access, credentials, or ownership itself.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Gather all prior-stage artifacts (requirements, architecture, test/evaluation/security results, demo materials).
2. **Load the skill.** Invoke the Skill tool with `documentation` and follow its Process for a handover audience specifically.
3. **Check standards.** Read `../../core/standards/governance/18-documentation.md` and `../../core/standards/governance/09-auditability.md`.
4. **Inspect existing context.** Confirm every claim in the handover package traces to a verified artifact from an earlier stage — do not describe capability that wasn't actually validated.
5. **Produce structured output.** Build the handover package using `../../templates/handover/`. Write to `../../outputs/<project-id>/handover/` (or the project's own repo).
6. **Record decisions.** Mark the handover as accepted only once a human confirms it — record that acceptance per `../../core/standards/governance/09-auditability.md`.
7. **Report back.** Confirm the recipient can actually operate the solution from what's written; list anything still missing (access, credentials, support contact) that handover requires but this command cannot itself provision.

## Permission boundary
- READ (all prior-stage artifacts): automatic.
- WRITE (the handover package): proceed, but show the user what was written.
- EXECUTE / DESTRUCTIVE: out of scope. This command never grants access, rotates credentials, or transfers ownership — those are separate, human-performed actions, consistent with `../../core/standards/security/10-secrets-management.md`.

## Human approval
The "handover accepted" quality gate requires explicit confirmation from the receiving party — this command prepares the package, it does not close the gate itself.

## Stops and asks when
- A prior-stage artifact needed for handover is missing (e.g. no security review on file).
- The handover package would need to include a real credential or secret — stop; credentials are transferred through the project's actual secret-management channel, never written into this document.

## Related
- Skill: `../skills/documentation/SKILL.md`
- Standards: `../../core/standards/governance/18-documentation.md`, `../../core/standards/governance/09-auditability.md`
- Template: `../../templates/handover/`
- Previous: Deploy/Monitor (manual) · Next: `/learn`
