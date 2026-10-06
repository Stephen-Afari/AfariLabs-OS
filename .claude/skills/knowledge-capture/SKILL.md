---
name: knowledge-capture
description: Capture project lessons and, once reviewed and validated, promote them into reusable AfariLabs patterns or standards. Use at the LEARN lifecycle stage and after any significant incident or decision.
---

# Knowledge Capture

## Purpose
Convert project outcomes into lessons, and — only after review and validation — into reusable patterns, skills or standards (spec §17).

## When to Use
- At the LEARN lifecycle stage, at the end of a project or project phase.
- After any significant incident, decision, or discovered gap, not only at project close.

## Inputs
- The problem, insight, or outcome to capture (a success, a failure, a workaround, a decision).
- Any client-specific detail involved, which must be checked against `../../../core/standards/security/16-client-data-protection.md` before anything is written down.

## Process
1. Capture the raw lesson in `../../../knowledge/lessons/` — a problem or insight, even before it's validated as reusable.
2. Strip client-identifying detail; generalize to the reusable insight (`../../../core/standards/security/16-client-data-protection.md`).
3. Apply the review/validation step before promoting a lesson candidate into `../../../knowledge/patterns/` — do not promote directly.
4. For a validated pattern, record: pattern_id, name, capability, version, status, validation history, confidence, problem, context, architecture, implementation, strengths, failure modes, when not to use, proven implementations, lessons, related patterns (`../../../core/standards/governance/15-knowledge-capture.md`).
5. If a pattern matures into something that should change a standard or skill, propose that update explicitly rather than letting it live only as a pattern.

## Outputs
- A lesson entry in `../../../knowledge/lessons/` (always, for anything meaningful).
- A validated pattern in `../../../knowledge/patterns/` (only after review).
- A proposed standard/skill update, where warranted.

## Quality Criteria
- No client-identifying information reaches `../../../knowledge/` without authorization and sanitization.
- A pattern wasn't promoted without the review/validation step.
- Negative/failure lessons are captured as readily as positive ones.

## Failure Conditions
- A raw, unreviewed observation is written directly into `../../../knowledge/patterns/`.
- Client-confidential information is promoted into reusable knowledge without authorization.
- A meaningful failure or gap goes uncaptured because it's unflattering.

## Related AfariLabs Standards
- `../../../core/standards/governance/15-knowledge-capture.md`
- `../../../core/standards/security/16-client-data-protection.md`
- `../../../core/standards/governance/09-auditability.md`

## Related Templates
- (none — outputs go directly into `../../../knowledge/`, not `templates/`)
