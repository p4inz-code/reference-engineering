# 3D Art — Reference Engineering Checklist

Run before opening your DCC. Run again at each production stage.
Mark: ✓ Complete / ~ Partial / ✗ Missing / N/A Not applicable

---

## PRE-PRODUCTION (Run before first polygon)

### Layer 1 — Function & Context
- [ ] Real-world equivalent identified and photographed in use (not just at rest)
- [ ] Context reference gathered — asset in its environment
- [ ] Condition/age state defined — new, used, aged, damaged?
- [ ] Failure-state reference gathered if asset appears worn

### Layer 2 — Scale & Proportion
- [ ] Scale anchor documented (one unambiguous real-world dimension)
- [ ] Orthographic reference gathered (front, side, back, top)
- [ ] Head count written down (characters)
- [ ] Grid unit confirmed (environments)
- [ ] Platform polygon budget confirmed

### Layer 4 — Governing Rules
- [ ] Shape language written (not felt — written)
- [ ] Detail density described as a distribution, not a feeling
- [ ] Edge treatment specified (bevel width, behavior)
- [ ] Style era identified (pre-PBR / early-PBR / modern-PBR / path-traced)
- [ ] "What this asset NEVER looks like" list written (minimum 5 items)
- [ ] Style rules sourced from minimum 3 references

### Layer 5 — Lighting Context
- [ ] Target renderer confirmed
- [ ] Primary scene lighting condition identified
- [ ] Albedo target range for primary material noted (linear values)
- [ ] Roughness target range for primary material noted

---

## BLOCKOUT STAGE

- [ ] Scale anchor verified in scene with reference object (mannequin, door, car)
- [ ] Primary silhouette checked from front, side, back, top — not just hero angle
- [ ] Primary silhouette checked at target camera distance (not close-up)
- [ ] Primary silhouette checked in primary gameplay/scene pose (not just T-pose)
- [ ] No hero detail reference consulted at this stage
- [ ] Brief updated if blockout revealed new questions

---

## MID-MODEL STAGE

- [ ] Construction reference gathered — assembly joints, panel logic, fasteners
- [ ] Style rules checked — does secondary form development match Layer 4 rules?
- [ ] Detail density checked — is 70/30 (or whatever the rule is) holding?
- [ ] Edge treatment verified against written rule
- [ ] Brief updated with any mid-model gaps discovered

---

## UV / TEXTURE PREP STAGE

- [ ] Tiling surfaces identified — which areas can tile without visible repetition?
- [ ] Unique UV areas identified — which areas require unique UV space?
- [ ] Texel density target confirmed for primary LOD
- [ ] Texel density consistent across assets in the same set
- [ ] Seam placement reference checked — where are seams hidden in real construction?

---

## TEXTURING / SURFACING STAGE

- [ ] PBR calibration done in the delivery renderer (not the texturing tool)
- [ ] Albedo values checked against linear range targets (no pure black, no pure white)
- [ ] Roughness values sourced from reference, not from visual preference
- [ ] Metallic mask correct — oxide layers break metallic even on metal surfaces
- [ ] Wear pattern reference gathered — wear placed where it physically occurs
- [ ] Wear is NOT uniform — hotspots at edges, contact points, stress zones
- [ ] Color variation present in albedo — no flat single-color surfaces

---

## RIGGING STAGE (if applicable)

- [ ] Deformation zone reference gathered for each major joint
- [ ] Shoulder deformation: topology supports full overhead extension?
- [ ] Elbow/knee deformation: topology supports 140°+ flex?
- [ ] Spine deformation: topology supports full range in animation set?
- [ ] Cloth/costume elements: will these deform correctly or need cloth physics?

---

## HERO DETAIL STAGE

- [ ] Hero detail gathered only at this stage (not earlier)
- [ ] Micro-texture source identified — real macro photography, not renders
- [ ] Hero detail zones confirmed against camera distance test
- [ ] Back-of-asset detail reduced (confirm what camera actually sees)
- [ ] Craftwork detail (stitching, welds, fasteners) reference gathered

---

## PRE-DELIVERY

- [ ] Asset checked in delivery renderer under primary scene conditions
- [ ] Scale verified one final time in scene with reference geometry
- [ ] LOD chain produced and validated (if required)
- [ ] All Pyramid layers covered — no critical gaps remain open
- [ ] Brief vFinal written with retrospective notes

---

## COMMON GAPS IN 3D ART BY ASSET TYPE

| Asset Type | Most Commonly Missing |
|---|---|
| Game props (real-time) | Layer 5 (pipeline mismatch), Layer 2 (scale anchor) |
| Characters | Layer 6 (deformation reference), Layer 3 (pose silhouette) |
| Environments (modular) | Layer 2 (grid unit), Layer 4 (style rules across full set) |
| VFX | Layer 1 (real-world motion behavior), Layer 3 (timing reference) |
| Marketplace assets | Layer 5 (multiple renderer calibration), Layer 2 (scale for unknown scenes) |
| Stylized assets | Layer 4 (written rules — not just visual reference) |

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
