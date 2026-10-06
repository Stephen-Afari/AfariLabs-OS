# Standard: Knowledge Capture

**Source:** OS spec §17 (Knowledge and Pattern Memory)

## Principle
Project outcomes compound into reusable agency knowledge, but only through a deliberate review step — not every observation automatically becomes permanent AfariLabs knowledge.

## Rule
1. Promotion chain: PROJECT → BUILD/DELIVER → PROBLEM OR INSIGHT → LESSON CANDIDATE → PATTERN REVIEW/VALIDATION → PATTERN → SKILL/STANDARD → BETTER FUTURE PROJECT.
2. A pattern record captures: pattern_id, name, capability, version, status, validation history, confidence, problem, context, architecture, implementation, strengths, failure modes, when not to use, proven implementations, lessons, and related patterns.
3. Promotion into `knowledge/patterns/` requires review and validation — a lesson candidate is not a pattern until reviewed.
4. Client-confidential information is never promoted without authorization and sanitization (see `core/standards/security/16-client-data-protection.md`).

## Claude Code must
- Capture a lesson (`knowledge/lessons/`) when a project surfaces a genuine problem or insight, even before it's validated as a pattern.
- Apply the review/validation step before treating something as a reusable AfariLabs pattern — don't promote a one-off observation directly to `knowledge/patterns/`.
- Sanitize and generalize any client-originated insight before it enters `knowledge/`.

## Claude Code must not
- Skip capturing a lesson because it reflects something that "didn't work" — negative/failure lessons are as valuable as positive ones.
- Treat `knowledge/` as a dumping ground for unreviewed raw project output.

## Related
`knowledge/README.md`, `core/standards/security/16-client-data-protection.md`
