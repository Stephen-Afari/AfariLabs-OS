# Project Registry (Human-Readable)

Source of truth for machine consumption: `registry.json`. This file mirrors it for readability. To register a new project, copy `TEMPLATE.json`, fill it in, and add the entry to `registry.json`'s `projects` array — see `README.md` for field definitions.

| project_id | name | status | classification | repository | lifecycle_stage |
|---|---|---|---|---|---|
| `pmraid` | PMRaid | COMPLETED | Reference Project | `AfariLabs-PMRaid` | N/A — predates AfariLabs-OS |
| `desta-cold-store` | Desta Cold Store Project | PILOT | Internal AfariLabs Product | `AfariLabs-Desta-Cold-Store` | not started |

## Notes

- **PMRaid** is a completed AfariLabs project retained in the portfolio as evidence of existing capability — used as a reference architecture, product demonstration, case study and portfolio asset. AfariLabs-OS was **not** used to build it, and its lifecycle is not tracked retroactively through the OS. (Spec Section 20)
- **Desta Cold Store Project** is the first internal AfariLabs product to be run through the complete AfariLabs-OS lifecycle (DISCOVER → DEFINE → ASSESS → ARCHITECT → SPECIFY → BUILD → VALIDATE → TEST → SECURITY REVIEW → HUMAN ACCEPTANCE → DEMONSTRATE → DEPLOY → MONITOR → HANDOVER → LEARN) — the proving ground for the operating system. It is an internal AfariLabs product, not a client engagement. **It has not been started.** No technical details (technology, architecture, capabilities used) are recorded because none have been decided yet — this registry does not invent them.

No `owner`, `created_date`, `technology`, `capabilities_used`, `security_status`, or `evaluation_status` are recorded for either project: none of this is stated in the OS specification, and this registry does not infer or invent project detail. See `registry.json` for the full field set, including which are `null` and why.
