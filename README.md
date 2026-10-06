# AfariLabs-OS

AfariLabs-OS is the **control plane** of AfariLabs — an AI-native digital solutions agency and product studio. It holds reusable agency intelligence (standards, skills, agents, commands, patterns, templates, governance and tool/MCP policy) and is kept separate from execution-plane repositories where actual client and product applications are built.

This repository implements the **Foundation phase** of the `AfariLabs AI Engineering & Delivery OS v1.1` specification (see `/Reference` alongside this repository for the authoritative source document and the AfariLabs Brand Kit). It establishes the control plane directory structure, operating principles, and project registry only. Reusable capabilities (skills, commands, templates with content), controlled delivery (agent specs, approval gates), the pilot project, and automation are later phases — see `CLAUDE.md` for what is deliberately deferred.

## Status

**Foundation only.** No skills, agents, commands, orchestrator, Control Centre, MCP or the Desta Cold Store application have been built yet. This repository currently provides structure, operating principles and the reused Brand Kit.

## Directory Layout

```text
AfariLabs-OS/
├── CLAUDE.md                  AI operating instructions (read this first)
├── README.md                  This file
├── .gitignore                 Keeps secrets/env files/build output out of git
├── core/                      Constitution, standards, commercial standards and decision records
├── knowledge/                 Compounding agency knowledge (patterns, lessons, decisions...)
├── capabilities/              The four production studios + client success
├── templates/                 Reusable lifecycle artifacts (discovery through handover)
├── environments/              Development / staging / production conventions
├── projects/                  Project registry and lifecycle tracking
├── outputs/                   Generated, non-authoritative artifacts
├── brand/                     The reused AfariLabs Brand Kit
└── .claude/                   Claude Code configuration (skills, agents, commands, hooks, settings)
```

Each directory contains its own `README.md` explaining its purpose in more detail.

## Control Plane vs Execution Plane

The master repository is AfariLabs-OS. Individual applications and client solutions remain in separate repositories (e.g. `AfariLabs-PMRaid`, `AfariLabs-Desta-Cold-Store`). The OS provides reusable standards and capabilities; projects provide concrete implementations and feedback back into `knowledge/`.

## Portability

This repository is designed to be IDE-independent and portable:

- `.claude/` holds Claude Code configuration but introduces no dependency that prevents the repository from being read, cloned or used without Claude Code.
- No absolute paths, machine-specific configuration, or local secrets are stored here.
- GitHub is the source of truth for version-controlled content. Local machines are working copies. Production data, secrets, runtime state and large assets require separate systems and backups — never this repository.

## Where to Start

1. Read `CLAUDE.md` for the operating principles and execution rules.
2. Read `core/constitution/README.md` for the foundational principles this OS is built on.
3. Read `projects/registry/README.md` for how projects are tracked.
4. Read `brand/README.md` before producing any AfariLabs-facing visual asset.
