# Character Design — Problem & Brief

**Project:** Archaeologist-Adventurer Hero Character (Stylized Action RPG, UE5)
**Stage:** Pre-production
**Brief version:** 1.0

---

## The Problem Without Reference Engineering

Character design briefs fail in two specific ways that Reference Engineering
prevents:

**Failure Mode A — Archetype Drift:** The designer starts from the archetype
("Indiana Jones type") and works from memory of that archetype. Every
decision is made from a remembered impression rather than documented analysis.
The result looks like the archetype — which means it looks like a copy of
the archetype. No specific rule set was extracted, so no specific character
was designed. A recognizable type was reproduced.

**Failure Mode B — Stage Collapse:** All reference is gathered at once before
production starts. The silhouette reference, the material reference, the
hero detail reference, and the rig deformation reference are all in the same
board. Production starts, and the board is "used" — but using it means
looking at it and making intuitive decisions rather than consulting specific
reference for the specific decision at hand. The board's comprehensiveness
disguises the absence of stage-appropriate organization.

Reference Engineering prevents Archetype Drift by requiring rule extraction
from the archetype analysis — not just visual collection. It prevents Stage
Collapse by explicitly assigning reference to production stages before the
first polygon is placed.

---

## Production Questions — Brief v1

### Layer 1 — Function & Context

- [ ] What is the character's narrative role? (protagonist, companion, NPC — and what does that role demand visually?)
- [ ] What is the character's functional role in gameplay? (combat, exploration, puzzle — what does the body need to do?)
- [ ] What cultural and historical context does "30s archaeologist-adventurer" actually mean? (real 1930s fieldwork vs pulp fiction version vs cinematic version — these are different things)
- [ ] What is the character's relationship to danger? (competent survivor vs fearless hero vs reluctant adventurer — each reads differently in proportion and costume)
- [ ] Who is the player identifying with? What does the player need to project onto this character?

### Layer 2 — Scale & Proportion

- [ ] Head count for this style range? (realistic: 7–7.5 heads; stylized hero: 6.5–7; cartoon: 5–6)
- [ ] What proportion exaggerations are appropriate for "slightly exaggerated" at this stylization level?
- [ ] Shoulder-to-hip ratio target?
- [ ] Hand size — bigger hands read better at distance and in action; what's the reference for this style?
- [ ] What are the rig requirements that constrain proportion? (shoulder deformation needs specific geometry; the proportion decision must account for how it deforms)

### Layer 3 — Production Stage (Silhouette)

- [ ] What is the primary silhouette read at third-person camera distance? (what 3–4 shapes make this character instantly recognizable?)
- [ ] What accessories/costume elements contribute to the silhouette? (hat, bag, tools — what reads at distance?)
- [ ] What poses will this character be in most frequently? (idle, running, combat — the silhouette must work in all primary poses, not just T-pose)
- [ ] How different is the silhouette from the camera's typical angle vs T-pose orthographic?

### Layer 4 — Governing Rules

- [ ] What specific visual rules define "stylized realism" at this level? (how many head counts, what bevel behavior, what surface complexity)
- [ ] What is the shape language? (hard vs soft, geometric vs organic — character design shape language must be deliberate)
- [ ] What costume design rules define the "30s adventurer" archetype vs the Hollywood version vs the pulp fiction version?
- [ ] What does this character NEVER look like? (most important constraint — what would break the read immediately?)

### Layer 5 — Contextual Conditions

- [ ] UE5 third-person camera: typical distance from character, angle, and field of view?
- [ ] What LOD distance is the hero budget calibrated for?
- [ ] What lighting conditions does the character appear in primarily? (outdoor adventure = harsh sun and shadow; underground = dramatic low-key; mixed?)
- [ ] Skin and hair: what rendering approach? (Lumen + subsurface? Groom system for hair?)

### Layer 6 — Behavior & Construction (Rig Deformation)

- [ ] What deformation zones need dedicated reference? (shoulder, elbow, knee, wrist, spine — all require topology decisions that reference must inform)
- [ ] What costume elements will deform? (cloth sim? rigid? mixed?)
- [ ] What is the animation priority? (what actions does this character do most — the deformation reference must match)

### Layer 7 — Precision Detail (Defer to v2)

- [ ] Fabric micro-detail for costume elements
- [ ] Skin pore distribution and SSS zone reference
- [ ] Weathering and wear patterns on costume and equipment

---

## Reference Tier Plan

| Question category | Expected tier | Source plan |
|---|---|---|
| 30s archaeologist reality | Primary | Historical photography, expedition documentation |
| Hollywood version of archetype | Primary | Film stills — Indy, Allan Quatermain, pulp covers |
| Stylized realism proportion rules | Secondary | Comparable stylized RPG characters |
| Shape language for hero archetype | Secondary | Character design analysis, animation studio references |
| UE5 deformation requirements | Primary | UE5 documentation, rigging community resources |

---

## Gap Risk Assessment

| Gap | Risk | Priority |
|---|---|---|
| Head count undecided | HIGH — all proportions derive from this | CRITICAL |
| Silhouette pose set undecided | HIGH — silhouette in T-pose ≠ silhouette in gameplay | CRITICAL |
| Shape language not defined | HIGH — all design decisions have no governing rule | HIGH |
| Deformation zones not researched | MEDIUM — will surface at rigging stage | HIGH |

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
