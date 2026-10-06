# Standard: Documentation

**Source:** OS spec §24 ("Do not allow the OS to become a documentation exercise disconnected from actual delivery"), §18 (content must come from verified project artifacts)

## Principle
Documentation exists to make the control plane and its projects usable and auditable — not as an end in itself. Every meaningful directory explains its purpose; no documentation claims something that isn't true of the actual state.

## Rule
1. Every directory with a distinct purpose has a `README.md` explaining that purpose (as already established across this repository).
2. Documentation reflects actual state — "no content exists yet" is said plainly where true, rather than a README implying capability that hasn't been built.
3. Content generated for external use (case studies, demos, proposals) is built from verified project artifacts — never invented claims, metrics, or implementation details (spec §18).
4. Documentation effort is not a substitute for delivery — don't write extensive docs for a capability that doesn't exist yet "in case it's useful."

## Claude Code must
- Keep a directory's README accurate to its current contents; update it when the contents materially change rather than letting it drift.
- When generating client-facing or portfolio content, cite the specific verified artifact a claim comes from.
- Say "not yet built" / "empty by design" plainly rather than writing around an absence.

## Claude Code must not
- Write a README or spec document describing a capability as if it exists when it's only planned.
- Generate marketing/demo content with a metric or technical claim that wasn't verified against a real project artifact.

## Related
`CLAUDE.md` (Claude Execution Rules), `templates/content/`
