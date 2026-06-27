# Game Environment — Outcome & Decisions

**Brief version:** 1.1
**Stage:** Production-ready
**Decision log:** Every decision below traces to a specific rule or reference
from `02_process.md`. Undocumented assumptions are flagged explicitly.

---

## Structural Decisions

**D01 — Modular grid: 0.5m**
All modules snap to a 0.5m grid.
No exceptions without documented justification in the production log.
Reference: derived from Soviet construction standard SNiP II-Л.1-71 (T1)
Confidence: CONFIRMED — real measurements, no translation required.

**D02 — Floor-to-floor height: 2.5m (5 grid units)**
Exact value from construction documentation.
Applies to all residential floor modules. Commercial ground floor: 3.5m
(documented exception — Soviet-era ground floor commercial standard).
Reference: SNiP II-Л.1-71 (T1)
Confidence: CONFIRMED

**D03 — Module set: facade panel 3.0m × 2.5m as primary unit**
One floor, one residential unit width. Confirmed against real Khrushchyovka
proportions. All other modules derive from this base unit or are
multiples/fractions of it.
Reference: Khrushchyovka architectural documentation (T1)
Confidence: CONFIRMED

**D04 — Minimum corridor width: 1.5m clear**
Derived from UE5 mannequin (180cm) + 0.5m clearance each side — rounding
down to fit the grid. Third-person camera navigates this comfortably at
standard settings; confirmed by test in UE5.
Reference: UE5 default mannequin spec (T1), grid derivation
Confidence: CONFIRMED — production-tested

---

## Damage Logic Decisions

**D05 — Damage hotspot placement: corners and reinforcement joints**
Never uniform across a surface. Damage originates at corners (thermal
cycling, stress concentration), window reveals (waterproofing failure),
and horizontal reinforcement joints (rebar corrosion expansion).
Reference: Pripyat photographic documentation, 2000–2006 (T1)
Confidence: CONFIRMED — primary reference, exact timeline and building type match

**D06 — Collapse type: floor pancake, not diagonal cut**
Structural collapse in this building type follows floor-level horizontal
failure, not diagonal or arbitrary geometry. Diagonal damage cuts are
rejected as visually incorrect for this building type.
Reference: Structural engineering documentation (T1), Pripyat collapse documentation (T1)
Confidence: CONFIRMED

**D07 — Three ruin states defined**
State 1 (Intact-Damaged): facade standing, windows gone, vegetation at base, spalling at joints.
State 2 (Partial Collapse): one section or floor has pancaked, interior floors visible.
State 3 (Standing Fragments): wall sections only, rubble field dominant.
Intermediate states are blends of these — not additional defined states.
Reference: Pripyat documentation (T1), S.T.A.L.K.E.R. 2 environmental design (T2)
Confidence: CONFIRMED (state definition), SUPPORTED (blending approach)

---

## Material & PBR Decisions

**D08 — Concrete albedo: 0.30–0.45 linear, cool gray base**
Calibrated to Lumen outdoor overcast conditions. Not pure gray — slight
blue shift (#707878 approximate). Carbonation surface layer (top 10mm):
0.40–0.50 (lighter, chalkier).
Reference: UE5 Lumen documentation (T1), Megascans calibration data (T1)
Confidence: CONFIRMED

**D09 — Concrete roughness: 0.85–0.95 across all states**
No specular on concrete in any aging state. The only surface with specular
below 0.80 is standing water (0.05–0.15).
Reference: Metro Exodus material approach (T2), physical material data (T3)
Confidence: SUPPORTED — T2 confirmed against T3 principle. Flag for T1
confirmation if Megascans concrete scan data is acquired.

**D10 — Rust albedo: 0.04–0.12 linear**
Counterintuitively dark. Despite appearing orange, iron oxide in linear
color space is very dark. Critical for correct Lumen behavior — wrong
rust albedo will read incorrectly under real-time GI.
Reference: Megascans rust material data (T1), PBR physics documentation (T1)
Confidence: CONFIRMED

**D11 — Vegetation color: more saturated than architecture**
Nature wins the color contrast. Vegetation is the most saturated element
in the scene. Architecture is desaturated. This contrast is the primary
visual rule of the "beautiful ruin" read.
Reference: The Last of Us Part I environmental design (T2), S.T.A.L.K.E.R. 2 (T2)
Confidence: SUPPORTED — two independent T2 sources in agreement. Cross-domain
confirmation from landscape photography principles (T3).

---

## Style Rule Decisions

**D12 — Desaturation level: between Metro Exodus and S.T.A.L.K.E.R. 2**
More saturated than Metro (which is very gray). Less saturated than TLOU
(which is lush). Concrete reads as cool gray with slight color variation.
Vegetation reads as stressed green, not garden green.
Status: PROVISIONAL — confirmed as a range, not a specific value.
**Gap 03 remains open.** Art director must lock the specific saturation
value before material finalization.
Reference: Metro Exodus (T2), S.T.A.L.K.E.R. 2 (T2)
Confidence: PROVISIONAL

**D13 — Accent color hierarchy**
Primary: cool gray (concrete, 60–70% of visible surface)
Secondary: stressed green (vegetation, 20–30%)
Accent 1: rust orange (metal elements, 10–15%)
Accent 2: efflorescence white (streaks at water exits, 5%)
Reference: Extracted from four reference productions (T2 aggregate)
Confidence: SUPPORTED

---

## Decisions Explicitly Not Made (Open Gaps)

**NOT DECIDED: Exact module count**
Gap 01 from analysis remains open. A market research pass on Fab
best-seller modular kits is required before production scope is locked.
Making this decision without that research risks either under-building
(poor marketplace performance) or over-building (scope overrun).

**NOT DECIDED: Interior visibility content specification**
Gap 02. Requires a UE5 lighting test before interior glimpse content
is specified. Making this decision without the test risks building
interior assets that are not visible or that read incorrectly through
the broken window aperture at camera distance.

**NOT DECIDED: Specific desaturation value**
Gap 03. Art director decision required. See D12.

---

## Undocumented Assumptions (Flagged)

**ASSUMPTION A01: Lumen GI enabled throughout production**
No production confirmation. All PBR calibration is Lumen-dependent.
If Lumen is disabled for performance reasons, all roughness and albedo
values need recalibration.
Risk: HIGH if Lumen is disabled. Seek technical confirmation.

**ASSUMPTION A02: No LOD distance constraint specified**
Module detail level calibrated for hero distance. If LOD distances change
significantly, detail density strategy may need revision.
Risk: LOW — LOD is typically handled post-production. Flag for technical review.

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
