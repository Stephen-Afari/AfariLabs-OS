---
name: demonstration
description: Produce a verified, brand-consistent client demo or internal demonstration from actual working project artifacts. Use at the DEMONSTRATE lifecycle stage.
---

# Demonstration

## Purpose
Produce a client demo or internal demonstration that accurately shows what was built, using verified artifacts and consistent AfariLabs branding (spec §12 DEMONSTRATE stage, §18, §28).

## When to Use
- At the DEMONSTRATE lifecycle stage, after VALIDATE/TEST and (where applicable) SECURITY REVIEW.
- Whenever a working capability needs to be shown to a client or stakeholder.

## Inputs
- The validated, working solution.
- Test/evaluation results to cite, if claims about performance or accuracy will be made.
- The AfariLabs Brand Kit (`../../../brand/`).

## Process
1. Confirm what will be demonstrated is actually working, not a mockup presented as working — if it's a mockup, say so explicitly.
2. Any claim made during the demo (accuracy, speed, capability) traces to a verified test or evaluation result (`../../../core/standards/governance/18-documentation.md`).
3. Use the AfariLabs Brand Kit exactly — check `../../../brand/` before producing any visual asset (`../../../core/standards/governance/17-brand-consistency.md`).
4. Prepare for realistic failure during a live demo — know the solution's actual limitations, don't oversell.
5. Record using `../../../templates/demonstration/`.

## Outputs
- A demo (live walkthrough, recorded video, or demo brief) accurately representing the working solution.
- Supporting materials using the AfariLabs Brand Kit.

## Quality Criteria
- Everything shown as working actually works at demo time.
- Every performance/capability claim is traceable to a verified result.
- Brand values (colors, typography, logo usage) match `../../../brand/` exactly.

## Failure Conditions
- A capability is demoed as working when it's actually a mockup or partial implementation, without disclosure.
- A claim is made that isn't backed by a test or evaluation result.
- Brand colors or assets are approximated instead of using the exact Brand Kit values.

## Related AfariLabs Standards
- `../../../core/standards/governance/17-brand-consistency.md`
- `../../../core/standards/governance/18-documentation.md`

## Related Templates
- `../../../templates/demonstration/`
