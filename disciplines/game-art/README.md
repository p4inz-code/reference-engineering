# Reference Engineering — Game Art

> Systematic pre-production reference methodology for game artists working on characters, environments, props, and UI for games.

**Discipline:** Game Art
**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Who This Is For

Game artists working on 2D and 3D art production specifically for games:
character art, environment art, prop art, concept art, UI art, and icon
design. The methodology accounts for the constraints specific to game art
that differ from general 3D art or illustration: polygon budgets, texel
density standards, LOD requirements, in-engine rendering constraints,
and the relationship between art and gameplay readability.

Game art reference work must account for gameplay before aesthetics.
An environment that looks beautiful but obscures enemy visibility is a
design failure. A character that reads as a hero from the front but is
indistinguishable from an NPC at gameplay distance has failed. Reference
Engineering in game art starts with gameplay readability, not visual quality.

---

## What Reference Engineering Solves in Game Art

The central reference failure in game art is building for renders, not
for gameplay. Reference is gathered from ArtStation portfolio renders —
close-up, hero-lit, high-quality renders — and the art is produced to
that standard. In gameplay, the art is seen from a distance, under dynamic
lighting, at 30–60fps, competing with UI elements and other characters.
The reference didn't match the production context.

Reference Engineering in game art requires gathering reference for the
actual gameplay context — the camera distance, the lighting conditions,
the competing visual elements — and for the technical constraints — the
polygon budget, the texel density, the LOD chain requirements.

---

## The Pre-Production Questions Game Art Must Answer

- [ ] What is the gameplay camera distance and angle? (This is Layer 1, not Layer 7)
- [ ] What is the polygon budget for this asset class at the target LOD?
- [ ] What is the texel density standard for this asset at the primary LOD?
- [ ] What is the rendering pipeline and what does it support? (PBR? mobile? stylized?)
- [ ] What is the gameplay readability requirement? (Can the player distinguish friend from enemy? Hero from prop? Interactive from static?)
- [ ] What style is the game art in, and what are the written rules of that style?
- [ ] What are the LOD transition distances and what geometry budget applies at each?
- [ ] What is the art direction target — which specific shipped games are the visual reference?

---

## Pyramid Layer Map for Game Art

| Pyramid Layer | What It Means in Game Art |
|---|---|
| Layer 1 — Function & Context | Gameplay function, camera distance/angle, readability requirements, player expectation |
| Layer 2 — Scale & Proportion | Polygon budget, texel density, scale relative to player character, LOD chain plan |
| Layer 3 — Stage Reference | Concept/silhouette; blockout; texturing; in-engine validation per stage |
| Layer 4 — Governing Rules | Game's visual style rules extracted from art direction targets — written parameters |
| Layer 5 — Lighting Context | In-engine lighting conditions, dynamic lighting range, platform rendering pipeline |
| Layer 6 — Behavior & Construction | LOD behavior, animation deformation, material behavior in engine |
| Layer 7 — Precision Detail | Hero detail for close camera moments, cut-scene quality, marketing render quality |

---

## Contents

| File | What's in it |
|---|---|
| [`REFERENCE_GUIDE.md`](./REFERENCE_GUIDE.md) | Full methodology, all seven layers, readability framework, brief template |
| [`mistakes.md`](./mistakes.md) | 7 game-art-specific failure modes |
| [`checklist.md`](./checklist.md) | Pre-production checklist with gameplay readability focus |
| [`sources.md`](./sources.md) | Game art reference sources by layer |

---

## Related

- **Discipline:** [`disciplines/3d-art/`](../3d-art/) — general 3D art methodology (game art is a specialization of this)
- **Example:** [`examples/game-environment/`](../../examples/game-environment/) — full worked example
- **Example:** [`examples/character-design/`](../../examples/character-design/) — character production with gameplay context

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
