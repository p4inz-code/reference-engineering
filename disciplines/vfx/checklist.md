# VFX — Reference Engineering Checklist

Run before any simulation begins. Run again at each phase milestone.
Mark: ✓ Complete / ~ Partial / ✗ Missing / N/A Not applicable

---

## PRE-SIMULATION

### Layer 1 — Phenomenon Identity
- [ ] Phenomenon named precisely (not "fire" — what type of fire?)
- [ ] Narrative function defined: hero / supporting / ambient
- [ ] Real-world footage found and reviewed (not other CG — real footage)
- [ ] Camera distance and angle to effect documented
- [ ] Compositional context documented (what is behind/around the effect)

### Layer 2 — Timing and Scale
- [ ] Physical scale of effect defined
- [ ] Real footage frame counts documented: onset / peak / dissipation
- [ ] Timing converted to target frame rate
- [ ] Density range estimated from reference footage

### Layer 3 — Phase Reference (all three required before starting)
- [ ] Onset reference gathered (first 20% of effect life)
- [ ] Peak reference gathered (30–60% of effect life)
- [ ] Dissipation reference gathered (60–100% of effect life)

### Layer 4 — Governing Rules (complete before starting sim)
- [ ] Onset: core color / edge color / density / velocity documented
- [ ] Peak: core color / edge color / density / column dimensions documented
- [ ] Dissipation: color shift sequence / density curve documented
- [ ] "What this effect NEVER does" list written
- [ ] All color values documented as hex from real footage (not from memory)

### Layer 5 — Contextual Conditions
- [ ] Background plate (or proxy) in the reference board
- [ ] Plate lighting conditions documented
- [ ] Camera: lens / exposure / frame rate documented
- [ ] Real-time budget documented (if applicable): particles / draw calls / overdraw

### Layer 6 — Physical Behavior
- [ ] Key physical behaviors documented (buoyancy, turbulence type, density behavior)
- [ ] Pipeline-specific parameter targets estimated from physical reference
- [ ] Secondary elements identified (embers, debris, spray — yes or no)

---

## ONSET MILESTONE

- [ ] Onset phase timing matches reference frame count
- [ ] Onset color matches reference hex values
- [ ] Onset energy/velocity matches real footage behavior
- [ ] Transition to peak phase is visible in the current sim

---

## PEAK MILESTONE

- [ ] Peak density matches reference
- [ ] Peak color (core vs. edge) matches reference hex values
- [ ] Peak turbulence scale matches reference
- [ ] Peak timing from onset matches documented frame count
- [ ] Background plate composite test run — color and exposure check

---

## DISSIPATION MILESTONE

- [ ] Dissipation color shift sequence matches reference
- [ ] Dissipation rate matches documented density curve
- [ ] Edge behavior at dissipation matches reference
- [ ] Secondary elements (embers, trailing smoke) match reference if present

---

## PRE-DELIVERY

- [ ] Full effect reviewed against background plate composite
- [ ] Color temperature of effect matches plate
- [ ] Exposure of effect matches plate lighting
- [ ] Motion blur matches plate camera settings
- [ ] Effect timing validated against editorial cut (is the effect the right length?)
- [ ] Loop point invisible (if looping effect)
- [ ] Real-time performance confirmed at budget (if real-time)

---

## COMMON GAPS IN VFX BY EFFECT TYPE

| Effect Type | Most Commonly Missing |
|---|---|
| Fire | Layer 6 (blackbody color behavior), Layer 3 (onset reference) |
| Explosion | Layer 2 (timing from real footage), Layer 3 (dissipation reference) |
| Water/fluid | Layer 6 (surface tension vs. gravity scale behavior) |
| Smoke | Layer 3 (dissipation — most smoke reference is onset/peak) |
| Magic/stylized | Layer 1 (indirect reference strategy), Layer 4 (shape language rules) |
| Looping ambient | Layer 7 (loop technique reference) |
| Weather | Layer 6 (large-scale atmospheric behavior), Layer 5 (composite integration) |

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
