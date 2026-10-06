---
name: process-assessment
description: Map a client's or team's current process, find bottlenecks and repetitive work, before any automation or AI solution is proposed. Use during DISCOVER/ASSESS stages.
---

# Process Assessment

## Purpose
Understand and map the current process well enough to identify where the real bottleneck or repetitive work is, before proposing automation or AI (spec §11, §2).

## When to Use
- At the DISCOVER and ASSESS lifecycle stages (spec §12), before Solution Architecture.
- Whenever an automation/AI request arrives without an existing process map.

## Inputs
- Access to the people or documentation describing the current process (interviews, walkthroughs, existing SOPs, tickets, logs).
- The stated business problem (from Requirements Analysis or the commercial pipeline).

## Process
1. Map the current process step by step: who/what does what, in what order, with what inputs/outputs.
2. Identify bottlenecks: where time, effort or error concentrates.
3. Identify repetitive, rule-based, or high-volume work — candidates for automation.
4. Separate "process is broken" from "process is fine but manual" — these call for different solutions (fix the process vs. automate it).
5. Do not propose a technology solution yet — that's `../ai-opportunity-assessment/SKILL.md` and `../solution-architecture/SKILL.md`.
6. Record findings using `../../../templates/process-assessment/`.

## Outputs
- A process map (steps, roles, systems involved).
- A ranked list of bottlenecks/repetitive-work candidates.
- A clear statement of which parts of the problem are process issues vs. automation/tooling gaps.

## Quality Criteria
- The process map reflects the actual current process, not an idealized or assumed one.
- Bottlenecks are evidenced (observed, described by someone doing the work), not guessed.

## Failure Conditions
- A process is assumed rather than verified, and that assumption turns out wrong downstream.
- Automation is recommended for a process that's actually broken and needs redesign first (`../../../core/standards/governance/02-process-before-technology.md`).

## Related AfariLabs Standards
- `../../../core/standards/governance/02-process-before-technology.md`
- `../../../core/standards/governance/01-business-outcome-first.md`

## Related Templates
- `../../../templates/process-assessment/`
