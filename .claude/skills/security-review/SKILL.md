---
name: security-review
description: Verify identity, data, AI, application and operational security considerations are actually addressed before human acceptance. Use at the SECURITY REVIEW lifecycle gate.
---

# Security Review

## Purpose
Verify that identity, data, AI security, application security and operations considerations were actually addressed in the built solution — not merely designed for (spec §14, §12 SECURITY REVIEW gate).

## When to Use
- At the SECURITY REVIEW lifecycle stage, after BUILD/VALIDATE/TEST and before HUMAN ACCEPTANCE.
- Any time a solution involves client or production data, external tool access, or an AI agent with real-world effects.

## Inputs
- The architecture document and its stated security design (`../solution-architecture/SKILL.md` output).
- The built solution (code, workflow, or AI capability).

## Process
1. Check each of the five areas from `../../../core/standards/security/05-security-by-design.md` against what was actually built, not just what was designed.
2. Verify no secret is present in code, config, prompts, or documentation (`../../../core/standards/security/10-secrets-management.md`).
3. Verify environment separation was respected — no production credential or data leaked into dev/staging (`../../../core/standards/security/11-environment-separation.md`).
4. Verify client data handling meets `../../../core/standards/security/16-client-data-protection.md`, including tenant isolation if multi-tenant.
5. For AI capabilities, verify prompt-injection controls, tool boundaries, and human-approval checkpoints are actually implemented, not just described.
6. Record findings using `../../../templates/security/`.

## Outputs
- A security review record: what was checked, what passed, what gaps remain.
- A list of any gap that must be fixed before HUMAN ACCEPTANCE, versus one that's acceptable to track and address later.

## Quality Criteria
- Every applicable security area from `05-security-by-design.md` was actually checked against the real implementation.
- No unresolved high-impact gap (secret exposure, missing tenant isolation, unrestricted agent tool access) is waved through.

## Failure Conditions
- A security review is marked passed without checking against the actual built artifact.
- A known gap is left unrecorded instead of flagged.
- An AI capability with unrestricted tool access or no approval checkpoint passes review.

## Related AfariLabs Standards
- `../../../core/standards/security/05-security-by-design.md`
- `../../../core/standards/security/10-secrets-management.md`
- `../../../core/standards/security/11-environment-separation.md`
- `../../../core/standards/security/16-client-data-protection.md`

## Related Templates
- `../../../templates/security/`
