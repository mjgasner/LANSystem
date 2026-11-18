# LAN System — Codex Task List

**Base:** Fork of LANCommander/LANCommander  
**Target:** Windows 10/11 x64, including older PCs (dual-core CPU, 4 GB RAM, HDD)  
**Updated:** 2026-11-18  
**Status:** Fork created; source-only preliminary audit completed; local builds/tests not yet run.

> This checklist is the project's durable source of truth. Mark a task complete only after verifying it. Update notes after each Codex work session. Work sequentially through M0 before starting features.

## M0 — Fork, baseline, Codex preparation

- [x] **M0.01 Fork LANCommander/LANCommander into mjgasner/LANSystem.** Verified this is a true GitHub fork with parent LANCommander/LANCommander; history retained.
- [ ] **M0.02 Clone the fork locally**, verify origin, and configure upstream to https://github.com/LANCommander/LANCommander.git. Continue work on a feature branch; do not push unreviewed work to main.
- [x] **M0.03 Record exact initial fork commit:** 8e76e0c452dcbb45107b9e8113e7f2e2983c17f8 (main, inspected 2026-11-18). Evaluate stable versus current 2.2 prerelease as future maintained baseline before changing dependencies.
- [x] **M0.04 Inspect upstream license and development prerequisites.** MIT LICENSE, .NET 10 SDK, Node.js.
- [x] **M0.05 Preliminary repository audit.** Read README, CONTRIBUTING, solution/project files and version props; see M0_PRELIM_AUDIT.md.
- [ ] **M0.06 Full architecture audit:** launcher entry and windows, Avalonia styles, services and bindings, SDK and plugin interfaces, server APIs, user data, saves, installation/redists, LCX packaging, version model and tests.
- [ ] **M0.07 Verify local prerequisites:** Windows SDK/toolchain needs, .NET 10, Node, restore packages. Record actual tool versions.
- [ ] **M0.08 Restore/build server and launcher** following CONTRIBUTING.md; record exact commands and failures.
- [ ] **M0.09 Run automated tests** and smoke-test server + Windows launcher where environment permits. Separate pre-existing failures from new issues.
- [x] **M0.10 Create initial AGENTS.md**, project specification, and first Codex work instructions on documentation branch. Revise them as actual architecture is learned.
- [ ] **M0.11 Create ARCHITECTURE.md** with verified source paths, component interaction, service contracts and reused capabilities.
- [ ] **M0.12 Create UPSTREAM_STRATEGY.md**, establishing merge/rebase policy, branching/version strategy, copyright and third-party license constraints.
- [ ] **M0.13 Create ROADMAP.md and BASELINE_TEST_RESULTS.md** using measured results, not assumptions.
- [ ] **M0.14 Design SKIN_ENGINE_DESIGN.md:** Avalonia window shape/transparency, click/drag masks, layered artwork, binding model, low-end graphics fallbacks, plugin versus shell approaches.
- [ ] **M0.15 Prototype one safe skin integration point** without replacing launcher, then test with live game data.
- [ ] **M0.16 Produce reviewable PR and report** changes, baseline tests, blockers, recommended M1 task. Preserve functioning upstream code.

## M1 — Mandatory extreme freeform Winamp/WMP XP skin engine
- [ ] Create versioned declarative skin schema and asset packaging.
- [ ] Support asymmetric/freeform windows, nonrectangular transparency, unusual geometry, custom dragging/hit areas.
- [ ] Support image-based interaction states, artworks, decorative zones, text regions, animation and scalability.
- [ ] Bind actions to upstream launcher services and preserve keyboard/controller accessibility.
- [ ] Implement reliable fallback/default skin on malformed packages.
- [ ] Produce an intentionally outrageous freeform test skin driven by real game data (not a color-swapped rectangle).
- [ ] Benchmark CPU/RAM/disk/render latency on older Windows 10/11 PCs.

## M2 — Player experience
- [ ] Integrate game browsing, search, details, installation queue/status, updates, launching and errors.
- [ ] Reuse LANCommander accounts, personal profile settings and per-user saves.
- [ ] Validate save backup/restore, same-user conflicts, offline behavior and server outage recovery.
- [ ] Ensure UI stays responsive on HDDs and 4 GB RAM.

## M3 — LAN features and voting
- [ ] Audit existing server discovery, networking, sessions and IP configuration.
- [ ] Add play-next voting, game ratings, group polls, game requests.
- [ ] Add game-specific multiplayer configuration adapters only where existing functions fall short.

## M4 — Revisions and storage
- [ ] Audit upstream 2.2 game version support and LCX format; preserve compatibility.
- [ ] Support current + five previous game revisions, configurable retention.
- [ ] Detect files changed, review stage changes, publish versions atomically.
- [ ] Explore deduplicated content chunks and incremental transfer based on benchmarks.
- [ ] Safely update and roll back installations independently of user saves.

## M5 — Installation Capture Workshop
- [ ] Audit existing packaging hooks, registry capture and shared redistributable handling.
- [ ] Support versioned dependency families (VC++, DirectX legacy, .NET, emulators) with x86/x64 and coexistence rules.
- [ ] Record Windows 10/11 clean VM baselines; monitor file/registry/system changes before and after installation.
- [ ] Generate declarative game recipes and reuse recognized dependencies.
- [ ] Independently reproduce/verify the result on fresh VMs; flag unsupported drivers, DRM and machine-bound state.
- [ ] Maintain installation receipts, repair procedures, diagnostics and rollback boundaries.

## M6 — Optional alternate execution environments
- [ ] Research Sandboxie/Turbo app isolation and limitations for games.
- [ ] Evaluate DOSBox Pure/legacy Windows OS per-game difference layers.
- [ ] Evaluate native VHDX boot and optional CCBoot without assuming compatibility.
- [ ] Add execution profiles only where reliably tested.

## Standing rules
- Preserve LANCommander functionality; implement extensions instead of rewrites.
- Keep upstream mergeability; do not bulk rename namespaces/projects.
- No arbitrary execution of untrusted installation scripts; no copying protected Windows components or DRM bypasses.
- Never remove or overwrite user saves during game updates.
- Keep MIT notices and relevant third-party obligations.
- Record actual test results; source inspection is not a successful build.
- One logical commit per cohesive change; create PRs for review.
