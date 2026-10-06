---
description: Run AfariLabs Testing — execute tests covering core behavior and realistic failure scenarios.
argument-hint: <project-id-or-name>
---

# /test

Runs the **testing-qa** skill's Test step for the **TEST** lifecycle stage: execute tests and record results. Human-supervised: runs and reports tests. Does not deploy or touch staging/production.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Locate the `/validate` output and the implementation's existing test setup, if any.
2. **Load the skill.** Invoke the Skill tool with `testing-qa` and follow the Test portion of its Process.
3. **Check standards.** Read `../../core/standards/quality/12-testing.md`.
4. **Inspect existing context.** Check for an existing test suite before writing a new one from scratch; extend rather than duplicate.
5. **Produce structured output.** Execute tests (in a development/test environment only — see Permission boundary) and record results using `../../templates/testing/`. Write to `../../outputs/<project-id>/test/` (or the project's own repo).
6. **Record decisions.** If tests reveal a gap requiring a design or requirements change, record it and flag it rather than quietly patching around it.
7. **Report back.** Summarize what was tested, pass/fail results, and whether this clears the TEST quality gate. For AI-involving solutions, note explicitly that `/evaluate` is still required separately.

## Permission boundary
- READ (implementation, existing tests): automatic.
- WRITE (new/updated tests, test results): proceed, but show the user what was written.
- EXECUTE: running the test suite itself is permitted only against development/test environments (`../../environments/development/`), never staging or production.
- DESTRUCTIVE: out of scope entirely.

## Human approval
Test results are reported for human review before `/security-review` or `/evaluate` proceed — a passing local run is not itself the lifecycle gate sign-off.

## Stops and asks when
- No validated implementation exists yet (run `/validate` first).
- A test would need to run against staging or production data to be meaningful — stop and ask rather than doing so automatically.

## Related
- Skill: `../skills/testing-qa/SKILL.md`
- Standards: `../../core/standards/quality/12-testing.md`
- Template: `../../templates/testing/`
- Previous: `/validate` · Next: `/evaluate` (if AI involved) or `/security-review`
