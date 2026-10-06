---
description: Run AfariLabs Demonstration — prepare a verified, brand-consistent demo of the working solution.
argument-hint: <project-id-or-name>
---

# /demonstrate

Runs the **demonstration** skill (and **brand-experience** for visual assets) for the **DEMONSTRATE** lifecycle stage. Human-supervised: prepares demo materials for review. Does not perform the live demo itself or alter the solution.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Confirm Human Acceptance has occurred (or is explicitly being bypassed by the user's instruction) before preparing a demo — don't demo an unaccepted solution as if it were final.
2. **Load the skills.** Invoke the Skill tool with `demonstration`, and `brand-experience` if visual assets (slides, recordings) are needed.
3. **Check standards.** Read `../../core/standards/governance/17-brand-consistency.md` and `../../core/standards/governance/18-documentation.md`.
4. **Inspect existing context.** Gather the actual test (`/test`), evaluation (`/evaluate`), and security review (`/security-review`) results to cite — every claim made in the demo must trace to one of these.
5. **Produce structured output.** Build demo materials using `../../templates/demonstration/`, referencing `../../brand/` for all visual assets. Write to `../../outputs/<project-id>/demonstrate/` (or the project's own repo).
6. **Record decisions.** If the demo reveals a limitation that needs disclosing, record it rather than smoothing over it.
7. **Report back.** Summarize what will be shown, what claims are backed by which artifact, and any known limitation to disclose during the demo.

## Permission boundary
- READ (test/evaluation/security results, brand kit): automatic.
- WRITE (demo materials): proceed, but show the user what was written.
- EXECUTE / DESTRUCTIVE: out of scope. This command prepares materials; it does not run a live client session or alter the solution.

## Human approval
Demo materials are reviewed by a human before being shown to a client — this command does not send, present, or publish anything externally.

## Stops and asks when
- No verified test/evaluation/security artifacts exist to back the claims a demo would make.
- The solution hasn't passed Human Acceptance and the user hasn't explicitly said to proceed anyway.

## Related
- Skills: `../skills/demonstration/SKILL.md`, `../skills/brand-experience/SKILL.md`
- Standards: `../../core/standards/governance/17-brand-consistency.md`, `../../core/standards/governance/18-documentation.md`
- Template: `../../templates/demonstration/`
- Previous: Human Acceptance (manual) · Next: Deploy/Monitor (manual — no command; then `/handover`)
