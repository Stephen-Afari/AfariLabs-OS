# Standard: Auditability

**Source:** OS spec §26 ("Every completed pilot capability must leave an auditable artifact: decision, test, evaluation, implementation record or lesson"), §14 (audit logging)

## Principle
Meaningful work leaves a trace. A capability, decision, or production action that leaves no record cannot be reviewed, learned from, or trusted later.

## Rule
1. Every completed capability (a feature built, a decision made, an evaluation run, a production action taken) leaves at least one of: a decision record, a test result, an evaluation scorecard, an implementation record, or a lesson entry.
2. The artifact lives in the appropriate place: `core/decision-records/` (control-plane decisions), `knowledge/decisions/` or `knowledge/lessons/` (project-derived, once validated), or the originating project's own repository.
3. Production systems log actions taken (spec §14, §15) — this is an operational requirement for any deployed solution, not just a control-plane one.

## Claude Code must
- After completing a meaningful milestone, state explicitly what was created, what remains, what was learned, and what should change in the OS (spec §26, Claude Execution Rule 12) — this is itself the audit trail for control-plane work.
- Point to or create the relevant artifact (decision record, lesson, test result) rather than letting a significant decision or action go unrecorded.

## Claude Code must not
- Treat a verbal/chat-only explanation as a substitute for a durable artifact when the decision or action is significant enough to matter later.
- Silently skip recording a gap or limitation discovered during work — record it (spec: "Record gaps rather than hiding them").

## Related
`core/decision-records/`, `knowledge/decisions/`, `knowledge/lessons/`
