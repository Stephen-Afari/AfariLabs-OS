---
description: Run AfariLabs Learning Capture — record project lessons, and flag (not auto-promote) any candidate pattern.
argument-hint: <project-id-or-name>
---

# /learn

Runs the **knowledge-capture** skill for the **LEARN** lifecycle stage. Human-supervised: drafts lesson entries for review. Does not promote anything into `knowledge/patterns/` or `knowledge/standards/` on its own.

## Steps

1. **Resolve project context.** Look up `$ARGUMENTS` against `../../projects/registry/registry.json`. Gather the full project history (all prior-stage artifacts) as source material.
2. **Load the skill.** Invoke the Skill tool with `knowledge-capture` and follow its Process.
3. **Check standards.** Read `../../core/standards/governance/15-knowledge-capture.md` and `../../core/standards/security/16-client-data-protection.md`.
4. **Inspect existing context.** Check `../../knowledge/lessons/` and `../../knowledge/patterns/` for anything this project confirms, contradicts, or extends — connect new lessons to existing knowledge rather than capturing in isolation.
5. **Produce structured output.** Write lesson entries into `../../knowledge/lessons/`, generalized and stripped of client-identifying detail per `../../core/standards/security/16-client-data-protection.md`. Draft (but do not finalize) any candidate pattern — promotion into `../../knowledge/patterns/` is a separate, explicitly human-reviewed step, never automatic.
6. **Record decisions.** If a lesson suggests a standard or skill should change, propose the change explicitly rather than silently editing `core/standards/` or `.claude/skills/` as a side effect of this command.
7. **Report back.** Summarize what was captured, which items are candidate patterns awaiting review, and any proposed standard/skill update for the human to consider separately.

## Permission boundary
- READ (full project history, existing knowledge base): automatic.
- WRITE (lesson entries in `knowledge/lessons/`): proceed, but show the user what was written.
- EXECUTE / DESTRUCTIVE: out of scope. Promotion into `knowledge/patterns/`, `knowledge/standards/`, or edits to `core/standards/`/`.claude/skills/` are never performed automatically by this command.

## Human approval
Capturing a lesson doesn't require pre-approval (it's a WRITE to a non-authoritative lessons log), but promoting it into a validated pattern or standard does — per `../../core/standards/governance/15-knowledge-capture.md`, promotion requires review.

## Stops and asks when
- A lesson would require including client-identifying detail to make sense, and authorization to do so hasn't been confirmed.
- The project history is incomplete (missing prior-stage artifacts) such that a lesson can't be grounded in what actually happened.

## Related
- Skill: `../skills/knowledge-capture/SKILL.md`
- Standards: `../../core/standards/governance/15-knowledge-capture.md`, `../../core/standards/security/16-client-data-protection.md`, `../../core/standards/governance/09-auditability.md`
- Related directories: `../../knowledge/lessons/`, `../../knowledge/patterns/`
- Previous: `/handover` · Next: (end of lifecycle)
