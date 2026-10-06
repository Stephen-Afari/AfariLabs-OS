---
name: ai-opportunity-assessment
description: Identify and prioritize automation/AI opportunities from a process assessment, with feasibility, risk and value estimates. Use after Process Assessment, before Solution Architecture.
---

# AI Opportunity Assessment

## Purpose
Identify automation and AI opportunities from a process assessment, assess their feasibility and risk, estimate value, and prioritize a roadmap (spec §11).

## When to Use
- After `../process-assessment/SKILL.md` has produced a process map and bottleneck list.
- Before committing to a specific solution architecture or technology.

## Inputs
- The process map and bottleneck/repetitive-work list from Process Assessment.
- Any known constraints: budget, risk tolerance, timeline, existing systems.

## Process
1. For each candidate bottleneck, assess: is this better solved by a deterministic workflow, an AI/agent capability, or a process change with no technology at all (`../../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`)?
2. Assess feasibility: data availability, system access, technical complexity.
3. Assess risk: what happens if this fails, how reversible is it, does it touch client/production data.
4. Estimate value: time saved, error reduction, revenue/cost impact — grounded in the process assessment, not invented.
5. Prioritize into a roadmap, ranking by value-to-risk/effort ratio, not by what's most technically interesting (`../../../core/standards/governance/01-business-outcome-first.md`).

## Outputs
- A prioritized list of automation/AI opportunities, each with feasibility, risk, and estimated value.
- A recommendation of which opportunity to pursue first and why.

## Quality Criteria
- Every opportunity traces to a specific bottleneck identified in Process Assessment.
- Risk and feasibility are stated honestly, including for the agency's own preferred/favorite opportunities.
- Value estimates are labeled as estimates, not guaranteed outcomes.

## Failure Conditions
- An opportunity is recommended that wasn't grounded in the actual process assessment.
- Risk is understated to make an opportunity look more attractive.
- A technologically interesting but low-value opportunity is prioritized over a higher-value, plainer one (spec §24: "do not build technology merely because it is interesting").

## Related AfariLabs Standards
- `../../../core/standards/governance/01-business-outcome-first.md`
- `../../../core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`

## Related Templates
- `../../../templates/process-assessment/`
- `../../../templates/proposal/`
