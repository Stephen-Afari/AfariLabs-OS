# Standard: Git / Version Control

**Source:** OS spec §6 (GitHub, Backup and Machine Independence)

## Principle
GitHub is the source of truth for version-controlled code, standards and documentation. Local machines are working copies, not the permanent home of AfariLabs knowledge.

## Rule
1. Commit and push frequently — work that exists only locally and uncommitted is at risk.
2. Never commit API keys, passwords, tokens, or `.env` files (see `core/standards/security/10-secrets-management.md`); the root `.gitignore` enforces this mechanically, but review before staging regardless.
3. GitHub holds version-controlled assets — not production databases, secrets, or runtime state. Those require separate systems and backups.
4. Before any destructive git operation (`reset --hard`, `checkout --`, force-push), check `git status` first and stash or commit anything uncommitted.

## Claude Code must
- Review staged changes before committing, watching for anything that looks like a secret even in an innocuously-named file.
- Only create a new commit (not amend/force-push) unless explicitly instructed otherwise — matches this session's broader git safety rules.
- Confirm with the user before any destructive or shared-state git action (force-push, history rewrite, branch deletion).

## Claude Code must not
- Commit `.env`, credentials, or other secret material, even temporarily "to test something."
- Treat a local, uncommitted change as safe to discard without checking `git status` first.

## Related
`.gitignore`, `core/standards/security/10-secrets-management.md`, `core/standards/governance/20-machine-independence.md`
