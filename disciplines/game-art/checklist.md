# Game Art — Reference Engineering Checklist

Run before opening your DCC. Run again at each production milestone.
Mark: ✓ Complete / ~ Partial / ✗ Missing / N/A Not applicable

---

## PRE-PRODUCTION

### Gameplay Context (fill this first — before any other reference)
- [ ] Camera distance documented: close / mid / far / variable
- [ ] Camera angle documented: FPS / TPS / isometric / side / top-down
- [ ] Primary lighting conditions in-game documented
- [ ] Competing visual elements documented (what else is on screen)
- [ ] Target platform renderer confirmed

### Layer 1 — Gameplay Function and Readability
- [ ] Asset's gameplay function stated (not appearance — function)
- [ ] Readability requirement stated: what must player correctly identify at gameplay distance?
- [ ] In-game screenshots gathered from comparable game at target camera distance
- [ ] Color communication role defined: player / enemy / interactive / dressing

### Layer 2 — Technical Budget
- [ ] Triangle budget confirmed for this asset class at LOD0
- [ ] Texture resolution confirmed
- [ ] Texel density standard confirmed (pixels per cm at primary LOD distance)
- [ ] LOD chain plan documented (LOD0 through LODn, with distance thresholds)
- [ ] Scale anchor confirmed relative to player character

### Layer 4 — Style Rules
- [ ] Art direction target games identified (specific shipped games)
- [ ] Style rules extracted and written as parameters (not as descriptions)
- [ ] Color architecture documented with gameplay function for each color
- [ ] "What this asset NEVER looks like" list written
- [ ] Rules sourced from minimum 3 comparable game assets

---

## CONCEPT / SILHOUETTE STAGE

- [ ] Silhouette reads correctly at gameplay camera distance (not just at close-up)
- [ ] Silhouette differentiates asset from competing visual elements
- [ ] Silhouette consistent with style rules (shape language check)
- [ ] Readability requirement verified at this stage

---

## BLOCKOUT STAGE

- [ ] Scale validated against player character in-engine
- [ ] Primary mass proportions match style rules
- [ ] No detail added — blockout only
- [ ] LOD0 topology plan confirmed before high-poly begins

---

## HIGH-POLY / SCULPT STAGE (if applicable)

- [ ] Detail reference gathered for this specific surface type
- [ ] Detail density matches style rules (not personal aesthetic)
- [ ] Detail placed where it will survive bake to low-poly
- [ ] Detail at non-visible faces minimized

---

## RETOPO / LOW-POLY STAGE

- [ ] Triangle count within confirmed budget
- [ ] Topology supports deformation at all required joints (characters)
- [ ] Topology efficient — no unnecessary edge loops
- [ ] Silhouette preserved at target polygon count

---

## UV STAGE

- [ ] Texel density matches confirmed standard
- [ ] Tiling areas identified and UV'd to tile
- [ ] Unique areas UV'd with appropriate texel allocation
- [ ] Seams placed where they won't be visible at gameplay camera angle

---

## TEXTURE / SURFACE STAGE

- [ ] All texturing done in the delivery renderer (not in Marmoset or external tool)
- [ ] Albedo values within correct linear range (no pure black, no pure white)
- [ ] Roughness values sourced from reference, validated in-engine
- [ ] Color matches color architecture rule for this asset's gameplay role
- [ ] Material reads correctly at gameplay camera distance (not just close-up)

---

## IN-ENGINE VALIDATION (mandatory before delivery)

- [ ] Asset placed in game scene with actual game lighting
- [ ] Asset validated at actual gameplay camera distance
- [ ] Asset validated with competing visual elements present
- [ ] Readability requirement verified in actual game context
- [ ] Texel density consistent with other assets in the same scene
- [ ] LOD transitions validated (no visible pop)
- [ ] Mobile build validation completed (if mobile target)

---

## PRE-DELIVERY

- [ ] All LOD levels complete and validated
- [ ] Asset reads correctly at all LOD distances
- [ ] Color architecture role verified in context
- [ ] Style rules compliance confirmed
- [ ] Brief vFinal written

---

## COMMON GAPS BY GAME ART ASSET TYPE

| Asset Type | Most Commonly Missing |
|---|---|
| Player character | Layer 4 (color differentiation from enemies), Layer 6 (deformation at all joints) |
| Enemy characters | Layer 1 (readability at combat camera distance), Layer 4 (faction color rules) |
| Environment modules | Layer 2 (texel density consistency), Layer 6 (LOD chain plan) |
| Hero props | Layer 1 (interactive vs. decorative readability), Layer 5 (in-engine validation) |
| Background dressing | Layer 7 (over-invested — background needs less, not more) |
| UI art | Layer 5 (display resolution range), Layer 1 (readability at TV distance for console) |

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
