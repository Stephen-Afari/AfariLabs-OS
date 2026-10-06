# Standard: Client Data Protection

**Source:** OS spec §24 ("Do not expose client data across tenants or reusable knowledge without authorization"), §17 ("Client-confidential information must not be promoted into reusable knowledge without appropriate authorization and sanitization"), §14 (tenant isolation)

## Principle
Client-confidential information stays scoped to its originating client/project unless explicitly authorized and sanitized for reuse. This is the hard boundary between a project's execution-plane repository and this control plane's `knowledge/` directory.

## Rule
1. Nothing identifiable to a specific client (names, data, credentials, proprietary process detail) is promoted into `knowledge/patterns/`, `knowledge/lessons/`, `knowledge/decisions/`, or any other control-plane location without explicit authorization and sanitization first.
2. A "lesson" or "pattern" extracted from client work must be generalized — the reusable insight, not the client's specific data or identity.
3. Multi-tenant solutions must enforce tenant data isolation by design (see `core/standards/security/05-security-by-design.md`), not by convention.

## Claude Code must
- Treat any client-identifying detail encountered during project work as confidential by default; ask before including it in anything bound for `knowledge/` or `outputs/`.
- Strip client names, data samples, and proprietary specifics when writing up a lesson or pattern — capture the generalizable insight only.
- Flag (not silently proceed) if a request would promote client-specific content into reusable AfariLabs knowledge without stated authorization.

## Claude Code must not
- Copy real client data into `knowledge/`, templates, demos, or marketing content as an example, even sanitized-looking, without confirmed authorization.
- Assume authorization because a lesson "seems generic enough" — the authorization step is required, not optional.

## Related
`knowledge/README.md`, `core/standards/governance/15-knowledge-capture.md`
