# Skills

Reusable knowledge plus a repeatable method (spec Section 7-8: Core, Capability, Technology, Domain and Commercial skills). Skills should be composable and context-selected rather than loading the entire knowledge base into every task.

## The 14 Lifecycle Skills

These cover the minimum high-value steps of the AfariLabs project lifecycle (spec §12, §25 Phase B). Each skill directory contains a `SKILL.md` defining its Purpose, When to Use, Inputs, Process, Outputs, Quality Criteria, Failure Conditions, Related Standards and Related Templates.

| Skill | Lifecycle stage(s) | Studio / area |
|---|---|---|
| [`requirements-analysis`](requirements-analysis/SKILL.md) | DEFINE, SPECIFY | Core |
| [`process-assessment`](process-assessment/SKILL.md) | DISCOVER, ASSESS | Core / Commercial |
| [`ai-opportunity-assessment`](ai-opportunity-assessment/SKILL.md) | ASSESS | Core / Commercial |
| [`solution-architecture`](solution-architecture/SKILL.md) | ARCHITECT | Core |
| [`automation-engineering`](automation-engineering/SKILL.md) | BUILD | Automation Engineering |
| [`application-engineering`](application-engineering/SKILL.md) | BUILD | Application Engineering |
| [`ai-engineering`](ai-engineering/SKILL.md) | BUILD | AI Engineering |
| [`security-review`](security-review/SKILL.md) | SECURITY REVIEW | Security |
| [`ai-evaluation`](ai-evaluation/SKILL.md) | VALIDATE / before production | AI Engineering / Quality |
| [`testing-qa`](testing-qa/SKILL.md) | VALIDATE, TEST | Quality |
| [`documentation`](documentation/SKILL.md) | ongoing, HANDOVER | Core |
| [`demonstration`](demonstration/SKILL.md) | DEMONSTRATE | Experience & Growth |
| [`knowledge-capture`](knowledge-capture/SKILL.md) | LEARN, ongoing | Core |
| [`brand-experience`](brand-experience/SKILL.md) | ongoing (Experience & Growth outputs) | Experience & Growth |

## Scope

This is deliberately the full set for now — not a subset and not a larger catalog. It covers the lifecycle end to end without duplicating coverage. No agents, orchestration, or automatic skill chaining have been built; these are reference methods for a human or Claude Code to apply deliberately at each lifecycle stage (see `CLAUDE.md`, "Deliberately Deferred").

Technology-specific, domain-specific, and commercial (pricing/SOW) skills named in spec §8 are not yet created — they should be added only once real project work (the Desta Cold Store pilot) shows a specific, recurring need for one.
