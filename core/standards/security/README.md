# Security Standards

Holds AfariLabs' agreed security standards: identity, data classification/encryption, AI security, application security and operations.

## Standards

- [`05-security-by-design.md`](05-security-by-design.md) — address identity, data, AI security, application security and operations explicitly during design, not as a post-hoc review.
- [`10-secrets-management.md`](10-secrets-management.md) — secrets never enter version control, prompts, or generated documentation.
- [`11-environment-separation.md`](11-environment-separation.md) — development, staging and production stay separate: credentials, data and approval requirements never shared between them.
- [`16-client-data-protection.md`](16-client-data-protection.md) — client-confidential information stays scoped to its originating project unless authorized and sanitized for reuse.

Related: `capabilities/security/`, `core/standards/governance/`.
