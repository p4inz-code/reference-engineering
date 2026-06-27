# Reference Engineering — 3D Art

> Systematic pre-production reference methodology for 3D artists working in games, VFX, film, and marketplace production.

**Discipline:** 3D Art
**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Who This Is For

3D artists working on props, environments, characters, and VFX assets across
real-time (game engine) and offline (VFX/film) pipelines. The methodology
is production-stage aware — it tells you what reference to gather at blockout,
what to gather at UV stage, and what to gather at hero detail. Not all at once.

This section covers the full 3D production arc: concept through delivery.
It is calibrated for artists working alone or in small teams where pre-production
reference work is often informal or absent.

---

## What Reference Engineering Solves in 3D Art

The most expensive problems in 3D production — proportion errors discovered
at integration, style drift across a production, material values calibrated
to the wrong renderer, topology that fails at deformation — are almost always
reference failures. The geometry was built correctly. The specification
it was built from was wrong because the reference that would have defined
the correct specification was never gathered.

Reference Engineering in 3D art is the discipline of knowing what reference
to gather before you open your DCC, what it should answer, and when to
gather it.

---

## The Pre-Production Questions 3D Art Must Answer

Before the first polygon is placed, reference must answer these questions.
If any are unanswered, production will be stopped by them later.

- [ ] What is the real-world function of this asset? What does it do, and does it need to appear to do it correctly?
- [ ] What are the real-world dimensions? What is the scale anchor (the one thing whose size is unambiguous)?
- [ ] What is the target camera distance and angle? (FPS: 70–100 images. TPS hero: 50–70. Isometric: 15–25. Environment background: fewer.)
- [ ] What production style am I working in, and what are its written rules — not its feel?
- [ ] What lighting and rendering conditions will this asset live in? (renderer, HDRI conditions, time of day range)
- [ ] What are the PBR channel target ranges for each material zone on this asset?
- [ ] What deformation zones exist if this asset is rigged, and what does the deformation reference say about topology?
- [ ] What are the platform/polygon/texel constraints?
- [ ] What does the asset's silhouette look like from the primary camera angle in the primary gameplay or scene pose?

---

## Pyramid Layer Map for 3D Art

| Pyramid Layer | What It Means in 3D Art |
|---|---|
| Layer 1 — Function & Context | What the prop/character/environment does, where it lives, who uses it, how it is used in motion not just at rest |
| Layer 2 — Scale & Proportion | Real-world dimensions, scale anchor, head count for characters, modular grid for environments |
| Layer 3 — Stage Reference | Silhouette/orthographic for blockout stage; material and surface for UV stage; close-up texture for hero stage |
| Layer 4 — Governing Rules | Shape language, detail density map, surface quality, edge treatment, what the style never does — all written |
| Layer 5 — Lighting Context | Target renderer conditions, HDRI / scene light type, time of day, platform rendering pipeline (real-time vs offline) |
| Layer 6 — Material & Surface | PBR channel values per material zone, physical material behavior, construction and assembly logic, wear and aging patterns |
| Layer 7 — Precision Detail | Micro-texture, pore distribution, wear patterns at proximity, trim and fastener detail |

---

## Contents

| File | What's in it |
|---|---|
| [`REFERENCE_GUIDE.md`](./REFERENCE_GUIDE.md) | Full methodology — all seven layers, all production stages, brief template |
| [`mistakes.md`](./mistakes.md) | 8 discipline-specific failure modes with fixes and production costs |
| [`checklist.md`](./checklist.md) | Printable pre-production checklist for 3D art, stage-organized |
| [`sources.md`](./sources.md) | Best reference sources for 3D art, organized by Pyramid layer |

---

## Related

- **AI skill pack:** [github.com/p4inz-code/3d-ref-skills](https://github.com/p4inz-code/3d-ref-skills) — 9 skills implementing this methodology for Claude Code, Cursor, Codex, Gemini. The most complete AI implementation of Reference Engineering currently available.
- **Example:** [`examples/game-environment/`](../../examples/game-environment/) — full seven-layer example for a post-apocalyptic modular ruins kit
- **Example:** [`examples/character-design/`](../../examples/character-design/) — full lifecycle example (brief v1 → v2) for a hero character

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
