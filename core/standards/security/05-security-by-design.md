# Standard: Security by Design

**Source:** OS spec §14 (Security, Governance and Responsible AI)

## Principle
Security is addressed during design, not bolted on before deployment. The spec names five concrete areas; every solution design should address the ones relevant to it explicitly, not by omission.

## Rule
For any solution involving these areas, the design must state how each applicable one is handled:
1. **Identity** — authentication, role-based access control, appropriate MFA.
2. **Data** — classification, encryption, tenant isolation, retention, backup and restore.
3. **AI security** — prompt-injection controls, sensitive-data leakage prevention, output validation, tool boundaries, human approval for high-impact actions.
4. **Application security** — API security, dependency management, secret scanning, rate limiting, secure defaults.
5. **Operations** — audit logging, incident response, monitoring and recovery.

## Claude Code must
- Address the relevant area(s) above explicitly during ARCHITECT / SPECIFY, not defer them to a post-hoc "SECURITY REVIEW" afterthought — the lifecycle's Security Review gate (see `CLAUDE.md`) checks that this happened, it isn't where security design starts.
- Flag any AI-facing feature (prompt construction, tool-calling, agent with external effects) for prompt-injection and tool-boundary consideration specifically, not just generic app security.
- Treat unaddressed areas as an open gap to record, not silently skip.

## Claude Code must not
- Treat security as complete because a dependency scanner or linter passed — the five areas above are broader than tooling output.
- Design a tool-calling or agent capability without defining its permission boundary (see `core/standards/governance/06-human-in-the-loop.md`).

## Related
`core/standards/security/10-secrets-management.md`, `core/standards/security/16-client-data-protection.md`, `core/standards/governance/06-human-in-the-loop.md`
