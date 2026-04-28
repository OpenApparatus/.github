# OpenApparatus

**An open toolkit for reproducible behavioral-research environments.**

OpenApparatus generates multi-room floor plans, mazes, and other navigation apparatuses with deterministic output — same seed and parameters always produce the same environment, so methods sections only need to record those values for a result to be reconstructable.

## The toolkit

| Component | Purpose | Status |
|---|---|---|
| **[core](https://github.com/OpenApparatus/core)** | Engine-agnostic .NET library — topology, geometry, mesh assembly. Pure C#, no engine assumptions. | Pre-release |
| **[studio](https://github.com/OpenApparatus/studio)** | Cross-platform desktop app (Avalonia) for authoring, previewing, and exporting plans to OBJ. | Pre-release |
| **[unity](https://github.com/OpenApparatus/unity)** | Unity Package Manager package that spawns OpenApparatus environments directly inside Unity scenes. | Pre-release |

`core` is the source of truth; `studio` and `unity` are thin adapters over it. Picking one does not lock you out of the others — the same `.floorplan.json` spec drives all three.

## Why it exists

Behavioral experiments that depend on spatial environments — rodent navigation, VR wayfinding, agent-based simulations — are often reported in ways that make exact replication impractical. Hand-built scenes don't travel between studies; ad-hoc generators rarely publish their seeds. OpenApparatus treats the environment as a first-class, citable artifact:

- **Deterministic by construction.** Every generator takes a seeded RNG. Identical inputs, identical output, byte-for-byte.
- **Engine-agnostic core.** The same library underlies a desktop authoring tool and a Unity runtime — and is suitable for headless simulation pipelines.
- **Open source (MIT).** No license friction for reuse, derivative work, or institutional review.
- **Specs, not scenes.** A floor plan is described by a small JSON parameter spec; the geometry is regenerated on demand.

## Getting started

- Browsing? Start with [core](https://github.com/OpenApparatus/core) for the data model and architecture.
- Designing an apparatus? Use [studio](https://github.com/OpenApparatus/studio) for live preview and OBJ export.
- Running experiments in Unity? Add [unity](https://github.com/OpenApparatus/unity) to your project.

## Status

Active early development; APIs are unstable until v0.1. Roadmap and per-repo milestones are tracked in each repo's README.

## License

MIT across all repos.
