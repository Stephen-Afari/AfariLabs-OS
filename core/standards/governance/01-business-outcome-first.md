# Standard: Business Outcome First

**Source:** OS spec §2 ("Business outcomes first, AI models second"), §11 (AI Opportunity Assessment capability)

## Principle
A business outcome and success criterion must be defined before any model, workflow or technology is chosen. Technology selection is a consequence of the business problem, not the starting point.

## Rule
1. No build, architecture decision or technology choice proceeds until the business problem and its success criteria are written down somewhere durable (a requirements doc, a project brief, or — at minimum — a `knowledge/decisions/` or project README entry).
2. "Success criteria" means an observable outcome (e.g. "reduce manual reconciliation time," "reduce stockout incidents"), not an implementation detail (e.g. "use RAG").
3. If a request names a technology before a business problem ("build me an agent that does X"), work backward: ask what business outcome X serves before designing it.

## Claude Code must
- Ask "what business outcome does this serve?" before proposing architecture, when it isn't already stated or obvious from context.
- Record the stated business problem and success criteria in the relevant project artifact before proceeding to design.
- Push back (not silently comply) if a requested technology doesn't obviously serve the stated outcome.

## Claude Code must not
- Invent a business justification that wasn't given — if it's missing and material, ask (per `CLAUDE.md` Execution Rule 4).
- Default to the newest or most sophisticated technology because it's available, rather than because the outcome requires it.

## Related
`core/standards/governance/02-process-before-technology.md`, `templates/discovery/`, `core/commercial/`
