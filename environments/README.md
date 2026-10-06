# Environments

Conventions for keeping development, staging and production environments separate (spec Sections 10 and 14).

Rules:
- Keep credentials out of prompts, workflow definitions and this repository entirely.
- Classify tools by risk; every external action must have a defined permission boundary.
- GitHub is the source of truth for version-controlled assets — not production databases, secrets or runtime state.

No environment-specific configuration exists yet. These directories hold structure and convention documentation only; actual secrets and runtime configuration belong in appropriate secret-management systems, never in this repository.

## Secrets convention

No external secret manager is in use yet. Until one is adopted, the convention is:

- Real secrets live in a local `.env` file per environment, never committed. The root `.gitignore` already excludes `.env` and `.env.*` (with an explicit exception for `.env.example`).
- Each environment directory that ends up needing runtime configuration should ship an `.env.example` with variable *names* only — no real values — committed as documentation of what's required.
- This is a starting convention, not a final decision — revisit if/when AfariLabs adopts a dedicated secret manager (e.g. for production credentials shared across a team).
