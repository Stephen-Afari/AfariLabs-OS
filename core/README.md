# Core

The foundational control-plane content: the constitution, AfariLabs' agreed standards, and decision records about the control plane itself.

- `constitution/` — foundational, rarely-changing principles (see `constitution/CONSTITUTION.md`)
- `standards/` — agreed standards by area: architecture, security, quality, delivery, governance
- `commercial/` — agreed standards for the lead-to-expansion commercial pipeline (spec Section 11)
- `decision-records/` — decisions about AfariLabs-OS itself

## `core/` vs `capabilities/`

`core/standards/{delivery,security}` and `capabilities/{delivery,security}` are not duplicates:

- `core/standards/` holds the **agreed standard** — the rule AfariLabs has decided to follow in a given area.
- `capabilities/` holds the **applied capability** — skills, checklists and reusable assets for actually doing the work, once proven through delivery.

A standard can exist in `core/standards/` before any capability content exists in `capabilities/`, and vice versa. Both are currently empty; this note exists so a future contributor doesn't merge or duplicate them by mistake.
