---
name: application-engineering
description: Build production applications (React, TypeScript, Node/Express, databases, auth, APIs) from an approved architecture. Use at the BUILD stage for Application Engineering studio work.
---

# Application Engineering

## Purpose
Build production applications — React, TypeScript, Node/Express, databases, authentication, APIs, testing and deployment (spec §4, Application Engineering studio).

## When to Use
- At the BUILD lifecycle stage, for work architected as an application (persistent UI/API/data layer) rather than a pure automation workflow or AI capability.

## Inputs
- Approved architecture (`../solution-architecture/SKILL.md` output).
- Requirements document (`../requirements-analysis/SKILL.md` output).

## Process
1. Build against the approved architecture; use the simplest structure that satisfies requirements (`../../../core/standards/architecture/03-simplest-viable-architecture.md`).
2. Implement authentication/authorization and data handling per the security design (`../../../core/standards/security/05-security-by-design.md`).
3. Keep environment-specific config scoped per `../../../core/standards/security/11-environment-separation.md` — no shared credentials across dev/staging/production.
4. Write tests covering the application's core behavior (`../testing-qa/SKILL.md`).
5. Avoid machine-specific assumptions in code or config (`../../../core/standards/governance/20-machine-independence.md`).

## Outputs
- A working application matching the approved architecture and requirements.
- Test results.
- Deployment-ready configuration scoped per environment.

## Quality Criteria
- Core functionality is covered by tests, not just manually verified once.
- No hardcoded secrets or machine-specific paths.
- Authentication/authorization match the security design, not a simplified stand-in left in place.

## Failure Conditions
- A placeholder auth/security mechanism ships to production because "it worked for the demo."
- Environment configuration is hardcoded rather than separated per `environments/`.
- Requirements drift during build without being reflected back into the requirements document.

## Related AfariLabs Standards
- `../../../core/standards/architecture/03-simplest-viable-architecture.md`
- `../../../core/standards/security/05-security-by-design.md`
- `../../../core/standards/security/11-environment-separation.md`
- `../../../core/standards/quality/12-testing.md`
- `../../../core/standards/governance/20-machine-independence.md`

## Related Templates
- `../../../templates/architecture/`
- `../../../templates/testing/`
