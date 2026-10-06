# Standard: Machine Independence

**Source:** OS spec §6 ("Your desktop is a development environment—not the permanent home of AfariLabs knowledge")

## Principle
AfariLabs-OS and its projects must be recoverable on a different machine. A local desktop is a working copy; the recovery path is Desktop → local Git → private GitHub → another machine can clone and continue.

## Rule
1. Nothing durable depends on machine-specific state: no absolute local paths in committed content, no configuration that only works on one computer.
2. Large assets (videos, large binaries) that don't belong well in Git are backed up separately, with that location documented — not left only on one desktop.
3. A recovery procedure (how to get back up and running on a replacement computer) exists conceptually: clone from GitHub, restore secrets from the secret manager/notes (never from Git), restore any separately-backed-up large assets.

## Claude Code must
- Avoid introducing absolute paths, machine-specific config, or local-only dependencies into anything committed to this repository.
- Flag it if a workflow being built would only function on the current machine (e.g. relies on a local file path outside the repo without documentation).
- Keep `.claude/` configuration free of machine-specific assumptions, consistent with this repository's existing portability stance (see root `README.md`).

## Claude Code must not
- Hardcode a Windows-specific (or any machine-specific) absolute path into a script or config file that's meant to be portable.
- Treat "it works on my machine" as sufficient validation for anything meant to be cloned and run elsewhere.

## Related
`README.md` (Portability), `core/standards/governance/19-git-version-control.md`
