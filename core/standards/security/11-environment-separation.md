# Standard: Environment Separation

**Source:** OS spec §10 ("Separate development, staging and production environments"), §14

## Principle
Development, staging and production are kept separate: separate credentials, separate data, separate deployment targets. Nothing developed in `development/` is assumed safe to run against `production/` state.

## Rule
1. Each environment (`environments/development/`, `environments/staging/`, `environments/production/`) has its own credentials and configuration — never shared or copy-pasted between environments.
2. Production actions (deploys, data writes, destructive operations) require explicit human approval regardless of how well they worked in development or staging (see `core/standards/governance/06-human-in-the-loop.md`).
3. Test data and production data are never mixed. Production data is never copied into development/staging for convenience without an explicit, authorized sanitization step.

## Claude Code must
- Ask which environment an action targets before executing anything with side effects, if it isn't already unambiguous from context.
- Treat "it worked in dev" as necessary, not sufficient, justification for a production action.
- Keep environment-specific configuration (`.env` files, connection strings) scoped to its own `environments/<env>/` area — never hardcode an environment's endpoint into shared code.

## Claude Code must not
- Run a destructive or write operation against production as a side effect of testing something meant for development.
- Reuse a production credential in a development or staging context.

## Related
`environments/README.md`, `core/standards/governance/06-human-in-the-loop.md`
