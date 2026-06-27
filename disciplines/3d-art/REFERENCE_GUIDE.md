# 3D Art — Reference Engineering Guide

Full methodology for gathering, analyzing, and organizing reference across
the complete 3D production arc: from initial brief through delivery.

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Function & Context

### What to Find

**Existence reference:** Photographs and documentation of the real-world thing
(or its closest real-world equivalent). Not renders. Not concept art. The actual
object, material, or environment as it exists — at rest and in use.

**In-use reference:** The thing being operated, inhabited, or interacted with.
A weapon being held. A door being opened. A building being entered. Functional
reference shows you what the static reference cannot: how the thing relates
to a human body, how it moves, what it looks like from the angles that matter.

**Context reference:** The thing in its environment. Not a studio shot. The
sci-fi corridor with people in it. The prop on the table it belongs on. The
character in the world they inhabit. Context reference calibrates scale,
relationship to surroundings, and what visual elements must read clearly
against the background.

**Failure-state reference:** What the thing looks like when worn, damaged,
aged, or broken. For any prop that appears used rather than new, failure-state
reference is Layer 1, not Layer 6 — it defines what the asset fundamentally is.

### Discipline-Specific Questions

- What does this asset do, and does it need to look like it works?
- What is its relationship to the human body? (held, worn, inhabited, operated from a distance?)
- Is this asset seen in motion or predominantly static?
- What story does this asset's condition tell? (new, used, aged, damaged?)

### Where to Look

YouTube (search behavior and use, not appearance), manufacturer documentation
for real-world equivalents, historical archives for period-appropriate assets,
Wikimedia Commons for public domain functional photography.

---

## Layer 2 — Scale & Proportion

### What to Find

**Dimension documentation:** Technical specifications, engineering drawings,
or measured photographs that give absolute dimensions. Not estimated from
visual reference — actual measurements.

**Scale anchor:** The single reference that locks scale unambiguously. Usually
a human figure in the frame, a door, or a known-size object. Every other
scale decision derives from the anchor.

**Orthographic reference:** Front, side, top views. Blueprints when available
(vehicles, weapons, aircraft — these often have excellent orthographic documentation).
For characters: turnaround sheets, anatomy charts with head-count marked.

**Proportion system:** For characters — head count, body proportion ratios.
For environments — modular grid, structural bay, floor-to-floor height.
For props — overall ratio of primary mass to secondary elements.

### Discipline-Specific Questions

- What is the one dimension that, if wrong, makes everything else wrong?
- What is my platform's polycount budget and how does it constrain the level of geometric detail at real-world proportions?
- What is the texel density standard for this asset at its target LOD distance?
- For characters: what head count matches the production style? What does that head count look like in the target DCC at the target camera distance?

### Where to Look

Dimensions.com (human-scale reference), The-Blueprints.com (vehicles, weapons,
aircraft, machinery), manufacturer technical datasheets, UE5/Unity documentation
for platform-specific proportion constraints, ArtStation for style-matched
character turnarounds.

---

## Layer 3 — Stage-Appropriate Reference

### The 3D Art Production Stages

Reference is not gathered all at once. It is gathered in passes, one per
production stage. Using the wrong stage's reference for the current stage
is one of the most invisible failure modes in 3D production.

| Stage | What You're Building | Reference Needed |
|---|---|---|
| Concept / pre-production | Brief, questions, direction | All Layer 1–4 reference |
| Blockout | Primary masses, proportions | Orthographic, silhouette, primary mass reference — NOT detail |
| Mid-model | Secondary forms, panel lines, module logic | Construction and assembly reference, style rule verification |
| UV / texture prep | Seam placement, texel density planning | Tiling reference, unique vs. tiling surface decisions |
| Texturing / surfacing | Material values, surface variation, detail | PBR channel reference, micro-texture, wear patterns |
| Rigging (character) | Deformation zones, topology decisions | Anatomy in motion, deformation reference for each zone |
| Hero detail | Fine-craft, micro-surface, proximity detail | Close-up photography, material macro reference |
| Lighting / presentation | How asset reads in scene conditions | Scene lighting reference, comparable assets in similar conditions |

### Gathering by Stage

**At blockout stage:** Gather only reference that answers the blockout question:
is the primary mass correct? Orthographic views. Side-profile silhouettes.
Primary proportion studies. Do NOT add hero detail reference to the board
at blockout stage — it will be used to make blockout decisions and will
produce incorrect decisions.

**At UV stage:** Gather tiling seam reference. Look at how comparable assets
handle the transition between tiling and unique areas. What areas can tile
without visible repetition? What areas require unique UV space because pattern
repetition would be visible?

**At hero detail stage (only):** Close-up photography. Macro surface reference.
This is when Layer 7 reference is appropriate — not before.

---

## Layer 4 — Governing Rules

### What to Extract

**Shape language:** Is the style hard-edged or soft? Geometric or organic?
Where does the style use hard transitions and where does it use soft ones?
What is the bevel behavior — tight and precise, or broad and soft? Write it down.

**Detail density map:** Where is there detail and where is there rest?
A useful format: describe the detail distribution as a percentage.
"70% of the surface is negative space, 30% is information clusters."
Or zone-map it: "high detail at mechanical joints, low detail at structural panels."

**Surface quality:** Where on the matte-to-specular spectrum does this style live?
What is the roughness range for the primary materials? Does the style use
subsurface scattering? Does it suggest wetness?

**Edge treatment:** What happens at the edges between planes? Sharp? Chamfered?
Beveled with a specific pixel width at the target LOD? Does the style support
knife-edge transitions or does everything have a softened edge?

**Style era:** What production era does this style assume? Pre-PBR? Early PBR?
Modern PBR? Path-traced? This affects albedo ranges, specular behavior assumptions,
and what the reference images are actually showing.

**What the style never does:** Write this list before production starts.
"This style never uses rounded corners on mechanical elements. It never has
decorative surface detail that doesn't serve a functional read. It never
uses pure black as a surface color." This list is checked against every
decision throughout production.

### Minimum Source Requirement

Style rules extracted from a single source carry that source's idiosyncrasies.
Minimum three sources for any rule that will govern the whole production.
If three sources agree, the rule is the style. If they disagree, the
disagreement is information — investigate why before writing the rule.

---

## Layer 5 — Lighting Context

### What to Find

**Target renderer conditions:** What renderer will this asset live in?
Real-time (UE5 Lumen, Unity HDRP, Godot)? Offline (V-Ray, Arnold, Cycles)?
Each has different behavior for the same PBR values. Reference gathered
from the wrong renderer will produce incorrectly calibrated materials.

**Scene lighting type:** HDRI conditions (overcast, harsh sun, golden hour)?
Three-point studio lighting? Dynamic real-time lighting with Lumen GI?
Gather reference photographed under similar conditions to your target.

**Time-of-day range:** If the asset appears in multiple lighting conditions
(outdoor game environment), gather reference for the full range. A material
calibrated only for overcast conditions will fail under harsh midday sun.

**Platform rendering constraints:** Mobile has different lighting capabilities
than console. A mobile game asset needs reference calibrated for what mobile
renderers can actually represent — not what a path tracer would show.

### Albedo Calibration Reference

Real-world albedo values in linear space are commonly misunderstood:

| Material | Linear albedo range | Common mistake |
|---|---|---|
| Charcoal / darkest concrete | 0.02–0.06 | Painted black (#000000 = 0.00) |
| Dark wood, aged metal | 0.05–0.15 | Painted dark gray |
| Mid concrete, stone | 0.20–0.40 | Usually correct |
| Light plaster, sand | 0.45–0.60 | Often too bright |
| Snow, white paper | 0.80–0.90 | Painted white (#ffffff = 1.00) |
| Pure white | 0.90–0.95 | Never 1.0 in real materials |

If your darkest materials are at 0.00 and your brightest at 1.00, your
albedo map is almost certainly wrong.

### Where to Look

Polyhaven (HDRI environments, free), Megascans preview images for PBR
calibration reference, UE5/Unity documentation for renderer-specific
behavior, Lumen best practices documentation.

---

## Layer 6 — Material & Surface

### What to Find

**Construction reference:** How is the thing made? What are the assembly
joints, seams, welds, stitching, and fasteners? Construction reference
informs where wear begins, where seam geometry belongs, and what the
material is doing structurally rather than just visually.

**Physical behavior reference:** How does the material behave when stressed,
aged, or damaged? Metal dents, bends, corrodes. Concrete carbonates,
spalls, grows moss. Leather cracks at flexion points, darkens at oils.
Fabric frays at edges, pills at friction zones, sags at weight-bearing
points. This behavior is what makes surfaces read as real.

**PBR channel reference per material zone:** Not just one roughness value
for the whole asset. Each material zone — metal, worn paint, exposed base
material, rust, fabric — has its own channel targets. Gather reference
for each zone explicitly.

**Wear pattern reference:** Where does the specific type of wear on this
specific material type occur first, and in what progression?

### PBR Reference by Material Class

| Material Class | Albedo (linear) | Roughness | Metallic | Notes |
|---|---|---|---|---|
| Clean metal | 0.40–0.70 (by hue) | 0.10–0.30 | 0.95–1.0 | Fresnel dominant |
| Worn/oxidized metal | 0.05–0.20 | 0.60–0.90 | 0.0–0.4 | Oxide layer breaks metallic |
| Concrete (aged) | 0.25–0.45 | 0.80–0.95 | 0.0 | Cool gray, not neutral |
| Wood (untreated) | 0.05–0.15 | 0.75–0.95 | 0.0 | Very dark in linear |
| Fabric (dark) | 0.02–0.10 | 0.90–1.0 | 0.0 | Darkest in linear space |
| Skin | 0.25–0.45 | 0.45–0.70 | 0.0 | SSS required for real read |
| Painted surface | 0.05–0.55 (hue-dependent) | 0.40–0.80 | 0.0 | Sheen varies by paint type |
| Glass | 0.02–0.05 | 0.02–0.15 | 0.0 | Opacity + IOR govern read |
| Rubber/plastic | 0.02–0.15 | 0.70–0.95 | 0.0 | Very dark, high roughness |

---

## Layer 7 — Precision Detail

### What to Find

**Micro-texture reference:** Close-up photography of the real material surface.
Not art, not renders — real-world macro photography. What is the texture
frequency? What direction does grain run? What is the pore or grain size
relative to the object's dimensions?

**Wear pattern at proximity:** Where specifically does wear occur at the
scale of individual scratches, tool marks, and contact points?
A boot is scuffed at the toe cap. A gun has finish wear at the grip
contact points and at the ejection port. These are specific, not random.

**Craftwork reference:** Stitching, welding, riveting, fastener heads,
surface treatment variations. The specific visual language of how this
thing was made, at close range.

**Detail zoning:** Not all surfaces need hero detail. Identify which
surfaces the camera will actually reach at hero detail distance before
investing in micro-texture for the full asset. The back of a character's
jacket in a third-person game will never be seen at the distance that
micro-texture reads.

### Where to Look

Polyhaven (free CC0 surface photography), Quixel Megascans (free with
UE5, reference-quality surface documentation), Unsplash/Pexels for
macro photography, The British Museum collection online for historical
artifact close-up reference (CC licensed).

---

## The 3D Art Reference Brief

Fill this out before opening your DCC. Update it at each production milestone.

```
PROJECT: [asset name]
TYPE: [prop / character / environment / VFX]
PLATFORM: [game engine / offline render]
CAMERA DISTANCE: [FPS / TPS hero / isometric / environment bg]
TARGET LOD: [polygon count range]
DATE: [brief version date]

LAYER 1 — FUNCTION & CONTEXT
Real-world equivalent:
In-use reference source:
Context reference source:
Condition / age state:

LAYER 2 — SCALE & PROPORTION
Primary dimension (the unambiguous one):
Scale anchor:
Orthographic source:
Head count (if character):
Grid unit (if environment):

LAYER 3 — CURRENT STAGE
Current stage: [ ] Blockout  [ ] Mid-model  [ ] UV  [ ] Texture  [ ] Hero detail
Stage reference gathered:
Stage reference gaps:

LAYER 4 — GOVERNING RULES
Shape language:
Detail density:
Surface quality:
Edge treatment:
Style era:
What this asset NEVER looks like:

LAYER 5 — LIGHTING CONTEXT
Renderer:
Primary lighting condition:
Albedo range for primary material:
Roughness range for primary material:

LAYER 6 — MATERIAL & SURFACE
Primary material PBR targets:
Secondary material(s):
Construction / assembly logic:
Wear and aging: what, where, and in what progression:

LAYER 7 — HERO DETAIL (complete only when at hero stage)
Micro-texture source:
Primary wear pattern at proximity:
Craftwork detail reference:

GAPS (questions unanswered after this brief):
Critical:
High:
Low:

BRIEF VERSION: [v1.0 / v2.0 / vFinal]
```

---

## When to Re-Run Reference Work

Re-run the brief (run Core Loop again) when:
- Blockout is complete — does the proportion reference hold?
- You reach a material you haven't built yet
- The art director gives new direction that changes Layer 4 rules
- You discover the scale is wrong (immediately — scale errors compound)
- Production stalls on a decision and no reference answers it
- You move to hero detail stage (Layer 7 reference pass)

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
