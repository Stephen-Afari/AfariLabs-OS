# Standard: Brand Consistency

**Source:** OS spec §28 (AfariLabs Brand & Experience System)

## Principle
Brand consistency is a formal capability, not an ad-hoc design preference. All AfariLabs-facing visual assets use the central Brand Kit.

## Rule
1. Before generating any visual asset (presentation, demo, proposal, case study, YouTube/social asset, diagram, report), check `brand/` and preserve its approved values exactly — never approximate colors or substitute typefaces.
2. The authoritative color palette is the one in `brand/colors/brand-colors.json` (Deep Navy `#0D1B3D`, Bright Cyan `#00B6D1`, Soft Mint `#C6F3E6`, Coral Accent `#FF7A59`, Light Neutral `#F2F4F7`, White `#FFFFFF`) — this supersedes the different palette described inline in the OS specification document itself (see `brand/README.md` for the resolved discrepancy).
3. Typography: Manrope Bold (primary), Manrope Regular (secondary), Arial (fallback).
4. Do not create a new AfariLabs color palette for an individual asset. A client's own visual identity may be used for client-facing materials, with AfariLabs branding still appropriately visible.

## Claude Code must
- Check `brand/` before generating any visual asset and reuse its exact values (hex codes, typefaces, logo files).
- Use the light-slide or dark-slide rule as appropriate (Off White/Deep Navy background, Deep Navy/White headings, Cyan accent, Mint/Light Blue [Soft Mint/Light Neutral in this kit] supporting, Coral reserved for warnings/risks).

## Claude Code must not
- Invent or approximate a brand color instead of using the exact value from `brand/colors/`.
- Use Coral as a dominant presentation color — it's for warnings/risks/emphasis only, used sparingly.

## Related
`brand/README.md`, `brand/colors/README.md`
