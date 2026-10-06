# Standards

AfariLabs' foundational engineering standards, derived directly from the OS specification. Each is written to be practical enough for Claude Code (or any AI agent) to apply during real project work — not aspirational prose. See each subdirectory's README for the full list with summaries.

| # | Standard | Area |
|---|---|---|
| 1 | [Business Outcome First](governance/01-business-outcome-first.md) | governance |
| 2 | [Process Before Technology](governance/02-process-before-technology.md) | governance |
| 3 | [Simplest Viable Architecture](architecture/03-simplest-viable-architecture.md) | architecture |
| 4 | [Deterministic Workflow vs. Agent Decision](architecture/04-deterministic-workflow-vs-agent-decision.md) | architecture |
| 5 | [Security by Design](security/05-security-by-design.md) | security |
| 6 | [Human-in-the-Loop](governance/06-human-in-the-loop.md) | governance |
| 7 | [AI Evaluation](quality/07-ai-evaluation.md) | quality |
| 8 | [Structured Outputs](quality/08-structured-outputs.md) | quality |
| 9 | [Auditability](governance/09-auditability.md) | governance |
| 10 | [Secrets Management](security/10-secrets-management.md) | security |
| 11 | [Environment Separation](security/11-environment-separation.md) | security |
| 12 | [Testing](quality/12-testing.md) | quality |
| 13 | [Production Readiness](delivery/13-production-readiness.md) | delivery |
| 14 | [Monitoring](delivery/14-monitoring.md) | delivery |
| 15 | [Knowledge Capture](governance/15-knowledge-capture.md) | governance |
| 16 | [Client Data Protection](security/16-client-data-protection.md) | security |
| 17 | [Brand Consistency](governance/17-brand-consistency.md) | governance |
| 18 | [Documentation](governance/18-documentation.md) | governance |
| 19 | [Git / Version Control](governance/19-git-version-control.md) | governance |
| 20 | [Machine Independence](governance/20-machine-independence.md) | governance |

Each standard follows the same shape: Principle (why, sourced from the spec), Rule (the concrete policy), "Claude Code must" / "Claude Code must not" (actionable behavior), and Related links. None introduce content beyond what the OS specification states or directly implies — where the spec leaves a number undefined (e.g. a test coverage threshold or evaluation pass rate), the standard says so explicitly rather than inventing one.

These sit beneath `core/constitution/CONSTITUTION.md`, which holds the small set of foundational, rarely-changing principles; these 20 standards are the practical, applied layer derived from it.
