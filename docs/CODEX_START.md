# Initial Codex Task — LAN System M0

Repository: mjgasner/LANSystem
Parent: LANCommander/LANCommander
Documentation branch: lan-system/m0-foundation
Original upstream fork commit: 8e76e0c452dcbb45107b9e8113e7f2e2983c17f8

Read AGENTS.md, docs/TODO.md, docs/LAN_SYSTEM_SPEC.md, docs/M0_PRELIM_AUDIT.md, README.md and CONTRIBUTING.md first. Execute M0; do not stop after drafting a plan.

1. Verify Git status, fork history and remotes. Configure upstream https://github.com/LANCommander/LANCommander.git if missing. Work on a feature branch; preserve unrelated work.
2. Inspect real launcher Avalonia window, styles, ViewModels and service architecture; plugins and SDK; server APIs; saves, LCX distribution, packaging monitor, game versions, redistributables and test suites.
3. Compare current 2.2 prerelease baseline with stable, record exact commits and pros/cons. Do not force rebase or rewrite history.
4. Verify .NET 10, Node.js and other prerequisites. Run restore, server and launcher builds and appropriate tests. Smoke-test launcher/server where execution environment permits. Record exact commands and outcomes; do not claim tests succeeded without running them.
5. Create docs/ARCHITECTURE.md, docs/ROADMAP.md, docs/UPSTREAM_STRATEGY.md, docs/BASELINE_TEST_RESULTS.md, and docs/SKIN_ENGINE_DESIGN.md. Update docs/TODO.md based on verification.
6. Design the least invasive freeform XP-era Winamp/WMP skin seam with nonrectangular windows, transparent regions, decorative imagery, arbitrary buttons/hit zones, binding to real game data, fallback skin, and performance on HDD/4GB machines. Consider extension/plugin vs separate shell.
7. After baseline build, implement at most one minimal non-destructive skin integration prototype if feasible. Do not begin later milestones or rewrite launcher.
8. Commit logical changes, prepare reviewable PR, report blockers and specific next task for M1.

Preserve original MIT and third-party licenses. Never delete saves, install untrusted components or perform destructive Git operations without approval.
