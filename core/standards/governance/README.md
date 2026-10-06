# Governance Standards

Holds AfariLabs' agreed governance standards: approval matrix, risk classification, change control, versioning and decision-record practice (see spec Section 14).

The controlled-agent permission model (READ / WRITE / EXECUTE / DESTRUCTIVE, see `CLAUDE.md`) is the current governance baseline.

## Standards

- [`01-business-outcome-first.md`](01-business-outcome-first.md) — no build or technology choice proceeds until the business problem and success criteria are stated.
- [`02-process-before-technology.md`](02-process-before-technology.md) — understand the current process before proposing automation or AI.
- [`06-human-in-the-loop.md`](06-human-in-the-loop.md) — permission scales with impact: READ automatic, WRITE controlled, EXECUTE/DESTRUCTIVE require explicit human approval.
- [`09-auditability.md`](09-auditability.md) — every completed capability leaves a decision, test, evaluation, implementation record, or lesson.
- [`15-knowledge-capture.md`](15-knowledge-capture.md) — project insights become reusable knowledge only after review and validation, never automatically.
- [`17-brand-consistency.md`](17-brand-consistency.md) — all AfariLabs-facing visual assets use the exact values in `brand/`, never approximated.
- [`18-documentation.md`](18-documentation.md) — documentation reflects actual state and is never a substitute for delivery.
- [`19-git-version-control.md`](19-git-version-control.md) — GitHub is the source of truth; secrets never enter it.
- [`20-machine-independence.md`](20-machine-independence.md) — nothing durable depends on machine-specific state; the repository must be recoverable on another machine.

**Known gap (tracked, not yet resolved):** there is currently no format for *recording* that an approval was actually given, or that a quality gate (see `CLAUDE.md`) was actually met — the permission model and gate checklist describe what must happen, but nothing here captures that it did happen. A lightweight approval/decision log is expected to be the first piece of governance content this repository needs, likely triggered by the Desta Cold Store pilot reaching its first EXECUTE or DESTRUCTIVE action. Creating that format is intentionally deferred (Phase B/C, spec Section 25) rather than built speculatively now.

Related: `core/decision-records/`, `CLAUDE.md`.
