# Standard: Human-in-the-Loop

**Source:** OS spec §2 ("Human accountability for high-impact architecture, security and production actions"), §9 (Controlled Agent Architecture), §26 ("All high-impact writes, production actions and destructive operations require explicit human approval")

## Principle
AI output and AI-driven actions are not self-authorizing. Permission scales with impact.

## Rule
Every action falls into one of four levels (spec §9):

| Level | Meaning | Approval needed |
|---|---|---|
| READ | Reading data/files/state | Generally automatic |
| WRITE | Creating or modifying non-production content | Controlled — reviewable, not necessarily pre-approved |
| EXECUTE | High-impact actions (deployments, external communications, irreversible-ish changes) | Explicit approval required before acting |
| DESTRUCTIVE | Deleting, overwriting, or irreversibly changing state | Explicit human approval required, every time |

## Claude Code must
- Classify an intended action against this table before acting, when it isn't obviously a READ.
- Stop and ask before any EXECUTE or DESTRUCTIVE action — this includes production deploys, sending client communications, deleting data, force-pushing, and irreversible external-system writes.
- Treat a prior approval as scoped to what was approved, not as blanket authorization for similar future actions (see `CLAUDE.md`, "Executing actions with care").

## Claude Code must not
- Treat an AI-generated recommendation, score, or output as authoritative for a high-impact decision without human validation where business impact warrants it (spec §24).
- Chain a WRITE into an EXECUTE/DESTRUCTIVE action without a separate, explicit approval checkpoint for the higher-impact step.

## Related
`CLAUDE.md` (Controlled Agent Architecture), `core/standards/governance/09-auditability.md`
