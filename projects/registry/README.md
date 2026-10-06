# Project Registry

The authoritative list of AfariLabs projects, their status, classification and lifecycle state. See `registry.json` for the machine-readable list (which embeds its own field schema), `REGISTRY.md` for the human-readable view, and `TEMPLATE.json` to register a new project.

This registry **tracks** projects — it does not contain their implementation, which lives in each project's own execution-plane repository (see `CLAUDE.md`, Control Plane vs Execution Plane).

## Status values

- **ACTIVE** — currently in delivery under AfariLabs-OS governance, lifecycle in progress.
- **COMPLETED** — delivered through its full lifecycle (or, for a project predating AfariLabs-OS, delivered and closed) and retained in the portfolio.
- **PILOT** — the project currently validating AfariLabs-OS itself by being run through the complete lifecycle for the first time. Only one project should normally hold this status at a time.
- **ARCHIVED** — no longer active or maintained; retained for historical/reference purposes only.

## Classification

Free-text, not a closed enum (the specification doesn't define a fixed list) — e.g. `Reference Project`, `Internal AfariLabs Product`, `Client Engagement`. Use whatever accurately describes the project's relationship to AfariLabs; don't force-fit a project into an existing classification if it doesn't apply.

## Fields

Every entry in `registry.json` carries:

| Field | Meaning |
|---|---|
| `project_id` | Unique, kebab-case identifier (primary key) |
| `name` | Display name |
| `status` | One of the four status values above |
| `classification` | Free-text project category |
| `description` | Short, factual description — must be verifiable, not invented |
| `owner` | Person/role accountable; `null` if not assigned |
| `repository` | Execution-plane repository name; `null` if none exists yet |
| `created_date` | ISO 8601 date registered/started; `null` if not recorded |
| `technology` | Array of confirmed technologies; `null` if not yet known |
| `capabilities_used` | Array of `capabilities/` areas engaged; `null` if none yet |
| `lifecycle_stage` | Current stage of the 15-stage lifecycle, or `null` if not started |
| `security_status` | Security Review gate status; `null`/`"Not reviewed"` if not reached |
| `evaluation_status` | AI Evaluation gate status, if applicable; `null` otherwise |
| `deployment_status` | Current deployment state; `null` if not documented |
| `lessons` | Array of references into `knowledge/lessons/` |
| `patterns` | Array of references into `knowledge/patterns/`, once validated |
| `related_projects` | Array of other `project_id` values this project relates to |

The full definition of each field (including allowed values and null-handling rules) is embedded in `registry.json` under its `schema` key, so the schema travels with the data rather than living only in this prose.

## Registering a new project

1. Copy `TEMPLATE.json`.
2. Fill in every field — use `null` or `[]` rather than inventing a value you don't actually know.
3. Add the entry to the `projects` array in `registry.json`.
4. Add a row to the table in `REGISTRY.md`.
5. Do not mark a project `ACTIVE` until delivery work has actually begun, and do not record `technology`, `capabilities_used`, `lifecycle_stage`, `security_status`, `evaluation_status` or `deployment_status` beyond what is actually true yet — leave them `null` until real.

## Currently registered

- `pmraid` — COMPLETED, Reference Project.
- `desta-cold-store` — PILOT, Internal AfariLabs Product. Not yet started; do not build its application or repository ahead of actual lifecycle work (see `CLAUDE.md`, "Deliberately Deferred").
