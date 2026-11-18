# LAN System — Preliminary M0 Audit

**Date:** 2026-11-18  
**Upstream:** https://github.com/LANCommander/LANCommander  
**Fork:** https://github.com/mjgasner/LANSystem  
**Fork state:** GitHub API confirms fork=true and parent/source LANCommander/LANCommander.  
**Base commit at verification:** 8e76e0c452dcbb45107b9e8113e7f2e2983c17f8

## Verified by reading actual repository files

- LICENSE: MIT License, copyright LANCommander.
- Directory.Build.props: current source identifies Version 2.2.0-rc.2 and most projects target .NET 10.
- CONTRIBUTING.md: requires .NET 10 SDK and Node.js; provides commands:
  - dotnet restore
  - dotnet build LANCommander.Server
  - dotnet build LANCommander.Launcher
  - dotnet run --project LANCommander.Server
  - dotnet run --project LANCommander.Launcher -f net10.0-windows10.0.19041.0
- Launcher uses Avalonia, ReactiveUI/MVVM and SVG/Skia components. Do not assume WinForms.
- Server is an ASP.NET Blazor project.
- LANCommander.slnx includes launcher service/model/plugin projects; server services, UI and database adapters; packaging/monitor workers; SDK and extensive test projects.
- README documents local game distribution, user management, saves, redistributables, packaging/registry capture, auto-discovery and SDK. These are claims of existing features, not yet experimentally tested.
- Windows launcher has multiple target frameworks with distinct local development data locations; client/server major version mismatch can prevent communication.
- AGENTS.md did not exist at the upstream repository root when checked; still inspect nested or newly added instructions.

## Remaining verification

1. Clone and configure local remotes; select baseline after release/stability evaluation.
2. Run restore, server build, Windows launcher build, relevant tests and launch smoke tests in an environment with .NET 10 and Node.
3. Map real code seams for renderer/window management, launcher services, plugins and game data bindings.
4. Document performance considerations on low-spec Windows 10/11 hardware.

## Important limitations

This audit is source inspection only. No Windows execution, integration test, runtime memory benchmarking, package capture test or server deployment has been performed. Do not mark such steps completed before running them.
