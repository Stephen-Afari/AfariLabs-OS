---
name: ai-engineering
description: Build LLM/agent-based capabilities (prompts, structured outputs, RAG, guardrails) from an approved architecture, with evaluation planned in from the start. Use at the BUILD stage for AI Engineering studio work.
---

# AI Engineering

## Purpose
Build AI capabilities — LLM-based features, agents, structured outputs, RAG, guardrails, confidence scoring, human-in-the-loop, model routing (spec §4, AI Engineering studio).

## When to Use
- At the BUILD lifecycle stage, for work architected as an AI/LLM capability, including any agent justified under `../solution-architecture/SKILL.md`.

## Inputs
- Approved architecture, including the deterministic-vs-agent justification.
- Requirements, including any stated quality/accuracy expectations.

## Process
1. Define the output schema for any AI output consumed programmatically before writing the prompt/pipeline (`../../../core/standards/quality/08-structured-outputs.md`).
2. Define tool boundaries and human-approval checkpoints for any agent with external effects (`../../../core/standards/security/05-security-by-design.md`, `../../../core/standards/governance/06-human-in-the-loop.md`).
3. Build the capability; validate structured outputs against the schema, handling validation failure explicitly.
4. Hand off to `../ai-evaluation/SKILL.md` before considering the capability production-ready — do not self-certify quality.
5. Track model, token usage, latency and cost as built (spec §16), not as an afterthought.

## Outputs
- A working AI capability matching the approved architecture.
- A defined output schema and validation logic, where applicable.
- Cost/latency instrumentation sufficient for evaluation and ongoing monitoring.

## Quality Criteria
- No AI output feeding another system is unvalidated against a schema.
- Every agent-like component has a defined tool boundary and approval checkpoint.
- The capability has not been declared production-ready without going through `../ai-evaluation/SKILL.md`.

## Failure Conditions
- An agent is given unrestricted tool access with no defined boundary.
- AI output is passed to a downstream system without validation.
- A capability ships to production without evaluation (`../../../core/standards/quality/07-ai-evaluation.md`).

## Related AfariLabs Standards
- `../../../core/standards/quality/08-structured-outputs.md`
- `../../../core/standards/quality/07-ai-evaluation.md`
- `../../../core/standards/security/05-security-by-design.md`
- `../../../core/standards/governance/06-human-in-the-loop.md`

## Related Templates
- `../../../templates/architecture/`
- `../../../templates/evaluation/`
