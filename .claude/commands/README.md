# Commands

Repeatable procedures for the AfariLabs project lifecycle (spec Section 7, §12, §25 Phase B). Each command is a thin, human-supervised orchestration layer over an already-defined skill (`.claude/skills/`) and standard (`core/standards/`) — it does not contain new judgment logic beyond what those already specify.

## The 12 Lifecycle Commands

| Command | Lifecycle stage | Skill(s) invoked | Previous → Next |
|---|---|---|---|
| [`/discover`](discover.md) | DISCOVER | `process-assessment` | — → `/define` |
| [`/define`](define.md) | DEFINE | `requirements-analysis` | `/discover` → `/assess` |
| [`/assess`](assess.md) | ASSESS | `process-assessment`, `ai-opportunity-assessment` | `/define` → `/architect` |
| [`/architect`](architect.md) | ARCHITECT | `solution-architecture` | `/assess` → `/specify` |
| [`/specify`](specify.md) | SPECIFY | `requirements-analysis`, `solution-architecture` | `/architect` → BUILD (manual) |
| [`/validate`](validate.md) | VALIDATE | `testing-qa` | BUILD (manual) → `/test` |
| [`/test`](test.md) | TEST | `testing-qa` | `/validate` → `/evaluate` or `/security-review` |
| [`/evaluate`](evaluate.md) | (AI quality gate) | `ai-evaluation` | `/test` → `/security-review` |
| [`/security-review`](security-review.md) | SECURITY REVIEW | `security-review` | `/test`/`/evaluate` → Human Acceptance (manual) |
| [`/demonstrate`](demonstrate.md) | DEMONSTRATE | `demonstration`, `brand-experience` | Human Acceptance (manual) → Deploy/Monitor (manual) |
| [`/handover`](handover.md) | HANDOVER | `documentation` | Deploy/Monitor (manual) → `/learn` |
| [`/learn`](learn.md) | LEARN | `knowledge-capture` | `/handover` → end |

BUILD, HUMAN ACCEPTANCE, DEPLOY and MONITOR are deliberately **not** commands — they are human-performed actions (actual engineering work, an explicit approval, a real deployment, ongoing operations) that this command system supports with artifacts but does not automate, consistent with "do not create autonomous execution."

## What every command does

Each command follows the same seven-part structure (per the task that created them):

1. **Loads the appropriate skill(s)** via the `Skill` tool.
2. **Checks relevant standards** in `core/standards/` before producing output.
3. **Inspects existing project context** — the project registry, prior-stage artifacts, and `knowledge/` — before starting fresh.
4. **Produces structured output** using the matching `templates/` structure.
5. **Never modifies a staging or production system automatically** — every command's Permission Boundary section states this explicitly; EXECUTE/DESTRUCTIVE actions are out of scope.
6. **Respects human approval requirements** — each command's Human Approval section states what it cannot self-certify (gate sign-off, pattern promotion, production readiness).
7. **Records important decisions** — into `core/decision-records/`, `knowledge/decisions/`, or the stage's own output record, as appropriate.

## Output location

Structured output from these commands is written to `outputs/<project-id>/<stage>/` by default — this repository's existing staging area for generated, non-authoritative artifacts (see `outputs/README.md`). Once a project has its own execution-plane repository, output should go there instead; each command says so explicitly.

## Status

**Human-supervised only.** No command chains automatically into the next; no command executes against staging or production; no command promotes anything into `knowledge/patterns/` or edits `core/standards/`/`.claude/skills/` on its own. Running all 12 in sequence still requires a human to invoke each one and review its output before the next is appropriate to run.
