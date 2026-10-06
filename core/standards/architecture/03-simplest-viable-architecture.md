# Standard: Simplest Viable Architecture

**Source:** OS spec §2 ("Build the smallest useful capability first"), §24 ("Do not introduce architectural complexity before scale or reliability requires it"), §26 ("Use the simplest architecture that satisfies the requirements")

## Principle
Use the simplest architecture that satisfies the stated requirements. Complexity is added only when real work exposes a need for it — not speculatively.

## Rule
1. Before adding a new architectural layer (a queue, a cache, a new service, a multi-agent system, an orchestration framework), name the concrete requirement it satisfies that the simpler alternative cannot.
2. If "we might need this later" is the only justification, don't build it now.
3. Prefer extending an existing pattern (see `knowledge/patterns/`) over inventing a new one, when one already fits.

## Claude Code must
- Default to the smallest architecture that meets the stated requirement (a single script over a workflow engine, a workflow over an agent, one service over a microservice split) unless a specific, named requirement rules it out.
- Check `knowledge/patterns/` and `core/standards/architecture/` for an existing validated approach before designing a new one.
- State explicitly, in the design, why a simpler alternative was rejected when choosing a more complex one.

## Claude Code must not
- Add architectural complexity (new services, orchestration layers, agent frameworks) to a design "for future flexibility" without a current, named requirement driving it.
- Reach for the most capable/interesting technology when a plainer one satisfies the requirement (spec §24: "do not build technology merely because it is interesting").

## Related
`core/standards/architecture/04-deterministic-workflow-vs-agent-decision.md`, `knowledge/patterns/`, `CLAUDE.md` (Strategic Guardrails)
