# LAN System — Codex Agent Instructions

This is a fork of LANCommander. Follow docs/LAN_SYSTEM_SPEC.md and docs/TODO.md; the latter is the persistent milestone checklist. Consult docs/CODEX_START.md for the initial assignment.

## Priorities
1. Preserve the functioning upstream game-distribution, account, save, installer, redist and SDK subsystems.
2. Develop a **mandatory** freeform image-based launcher skin engine evoking extremely sculpted early-2000s Winamp/Windows Media Player interfaces—not rectangular color themes.
3. Keep Windows 10/11 x64 and older hardware (dual-core / 4 GB RAM / HDD) viable.
4. Implement voting, five previous game revisions, advanced packaging and alternate runtime environments only in their later milestones.

## Before any code modification
- Inspect the actual existing code and tests first, then choose the smallest reusable extension seam.
- Read upstream README.md, CONTRIBUTING.md, and this repo's relevant docs.
- Check current branch/status/remotes and do not overwrite unrelated user work.
- Document any uncertain third-party or version compatibility assumptions; do not invent APIs or architecture.
- Do not start M1 until M0 baseline builds and tests have been attempted and recorded.

## Build / verification (from upstream CONTRIBUTING.md)
- Requires .NET 10 SDK and Node.js.
- dotnet restore
- dotnet build LANCommander.Server
- dotnet build LANCommander.Launcher
- dotnet run --project LANCommander.Server
- Windows launcher: dotnet run --project LANCommander.Launcher -f net10.0-windows10.0.19041.0
- Identify actual test projects and run appropriate tests, recording exact commands, errors, environment and results.
- Different launcher framework targets may have separate local Data folders; development launcher/server versions must match.

## Engineering rules
- Prefer plugins, services and interfaces over rewriting core LANCommander code.
- Keep source code, persistence/storage, API, UI and skin definitions separate.
- Keep skins declarative and non-executable; provide crash-safe default/fallback.
- Preserve MIT and third-party license notices. Avoid committing game binaries, user saves, passwords, secrets or build outputs.
- Do not delete user saves, downgrade shared runtimes or run destructive migration/install operations without explicit approval.
- Never claim a tested result without actual execution.
- Commit cohesive changes and update docs/TODO.md as work is verifiably completed.
- Maintain compatibility with upstream contributions and future merges.

## Current assignment
M0 only: baseline audit, local build/test, architecture docs, upstream strategy and skin integration design, then one low-risk skin seam proof of concept. Stop and report if a decision materially changes architecture.
