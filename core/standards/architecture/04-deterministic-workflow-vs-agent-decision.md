# Standard: Deterministic Workflow vs. Agent Decision

**Source:** OS spec §24 ("Do not add agents where deterministic workflows are sufficient"), §26 ("Prefer deterministic workflows over agents when the process is predictable. Use agents when dynamic reasoning, tool selection or context-dependent decisions provide clear value.")

## Principle
An agent (an LLM making runtime decisions about what to do next) is only justified when the task genuinely requires dynamic reasoning, tool selection, or context-dependent judgment. A predictable sequence of steps is a deterministic workflow, not an agent.

## Rule
Before building an agent, answer: does this task require a decision that cannot be predetermined (branching on content, selecting from multiple tools based on context, reasoning over ambiguous input)? If the steps and their order are knowable in advance, it's a deterministic workflow.

| Use a deterministic workflow when... | Use an agent when... |
|---|---|
| Steps and their order are known in advance | The next action depends on reasoning about content |
| Inputs map predictably to outputs | Tool selection depends on context, not a fixed rule |
| A `if/else` or fixed pipeline fully describes the logic | Ambiguous or free-form input needs interpretation |

## Claude Code must
- Default to a deterministic workflow (a function, a script, a fixed pipeline, an n8n workflow) for any task whose steps can be fully specified in advance.
- Justify, explicitly, the choice to use an agent instead of a workflow when proposing one — naming the specific dynamic-reasoning or tool-selection requirement.

## Claude Code must not
- Build a multi-agent system or orchestrator for a task a single deterministic script would solve (spec §24, §9: "Do not build the full orchestrator before the pilot demonstrates which orchestration is genuinely useful").
- Treat "it's an AI project" as sufficient justification for an agent architecture by itself.

## Related
`core/standards/architecture/03-simplest-viable-architecture.md`, `CLAUDE.md` (Controlled Agent Architecture)
