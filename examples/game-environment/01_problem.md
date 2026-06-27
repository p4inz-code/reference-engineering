# Game Environment — Problem & Brief

**Project:** Post-Apocalyptic Modular Ruins Kit (UE5, third-person)
**Stage:** Pre-production
**Date:** [project start]
**Brief version:** 1.0

---

## Production Questions This Brief Must Answer

### Layer 1 — Function & Context

**Narrative function:**
- [ ] What caused the collapse? (nuclear? pandemic? societal? — each produces different visual evidence)
- [ ] How long has it been since collapse? (15–20 years per brief — what does 15–20 years of abandonment actually look like?)
- [ ] Who (if anyone) inhabits these ruins now? (affects what's been moved, scavenged, or modified post-collapse)
- [ ] What happens in this environment during gameplay? (combat, exploration, stealth — affects sight lines, cover density, navigation pathways)

**Architectural function:**
- [ ] What types of structures make up an Eastern European city block? (not "buildings" — specific types: residential, commercial, institutional, industrial)
- [ ] What is the standard floor-to-floor height in Soviet-era residential construction?
- [ ] What materials are standard in Eastern European brutalist/Soviet residential buildings?
- [ ] How do these buildings fail? (concrete delamination, rebar exposure, floor collapse patterns)

### Layer 2 — Scale & Proportion

- [ ] Standard Soviet-era apartment block: floor height, wall thickness, window module
- [ ] Standard door dimensions for this building type
- [ ] Street width (curb-to-curb) for Eastern European city blocks of this era
- [ ] Third-person camera height and distance — what height objects become obstructions vs. cover?
- [ ] Modular grid unit: what size module covers ≥80% of required assembly combinations?

### Layer 3 — Production Stage Reference (planned per stage)

*Silhouette stage:*
- [ ] Orthographic reference for Soviet-era apartment buildings (front, side)
- [ ] Clear silhouette reads for major ruin states: intact, damaged, collapsed-partial
- [ ] Module silhouette variety: how many distinct silhouette shapes needed for visual interest?

*Blockout stage:*
- [ ] Mass proportion reference for these building types
- [ ] Street/alley proportion reference (how narrow is too narrow for third-person navigation?)
- [ ] Coverage ratio: what percentage of a city block is building vs. open space?

*UV/texture prep stage:*
- [ ] Which surfaces tile and which are unique?
- [ ] What texel density is appropriate for a hero environment asset at UE5 Fab standard?

*Hero detail stage:*
- [ ] What does 15–20 year concrete degradation actually look like? (not generic "damaged")
- [ ] How does vegetation reclaim concrete at 15–20 years? (grass through cracks? trees? vines?)
- [ ] What specific debris types appear after societal collapse at 15-year mark?

### Layer 4 — Style Rules

- [ ] What productions define "grounded realism with slight desaturation" for post-apocalyptic environments?
- [ ] What is the desaturation degree? (TLOU, Fallout 4, Metro Exodus — very different amounts)
- [ ] What level of stylization is acceptable in a "grounded" read?
- [ ] What does this style NEVER do? (what would look wrong immediately)

### Layer 5 — Lighting Context (UE5)

- [ ] What sky/HDRI conditions define the target look? (overcast? golden hour? harsh midday?)
- [ ] Will Lumen (real-time GI) be used? This affects how surfaces read
- [ ] What time-of-day range does gameplay cover? (affects roughness calibration — surfaces read differently under harsh sun vs. overcast)
- [ ] Nanite use? (affects polygon budget decisions and detail strategy)

### Layer 6 — Material & Surface

- [ ] Concrete aging behavior at 15–20 years: delamination pattern, rebar exposure rate, moss/lichen coverage
- [ ] Window glass behavior at collapse stage (broken? mostly intact? safety glass crumble vs. shard?)
- [ ] Paint condition on Soviet-era exteriors at 15–20 years without maintenance
- [ ] Metal corrosion rate (pipes, railings, window frames) for this climate

### Layer 7 — Hero Detail (defer to mid-production)

- [ ] Specific graffiti/marking layers that read as authentic to this setting
- [ ] Nature reclamation micro-detail: root patterns in concrete, specific moss species
- [ ] Interior glimpse detail (visible through broken windows): what does an abandoned Soviet apartment contain?

---

## Reference Tier Plan

| Question category | Expected tier | Source plan |
|---|---|---|
| Soviet architecture specs | Primary | Architecture databases, construction standards |
| Collapse timeline visual evidence | Primary | Real-world photogrammetry, war documentation |
| Style rules | Secondary | TLOU, Metro, S.T.A.L.K.E.R. — game productions |
| 15-20yr abandonment look | Primary | Chernobyl/Pripyat documentation (exact match for timeline and building type) |
| UE5 rendering context | Primary | UE5 documentation, Fab quality standards |

---

## Gap Risk Assessment

| Gap | Risk if unresolved | Priority |
|---|---|---|
| Modular grid size undecided | High — all modules must share the grid | CRITICAL |
| Soviet building dimensions not confirmed | High — scale will be wrong | CRITICAL |
| Style desaturation degree unclear | High — art direction contested mid-production | HIGH |
| Lumen/Nanite spec not confirmed | Medium — affects LOD and polygon strategy | HIGH |
| Collapse cause undefined | Low — aesthetic, can default to generic | LOW |

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
