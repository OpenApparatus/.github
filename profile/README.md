# OpenApparatus

**An open toolkit for reproducible behavioral-research environments.**

OpenApparatus generates multi-room floor plans, mazes, and other navigation apparatuses with deterministic output — same seed and parameters always produce the same environment, so methods sections only need to record those values for a result to be reconstructable.

## Built for

- Rodent navigation studies — Morris water maze, radial-arm and plus-maze analogues, custom apparatuses
- Spatial-cognition and wayfinding experiments in VR with human subjects
- Reinforcement-learning agent training with reproducible environment seeds
- Agent-based simulation in computational neuroscience

## The toolkit

| Component | Purpose | Status |
|---|---|---|
| **[core](https://github.com/OpenApparatus/core)** | Engine-agnostic .NET library — topology, geometry, mesh assembly. Pure C#, no engine assumptions. | Pre-release |
| **[studio](https://github.com/OpenApparatus/studio)** | Cross-platform desktop app (Avalonia) for authoring, previewing, and exporting plans to OBJ. | Pre-release |
| **[unity](https://github.com/OpenApparatus/unity)** | Unity Package Manager package that spawns OpenApparatus environments directly inside Unity scenes. | Pre-release |

`core` is the source of truth; `studio` and `unity` are thin adapters over it. Picking one does not lock you out of the others — the same `.floorplan.json` spec drives all three.

## Reproducibility, in a few lines

```csharp
using OpenApparatus.Core;

var gen = new GridDominoGenerator
{
    FloorWidthCells = 16,
    FloorLengthCells = 16,
    RectangleRoomCount = 8,
};
var plan = gen.Generate(new SeededRandom(seed: 42));
// any machine, any OS, any year — the same plan, byte-for-byte
```

That guarantee is the central design constraint. It's what lets a published seed substitute for a published asset.

## Why it exists

Behavioral experiments that depend on spatial environments — rodent navigation, VR wayfinding, agent-based simulations — are often reported in ways that make exact replication impractical. Hand-built scenes don't travel between studies; ad-hoc generators rarely publish their seeds. OpenApparatus treats the environment as a first-class, citable artifact:

- **Deterministic by construction.** Every generator takes a seeded RNG. Identical inputs, identical output, byte-for-byte.
- **Engine-agnostic core.** The same library underlies a desktop authoring tool and a Unity runtime — and is suitable for headless simulation pipelines.
- **Open source (MIT).** No license friction for reuse, derivative work, or institutional review.
- **Specs, not scenes.** A floor plan is described by a small JSON parameter spec; the geometry is regenerated on demand.

## Citing OpenApparatus

Each repository ships a `CITATION.cff` — GitHub renders a "Cite this repository" button on the right sidebar. For methods sections, once you've fixed a version, a sentence of the following form is sufficient:

> Environments were generated using OpenApparatus core v0.x.y (https://github.com/OpenApparatus/core) with `seed = N` and parameters `{ FloorWidthCells, FloorLengthCells, RectangleRoomCount, ... }`.

A formal Zenodo DOI will be minted on the v0.1 release.

## Getting started

- **Browsing?** Start with [core](https://github.com/OpenApparatus/core) for the data model and architecture.
- **Designing an apparatus?** Use [studio](https://github.com/OpenApparatus/studio) for live preview and OBJ export.
- **Running experiments in Unity?** Add [unity](https://github.com/OpenApparatus/unity) to your project.

Questions, feedback, or use-case stories are welcome in [Discussions](https://github.com/OpenApparatus/.github/discussions).

## Status

Active early development; APIs are unstable until v0.1. Roadmap and per-repo milestones are tracked in each repo's README.

## License

MIT across all repos.
