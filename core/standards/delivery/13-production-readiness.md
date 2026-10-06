# Standard: Production Readiness

**Source:** OS spec §2 ("Production readiness includes monitoring, recovery and support—not deployment alone")

## Principle
A solution is not "done" at deployment. Production readiness includes monitoring, recovery procedures, and support being in place — deployment is one of several required conditions, not the finish line.

## Rule
Before a solution is considered production-ready, these are in place, not merely planned:
1. Monitoring (see `core/standards/delivery/14-monitoring.md`).
2. A recovery/rollback procedure for when something breaks.
3. A support path — someone or something responsible for responding when the solution fails.
4. Post-deployment verification that the deployed solution actually works as intended (spec §12 quality gate: "post-deployment verification completed").

## Claude Code must
- Treat "deployed" and "production-ready" as different claims — don't report a solution as production-ready based on deployment success alone.
- Confirm monitoring, recovery and support exist (or explicitly flag them as missing) before recommending a go-live.
- Include hosting, API, automation and monitoring costs in solution economics when assessing production readiness (spec §16), not just the build cost.

## Claude Code must not
- Mark the DEPLOY lifecycle stage as complete without MONITOR being active immediately after (spec §15: DEPLOY → MONITOR → DETECT → RESPOND → RECOVER → LEARN).
- Treat the absence of a rollback procedure as acceptable for a production deployment.

## Related
`core/standards/delivery/14-monitoring.md`, `environments/production/`
