# Reference Engineering — VFX

> Systematic pre-production reference methodology for VFX artists working in simulation, compositing, and real-time effects.

**Discipline:** Visual Effects (VFX)
**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Who This Is For

VFX artists working in simulation (Houdini, Niagara, EmberGen), compositing
(Nuke, After Effects), and real-time effects (Unreal Engine Niagara, Unity
VFX Graph). The methodology covers both offline VFX for film/TV and real-time
VFX for games and interactive. Production stage coverage: pre-sim brief
through final composite.

---

## What Reference Engineering Solves in VFX

VFX fails at reference in a way that is uniquely expensive: simulations
are slow to iterate. A fluid sim that runs for six hours and produces the
wrong result because the reference for the fluid behavior was absent
costs six hours before the error is even visible. Reference Engineering
in VFX front-loads the questions that would otherwise be discovered mid-sim:
what is the onset behavior? What is the peak density? What is the dissipation
rate? What color does this fluid actually turn at this temperature?

The second specific problem: VFX artists frequently use other VFX as reference.
Other VFX is Secondary or Tertiary tier. Real-world footage of the actual
phenomenon is Primary. Using CG fire as reference for CG fire produces
CG-looking fire. Using real fire footage as reference produces convincing fire.

---

## The Pre-Production Questions VFX Must Answer

- [ ] What is the real-world phenomenon being simulated? Have I watched real footage of it?
- [ ] What are the three phases? (onset / peak / dissipation — each has different visual parameters)
- [ ] What is the timing? (how many frames from onset to peak? from peak to dissipation?)
- [ ] What is the color at each phase? (real phenomena change color — fire goes from blue base to orange to yellow to white at peak)
- [ ] What is the density and opacity at each phase?
- [ ] What is the motion behavior? (turbulence scale, velocity range, direction bias)
- [ ] What is the context? (what is the VFX composited over, and how does it read in that context?)
- [ ] What are the pipeline constraints? (real-time budget? render time budget? resolution?)

---

## Pyramid Layer Map for VFX

| Pyramid Layer | What It Means in VFX |
|---|---|
| Layer 1 — Function & Context | What phenomenon is being simulated, narrative function (hero effect vs background), compositional context |
| Layer 2 — Scale & Proportion | Physical scale of the effect, timing (frame counts per phase), density range |
| Layer 3 — Stage Reference | Reference per phase: onset reference, peak reference, dissipation reference |
| Layer 4 — Governing Rules | Extracted timing parameters, color gradient, density curve, turbulence behavior — written numbers |
| Layer 5 — Contextual Conditions | Final composite lighting conditions, background plate, camera conditions (lens, exposure) |
| Layer 6 — Behavior & Construction | Real-world physical behavior: combustion chemistry, fluid dynamics, particulate behavior |
| Layer 7 — Precision Detail | Micro-detail within the effect: ember behavior, secondary smoke wisps, edge breakup |

---

## Contents

| File | What's in it |
|---|---|
| [`REFERENCE_GUIDE.md`](./REFERENCE_GUIDE.md) | Full methodology — all seven layers, phase breakdown, pipeline-specific sections |
| [`mistakes.md`](./mistakes.md) | 7 VFX-specific failure modes |
| [`checklist.md`](./checklist.md) | Pre-sim checklist, phase-organized |
| [`sources.md`](./sources.md) | Best VFX reference sources by layer |

---

## Related

- **Example:** [`examples/game-environment/`](../../examples/game-environment/) — includes VFX context reference (explosion timing, environmental conditions)
- **AI skill pack:** [github.com/p4inz-code/3d-ref-skills](https://github.com/p4inz-code/3d-ref-skills) — includes `ref-vfx` skill for VFX pre-production

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
