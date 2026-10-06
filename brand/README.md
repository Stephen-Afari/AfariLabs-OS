# AfariLabs Brand Kit

Brand consistency is a formal AfariLabs capability, not an ad-hoc design preference. All AfariLabs presentations, demos, proposals, case studies, YouTube assets, diagrams, training materials and reports should use this Brand Kit unless a client-specific brand system is explicitly required (spec Section 28).

**This is the reused AfariLabs Brand Kit**, copied as-is from `/Reference/AfariLabs_Brand_Kit` alongside this repository. It is itself the AfariLabs-rebranded version of a supplied ProjectIQ brand kit — see `colors/brandcolors.md` and the original kit's own `README.md` for that provenance. Nothing here has been invented; assets and values are reused exactly as supplied.

## Palette discrepancy — resolved

The OS specification document (Section 28) describes a brand palette inline (Deep Navy `#0B1F3A`, Cyan `#00C2D7`, Mint `#6FE7D4`, Coral `#FF6B5A`, Light Blue `#8ED8FF`, Off White `#F7FAFC`, White `#FFFFFF`, Charcoal `#1F2937`, Mid Gray `#64748B`), which differs from the **actual Brand Kit files**.

**Decision (human-confirmed):** the Brand Kit files are authoritative. All AfariLabs visual assets must use the palette defined in `colors/brand-colors.json` / `colors/brandcolors.md` / `colors/brandcolors.js`:

| Token | Hex |
|---|---|
| Deep Navy | `#0D1B3D` |
| Bright Cyan | `#00B6D1` |
| Soft Mint | `#C6F3E6` |
| Coral Accent | `#FF7A59` |
| Light Neutral | `#F2F4F7` |
| White | `#FFFFFF` |

The specification's inline §28 palette is superseded for all asset-generation purposes and must not be used.

## Structure

```text
brand/
├── colors/        Brand colors — JSON (machine-readable), JS export, Markdown reference
├── logos/          Primary icon, primary logo lockup, icon family
├── typography/      No font files supplied yet — see typography/README.md
├── presentation/    Brand identity guide/board, proposal cover
├── youtube/        YouTube banner
├── social/          Personal brand banner
└── templates/       Business card, letterhead, email signature mockups
```

## Rules

- Do not create a new AfariLabs color palette for an individual asset.
- If a client has its own visual identity, the client palette may be used for client-facing materials while AfariLabs branding remains appropriately visible.
- Asset-generation agents must check this Brand Kit before generating visual assets and must preserve the approved color values rather than approximating them.
