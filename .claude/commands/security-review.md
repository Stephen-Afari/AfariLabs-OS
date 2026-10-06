---
description: Run AfariLabs Security Review — verify identity, data, AI, application and operational security were actually addressed.
argument-hint: <project-id-or-name>
---

# /security-review

Runs the **security-review** skill for the **SECURITY REVIEW** lifecycle stage. Human-supervised: produces a security review record and gap list. Does not fix findings itself and does not touch staging/production.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Locate the architecture document and the actual built implementation.
2. **Load the skill.** Invoke the Skill tool with `security-review` and follow its Process.
3. **Check standards.** Read `../../core/standards/security/05-security-by-design.md`, `../../core/standards/security/10-secrets-management.md`, `../../core/standards/security/11-environment-separation.md`, and `../../core/standards/security/16-client-data-protection.md`.
4. **Inspect existing context.** Check the real implementation (code, config, workflow definitions) directly for secrets, tenant isolation, and tool boundaries — do not rely solely on the architecture document's stated intent.
5. **Produce structured output.** Record findings using `../../templates/security/`. Write to `../../outputs/<project-id>/security-review/` (or the project's own repo).
6. **Record decisions.** Every finding is logged as either "must fix before Human Acceptance" or "tracked, acceptable to defer" — with reasoning, per `../../core/standards/governance/09-auditability.md`.
7. **Report back.** List what was checked, what passed, and every unresolved gap — do not report "passed" if a high-impact gap (secret exposure, missing tenant isolation, unrestricted agent tool access) remains.

## Permission boundary
- READ (implementation, config, architecture): automatic.
- WRITE (the security review record): proceed, but show the user what was written.
- EXECUTE / DESTRUCTIVE: out of scope entirely. This command never remediates a finding itself and never touches staging or production — fixes are a separate, human-directed action.

## Human approval
This gate (spec: "security and data considerations addressed") requires explicit human sign-off before Human Acceptance — this command cannot self-certify the review as passed.

## Stops and asks when
- The implementation can't be located to review directly.
- A finding's severity is ambiguous and the deferral decision needs a human call.

## Related
- Skill: `../skills/security-review/SKILL.md`
- Standards: `../../core/standards/security/05-security-by-design.md`, `../../core/standards/security/10-secrets-management.md`, `../../core/standards/security/11-environment-separation.md`, `../../core/standards/security/16-client-data-protection.md`
- Template: `../../templates/security/`
- Previous: `/test` (or `/evaluate`) · Next: Human Acceptance (manual — no command; then `/demonstrate`)
