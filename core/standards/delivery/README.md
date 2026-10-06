# Delivery Standards

Holds AfariLabs' agreed delivery standards: the standard project lifecycle (Discover → Define → Assess → Architect → Specify → Build → Validate → Test → Security Review → Human Acceptance → Demonstrate → Deploy → Monitor → Handover → Learn) and its quality gates.

The full quality-gate checklist for each lifecycle stage is recorded in `CLAUDE.md` ("Standard Project Lifecycle and Quality Gates"), not duplicated here, to avoid two sources of truth drifting apart.

## Standards

- [`13-production-readiness.md`](13-production-readiness.md) — a solution is not done at deployment; monitoring, recovery and support must be in place, not just planned.
- [`14-monitoring.md`](14-monitoring.md) — a deployed solution is actively watched: logging, health checks, alerts, backup/restore, rollback, and incident management.

Further delivery standards should be written once the Desta Cold Store pilot has exercised the lifecycle at least once.

Related: `core/standards/quality/`, `capabilities/delivery/`, `projects/registry/`.
