# Game Environment — Reference Engineering Process

**Brief version:** 1.0
**Stage:** Pre-production
**Reference gathered:** organized by Pyramid layer

---

## Layer 1 — Function & Context

### Real-World: Pripyat, Ukraine (Chernobyl Exclusion Zone)
*Answers: "What does 15–20 year abandonment actually look like?"*
Timeline match: Chernobyl accident 1986, most documentation from 2000–2006 = 14–20 years.
Building type match: Soviet-era Khrushchyovka apartment blocks, the exact type specified.
Climate match: Eastern European continental climate.

Key observations extracted:
- Concrete exterior: surface delamination begins at weathering joints, not uniformly
- Paint: fades to chalky, not chips off — specific behavior differs from Western plaster
- Vegetation: grass/weeds at ground level years 1–5, shrubs years 5–10, trees inside buildings by year 15
- Glass: almost entirely broken at year 10+, frames corroding at hinges first
- Debris type: furniture, personal items, structural rubble, NOT post-war/conflict debris
- Metal: significant orange rust on exposed steel, railings fail at weld points first

Hierarchy tier: **Primary** — exact match on timeline, building type, and climate.

### Real-World: Varosha, Cyprus (Abandoned resort district)
*Answers: Layer 1 supplementary — different collapse type, different debris pattern*
Observation: commercial collapse (political abandonment) vs. disaster abandonment.
Difference: no interior looting (zone sealed), so interiors are intact.
Contrast with Pripyat: suggests our post-societal-collapse scenario had looting —
interiors should be stripped, not preserved.
Hierarchy tier: **Primary** (supplementary — different scenario but useful contrast)

### Gameplay Reference: The Last of Us Part I — Pittsburgh/Pittsburgh chapter
*Answers: "What happens during gameplay in this environment?"*
Observation: cover density every 8–12m for third-person cover-based gameplay.
Sight line breaks every 20–30m for stealth sections.
Navigation: rubble creates natural routing — not all paths equally accessible.
Implication: some modules need to produce rubble piles that redirect player flow.
Hierarchy tier: **Secondary** (game, not real-world, but directly analogous gameplay scenario)

---

## Layer 2 — Scale & Proportion

### Soviet Architecture Standard: Khrushchyovka (Khruschev-era apartments)
*Answers: building dimension questions*
From construction documentation:
- Floor-to-floor height: 2.5m (significantly lower than Western residential 2.7m)
- Window module: 1.2m wide × 1.4m tall, 0.6m from floor to sill
- Wall thickness (exterior): 0.38m (brick) or 0.32m (concrete panel)
- Building footprint: 12m deep × varies in length, typically 10m sections
- Street-facing facade module: 3m per residential unit width
Source: Soviet construction standard SNiP II-Л.1-71
Hierarchy tier: **Primary** (engineering documentation)

### Third-Person Camera Reference: UE5 Mannequin
*Answers: "What height becomes obstruction vs. cover?"*
UE5 default mannequin: 180cm tall
Third-person camera: typically 150–180cm above ground at 200–300cm behind character
Cover threshold (crouch-cover): 90–100cm height (waist height)
Full cover threshold: 160–170cm (shoulder height of character)
Line-of-sight obstruction: 190cm+ (taller than character)
Hierarchy tier: **Primary** (UE5 default, confirmed from documentation)

### Modular Grid Analysis
*Answers: "What grid unit covers ≥80% of required combinations?"*
Analysis: Soviet apartment facade module is 3m per unit.
Minimum hallway width for navigation: 1.5m (one mannequin width + 0.5m clearance)
Standard door: 0.9m wide, 2.0m tall
Conclusion: 1m grid unit allows all key dimensions as multiples (3m facade = 3 units, 0.9m door rounds to 1 unit, 2.5m floor height = 2.5 units — acceptable).
Alternatively: 0.5m grid for more precision (3m = 6 units, 1.5m corridor = 3 units, 0.9m door = 1.8 units — rounds to 2).
Decision needed: 0.5m vs 1m grid. See Gap 01 in analysis.
Hierarchy tier: **Primary** (derived from real measurements)

---

## Layer 3 — Production Stage (Silhouette)

### Orthographic Reference: Khrushchyovka Facades
*Answers: "Orthographic front/side reference"*
Key silhouette characteristics:
- Flat roofline (no pitched roof)
- Regular window rhythm, slight variation at stairwell bays
- Minimal facade articulation — recessed windows, no projections
- Ground floor often has taller commercial units (different module height)
- External stairwell access on some building types (creates side-profile interest)
Hierarchy tier: **Primary** (photographic documentation)

### Damage State Silhouettes
*Answers: "Distinct silhouettes for ruin states"*
Three states researched:
1. Intact-damaged: window frames gone, some spalling, vegetation at base
2. Partially collapsed: one corner/section collapsed, internal floors visible
3. Mostly collapsed: standing wall fragments only, rubble field
Observation: partial collapse in real buildings follows floor-by-floor pattern,
not diagonal. Floors pancake or one section separates. Avoid diagonal damage
cuts — they read as artificial.
Hierarchy tier: **Primary** (Pripyat documentation)

---

## Layer 4 — Style Rules

### Style Reference: Metro Exodus (4A Games, 2019)
*Answers: "What is 'grounded realism with slight desaturation'?"*
Desaturation level: moderate. Environmental hues retained (green vegetation
visible as green, concrete as gray). Not color-graded to monochrome.
Detail density: high on hero objects (player-interactable), medium on background.
Surface quality: high roughness values across the board. Almost no specular
except wet surfaces and glass fragments.
Hierarchy tier: **Secondary** (game production, post-apocalyptic, Eastern European — high relevance)

### Style Reference: S.T.A.L.K.E.R. 2 (GSC Game World, 2024)
*Answers: "Eastern European post-apocalyptic visual standard"*
Setting match: Chernobyl Exclusion Zone — exact match.
Desaturation level: lighter than Metro. Slightly more saturated greens.
Style rules extracted:
- Mud and rust are the two dominant accent colors
- Vegetation is always overgrown relative to the structure — nature is winning
- Artificial light sources (inside structures) are warm; exterior is cool
Hierarchy tier: **Secondary** (game, Eastern European post-apocalyptic — high match)

### Style Reference: The Last of Us Part I/II (Naughty Dog)
*Answers: "How does nature reclamation read as 'beautiful ruin' vs 'ugly ruin'?"*
Observation: TLOU uses high-quality vegetation with strong color saturation to
contrast against desaturated architecture. The ruin reads as beautiful because
nature is lush, not struggling.
Applicable: yes — same contrast strategy useful for hero environment reads.
What this style does that ours doesn't: TLOU is more stylized in its lighting.
Their skies are more saturated. Our target is more grounded.
Hierarchy tier: **Secondary** (different geography/climate but same design problem)

### Extracted Style Rules (from all three references):
1. Concrete surfaces: high roughness (0.8–0.95), low metallic (0.0), slight variation in albedo but stay near #808080 range
2. Nature always dominates architecture in color saturation
3. Rust and dirt are the primary accent colors (warm mid-tones against cool concrete gray)
4. Almost no clean specular — only wet surfaces, glass, and standing water
5. Damage follows structural logic — floors pancake, corners separate, walls delaminate not shatter

**What this style NEVER does:**
- Uniform damage across a surface (real damage has hotspots)
- Clean geometric damage cuts (diagonal clean breaks look fake)
- Overly dark/black albedo values on concrete (even darkened concrete stays in mid-gray range)
- Specular on concrete surfaces (concrete in this weathering stage is uniformly matte)
- Perfectly symmetric vegetation placement

---

## Layer 5 — Lighting Context

### UE5 Lumen — Outdoor Day Conditions
*Answers: "What sky conditions define the target look?"*
Target: overcast/partly cloudy Eastern European sky. Soft directional light.
Not golden hour — avoid warm color cast on concrete. Neutral to cool.
Lumen global illumination: enabled. Affects how interior-glimpse surfaces read
(they will be significantly darker than exterior — reference needed for interior values).
Nanite: enabled. No polygon budget concern. Displacement maps viable.
Hierarchy tier: **Primary** (confirmed from project technical spec)

### Albedo Calibration Reference
*Answers: "How do surfaces read under Lumen outdoor overcast conditions?"*
Concrete albedo under overcast Lumen: aim for 0.30–0.45 in linear space.
Vegetation albedo: 0.08–0.15 for leaves (much darker than perceived).
Rust: 0.05–0.15 (very dark in linear space despite appearing orange).
Hierarchy tier: **Primary** (UE5 documentation + Lumen best practices)

---

## Layer 6 — Material & Surface

### Concrete Aging at 15–20 Years (Pripyat documentation)
*Answers: material behavior questions*
Delamination: begins at reinforcement joints and corners. Interior steel rebar
becomes visible at 10–15 year mark in unheated buildings (freeze-thaw cycling).
Carbonation depth: 10–20mm of surface concrete has carbonated (color shift
toward lighter gray/white, more chalky texture).
Efflorescence: white calcium deposits at water egress points (around windows,
at floor level exterior, at cracks).
Moss/lichen: starts at permanently shaded areas, spreads upward from ground level.
By year 15: base 0–1m is near-100% moss/lichen coverage in shaded areas.
Hierarchy tier: **Primary** (photographic evidence from matching timeline)

### Window Glass Behavior
Documented observation from Pripyat:
- Float glass (standard Soviet-era): breaks into large shards, some remain in frame corners
- By year 15: frames contain only corner fragments, rest fallen inward
- Glass on floors: mostly pulverized by weather, some larger pieces remain
- Frame condition: wood frames rotted at joints, metal frames corroded at hinges
Hierarchy tier: **Primary**

---

## Layer 7 — Hero Detail (Pre-gathered for mid-production)

### Macro Photography: Concrete Surface at 15–20 Year Aging
*For hero texture reference — defer use to mid-production*
Sources: Pripyat photography, Chernobyl documentary footage (close-ups)
Key details to capture in texture:
- Carbonation layer (pale, chalky top 5–10mm)
- Sub-surface (darker, still-solid concrete beneath)
- Crack networks: follows rebar grid pattern
- Aggregate exposure at worn areas: gravel becomes visible
- Efflorescence deposits: streaked, white, semi-transparent in thin layers

### Vegetation Detail
Specific plant species at Chernobyl year 15–20:
- Birch saplings (primary tree reclamation agent)
- Wormwood/Artemisia (common ground cover, gray-green, distinctive silhouette)
- Common wall moss (Tortula muralis — specific appearance worth referencing)
- Pin cherry / bird cherry (understory level, pinkish bark detail)

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
# Game Environment — Analysis & Gap Audit

---

## Extracted Rules

### Modular Grid Specification
Grid unit: **0.5m**
Rationale: allows 3m facade module (6 units), 1.5m minimum corridor (3 units),
0.9m door (2 units with 0.05m wall reveal — acceptable), 2.5m floor height
(5 units exact). All key dimensions hit integer multiples cleanly.
Every module must snap to this grid. No exceptions without documented justification.

Key module dimensions derived from grid + real-world data:
- Facade panel: 3.0m × 2.5m (one floor, one residential unit width)
- Window opening: 1.0m × 1.4m (rounded from real 1.2m to fit 0.5m grid)
- Door opening: 1.0m × 2.0m (rounded from real 0.9m)
- Floor-to-floor: 2.5m (exact from Soviet standard)
- Corridor minimum: 1.5m clear width
- Street minimum (gameplay): 8.0m (two lanes + rubble margin)

### Style Rules (Written Parameters)

**Concrete:**
- Albedo: 0.30–0.45 linear space. Base hue: cool gray (#707878 approximate, slight blue shift)
- Roughness: 0.85–0.95. No clean specular on concrete.
- Damage hotspots at corners, reinforcement joints, and window reveals — NOT uniform
- Carbonation layer (top 10mm): lighter, chalkier, roughness 0.90–0.95

**Vegetation:**
- Always more saturated than architecture — contrast is the key rule
- Ground level (0–1m): 80–100% coverage in shaded areas at this timeline
- Color: desaturated greens (not lush garden green — stressed concrete-grown green)
- Species-specific for hero areas: birch, wormwood, Tortula moss

**Damage logic:**
- Floors pancake (horizontal collapse) — NOT diagonal cuts
- Corners separate from facade (thermal cycling + rebar failure pattern)
- Wall delamination is surface-level — cracks expose sub-surface, not void
- Never perfectly uniform damage — real damage has a cause and a hotspot

**Color architecture:**
- Base: cool gray concrete (dominant)
- Secondary: desaturated green (vegetation — also dominant, competing for space)
- Accent 1: rust orange (metal elements — 10–15% of surface area)
- Accent 2: efflorescence white (streaks at water exits — 5% of surface area)
- Accent 3: moss dark green (shaded corners — grades into vegetation color)

**What this environment NEVER has:**
- Diagonal clean damage cuts
- Uniform aging across a surface (always varied)
- Concrete specular
- Black concrete (darkest albedo stays above 0.15 linear)
- Perfectly symmetric vegetation placement
- Modern construction materials (no aluminum cladding, glass curtain wall)

### PBR Channel Targets

| Surface | Albedo (linear) | Roughness | Metallic | Notes |
|---|---|---|---|---|
| Aged concrete | 0.30–0.45 | 0.85–0.95 | 0.0 | Cool gray, slight variation |
| Concrete carbonation | 0.40–0.50 | 0.90–0.95 | 0.0 | Lighter, chalkier |
| Rust (iron) | 0.04–0.12 | 0.75–0.90 | 0.0–0.3 | Dark despite appearance |
| Window frame (corroded) | 0.05–0.15 | 0.70–0.85 | 0.2–0.6 | Mixed metal/oxide |
| Moss (Tortula) | 0.05–0.10 | 0.90–1.0 | 0.0 | Very dark in linear space |
| Birch bark | 0.35–0.50 | 0.80–0.90 | 0.0 | Pale, high roughness |
| Dry vegetation | 0.08–0.15 | 0.85–0.95 | 0.0 | Dark in linear space |
| Standing water | 0.02–0.05 | 0.05–0.15 | 0.0 | Low roughness — specular allowed |

---

## Gap Audit

### Resolved Gaps (closed before production start)

**RESOLVED: Modular grid size** — 0.5m grid confirmed, derived from real dimensions.

**RESOLVED: Soviet building dimensions** — Floor height 2.5m, window module confirmed
from construction documentation.

### Remaining Gaps

**GAP 01: Exact module set count not defined**
We know the grid. We have not defined how many unique modules to build.
Too few = obvious tiling. Too many = production scope problem.
Industry reference needed: how many modules do comparable Fab marketplace
modular kits contain?
*Resolution:* Research Fab best-seller modular kits and count module variety.
*Blocking:* Production scope planning

**GAP 02: Interior visibility spec not resolved**
Players will see interiors through broken windows at some distance.
Interior albedo values under Lumen indirect light not confirmed.
Interior glimpse content (furniture, debris) not specified.
*Resolution:* Test in UE5 with Lumen enabled at target camera distance.
*Not blocking pre-production but blocking mid-production*

**GAP 03: Desaturation grade not locked**
Style rules say "less saturated than TLOU, more than Metro Exodus."
This range is too wide to prevent art direction disputes.
*Resolution:* Request project art director decision. Provide Metro/TLOU
screenshots with annotated saturation values as decision aid.
*Blocking: material finalization*

---

## Reference Hierarchy Summary

| Decision | Tier | Confidence |
|---|---|---|
| 0.5m grid | Primary (derived from real measurements) | High |
| Floor height 2.5m | Primary (construction documentation) | High |
| Concrete PBR values | Primary (UE5 documentation) | High |
| Damage logic (floors pancake) | Primary (Pripyat documentation) | High |
| Style desaturation level | Secondary (game productions) | Medium — needs lock |
| Module count | Tertiary (industry benchmark) | Low — needs research |

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
