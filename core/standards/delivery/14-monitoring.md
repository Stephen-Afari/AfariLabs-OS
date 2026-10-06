# Standard: Monitoring

**Source:** OS spec §15 (Production Operations & Reliability)

## Principle
A deployed solution is actively watched, not just left running. The DEPLOY → MONITOR → DETECT → RESPOND → RECOVER → LEARN loop is the baseline operating model for anything in production.

## Rule
For any production solution, the applicable items from this list are in place:
1. Application logging
2. Workflow monitoring
3. AI usage and cost monitoring (for AI-involving solutions)
4. Uptime and health checks
5. Error tracking
6. Alerts
7. Backup and restore
8. Rollback procedures
9. Incident management process
10. Post-incident learning (feeding back into `knowledge/lessons/`)

## Claude Code must
- Identify which of the above apply to a given solution during ARCHITECT/SPECIFY, not as an afterthought post-deployment.
- Treat an incident as incomplete until a post-incident lesson is captured (see `core/standards/governance/15-knowledge-capture.md`), not just resolved.
- Track AI cost/usage explicitly for any solution with recurring model calls (spec §16: "Track cost per workflow, project and client").

## Claude Code must not
- Deploy a solution with externally-facing or business-critical impact without at minimum logging and basic health checks in place.
- Treat "no alerts yet" as evidence of health rather than as evidence that alerting isn't configured.

## Related
`core/standards/delivery/13-production-readiness.md`, `core/standards/governance/15-knowledge-capture.md`
