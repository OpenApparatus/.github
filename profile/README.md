<div align="center">

# OpenApparatus

### Reproducible environments for behavioral research

</div>

---

OpenApparatus is an open-source organization building tools to procedurally generate navigation environments — floor plans, mazes, and apparatuses — that can be reproduced exactly from a single seed.

The aim is simple: the environment should never be the unstated variable in a methods section.

## A shared problem

Spatial environments in behavioral experiments are rarely reusable across studies. Hand-built scenes don't travel between labs; ad-hoc generators rarely publish their seeds. The result is an unspoken gap in otherwise rigorous reporting — the geometry an animal navigated, or a participant walked through, or an agent trained in, is treated as incidental rather than as part of the experimental record.

OpenApparatus treats the environment as a first-class, citable artifact. A small parameter description, plus a seed, fully specifies it; the environment itself is regenerated on demand. Identical inputs always produce an identical environment, on any machine, in any year.

## Suited to

Rodent navigation paradigms · VR wayfinding studies with human subjects · reinforcement-learning agent training · computational-neuroscience simulations · anywhere a spatial environment needs to be specified once and reproduced exactly.

## The projects

<table>
<tr>
<td width="33%" valign="top">

### [core](https://github.com/OpenApparatus/core)

The foundation. The library every other project builds on — and the one you can use directly in your own analysis or simulation pipelines.

</td>
<td width="33%" valign="top">

### [studio](https://github.com/OpenApparatus/studio)

The desktop app. Design an apparatus visually, preview it live, and export it for use elsewhere — rendering, simulation, or publication figures.

</td>
<td width="33%" valign="top">

### [unity](https://github.com/OpenApparatus/unity)

The Unity integration. Drop it into a Unity project to bring OpenApparatus environments straight into your scenes.

</td>
</tr>
</table>

> One specification. Three surfaces. The same environment, every time.

## Citation

Every repository ships citation metadata, so GitHub renders a *Cite this repository* button directly on the project page. A formal DOI will accompany the v0.1 release.

## Conversations

Questions, feedback, and use-case stories are welcome in [Discussions](https://github.com/OpenApparatus/.github/discussions). Bug reports and feature requests belong on the relevant project repository.

<br>

<div align="center">
<sub>Open source under the MIT license.</sub>
</div>
