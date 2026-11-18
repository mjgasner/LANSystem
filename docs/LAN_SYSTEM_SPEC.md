# LAN System — Product and Engineering Specification

Base: MIT-licensed fork of LANCommander. Target Windows 10/11 x64 and older hardware (dual-core CPUs, 4 GB RAM, HDDs).

## Mission
A locally hosted game library that distributes, installs and runs games across a LAN with simple accounts, individual saves/settings, voting, version history, and extremely expressive XP-era Winamp/WMP skins. Users log in, select a game, and play. Preserve existing LANCommander server, SDK, save, redist and distribution capabilities instead of duplicating them.

## Architectural priorities
- Keep current .NET 10/Avalonia launcher and LANCommander server/API as the baseline until their extension points are assessed.
- Keep existing LCX game package support, install scripts, user account and cloud save behavior.
- Prefer normal Windows folders for current game installations and per-user saves; use explicit staging areas for admin changes.
- Keep server-authoritative files, local client working copies and each user's saves separate.
- Support current game version plus five previous versions, approved change detection, atomic updates, rollback and deduplication where practical.
- Manage ISO media, emulators, VC++ generations (x86/x64), legacy DirectX and .NET with dependency detection, coexistence/version constraints and install receipts.
- Auto-discover LAN services and configure game networking with safe per-game adapters. Include voting, ratings, polls, game requests.

## Mandatory launcher skins
Freeform, sculpted, organic, metallic and glossy early-2000s skins with unusual angles, nonrectangular chrome, transparent cutouts, click/drag masks, detached panels, arbitrary controls and large decorative art regions. Not simply palettes or conventional rectangular themes. Use versioned declarative skin metadata and bind controls to existing launcher services. A broken skin must safely fall back to the default. Preserve usability, keyboard inputs and responsiveness on older hardware.

## Installation Capture Workshop — later milestone
Start disposable clean Windows 10/11 VM; inventory files, registry, services, dependencies and configuration; install game, patches and perform reboots; capture persistent changes and process operations; classify reusable dependencies; generate payload + declarative installation actions; reproduce independently in another clean VM; verify launch and record failures. Retain evidence and original installers. No false claims of arbitrary Windows portability, DRM bypass or unsafe replacement of system components.

## Alternative execution
Possible profiles: native portable, reconstructed installation, emulator, sandbox/isolation and optionally a game-specific OS image/CCBoot. Do not implement optional environments before validation.

## Milestones
M0 repository fork, build/test baseline, architecture and Codex instructions. M1 extreme freeform skin proof. M2 player workflow/saves. M3 voting and networking. M4 five-revision management. M5 VM installation capture. M6 alternative execution experiments.

Keep upstream compatibility and MIT attribution. Never overwrite user saves or auto-uninstall shared system dependencies. See docs/TODO.md for durable task tracking and AGENTS.md for agent instructions.
