# 3D Art — Reference Sources

Best sources for Reference Engineering in 3D art, organized by Pyramid layer.

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Function & Context

**YouTube** — FREE
Best source for in-use and behavior reference. Search the function, not
the appearance. "How [object] works", "[material] under stress", "how
[object] is manufactured". The Slow Mo Guys for material behavior at
extreme frame rates. How It's Made for construction and assembly logic.
Smarter Every Day for mechanical function.

**Wikimedia Commons** — FREE
Public domain photography organized by subject. Search by object type
for real-world functional photography. Strong for historical objects,
everyday props, architecture. CC licensed — use freely as reference.

**Getty Images / Shutterstock preview** — FREE to use as reference
Preview images are sufficient resolution for reference extraction.
Search behavior and use states, not just appearance. "Person using [object]"
returns in-use reference that product photography doesn't.

**Google Patents / Espacenet** — FREE
Exploded diagrams and technical specifications for manufactured objects.
Excellent for understanding construction logic (Layer 6) and function
(Layer 1) simultaneously. Search by product name or category.

---

## Layer 2 — Scale & Proportion

**Dimensions.com** — FREE
The most useful single reference source for human-scale proportion.
Every entry includes exact metric/imperial dimensions with a human figure
for comparison. Architecture, furniture, vehicles, everyday objects.
Bookmark and use before every prop brief.

**The-Blueprints.com** — FREE / PAID (HD downloads)
Orthographic line drawings for vehicles, aircraft, weapons, ships,
and machinery. Free preview resolution is usable. HD downloads require
subscription. Essential for Layer 2 on any mechanical or vehicle asset.

**Sketchup 3D Warehouse** — FREE
User-uploaded models often include real-world dimensions in the model
metadata or description. Useful for quick scale verification on
architecture and furniture. Verify dimensions independently — not all
submissions are accurate.

**UE5 Mannequin** — FREE (with UE5)
The 180cm UE5 default mannequin is the scale anchor for any UE5 real-time
asset. Place it in scene before finalizing any asset's proportions.
Use the Unreal Engine marketplace's free asset packs for additional
scale reference (vehicles, furniture, architecture).

---

## Layer 3 — Stage Reference

### Silhouette / Orthographic

**ArtStation** — FREE / PAID (Pro)
Filter by "2D" or "concept art" for turnaround sheets and orthographic
design references. Search by genre (sci-fi, fantasy, realistic) and
asset type. Strong for character turnarounds and prop orthographics
from game productions.

**The-Blueprints.com** — FREE / PAID
See Layer 2. Also the best source for silhouette-stage reference on
vehicles and machinery.

**Pinterest** — FREE
Use specifically for silhouette shape collection at blockout stage.
Set up boards by asset type and style. Useful for rapid silhouette
variety research. Not suitable for style rule extraction — too low
quality and too uncurated for Layer 4 work.

### Stage-Appropriate Search Modifiers

Add these to any search to find stage-appropriate reference:
- Silhouette stage: `[subject] orthographic`, `[subject] side view`, `[subject] turnaround`
- Blockout stage: `[subject] blockout`, `[subject] grey box`, `[subject] base mesh`
- Texture stage: `[material] surface close up`, `[material] macro photography`
- Hero detail: `[material] 4K texture`, `[subject] detail photography`

---

## Layer 4 — Governing Rules

**GDC Vault** — FREE / PAID
Game Developers Conference talks. Search by game title or "art direction"
or "visual development" or "style guide". Many studios present their
visual style development process explicitly, including the rules they
extracted. Free tier has significant content. Paid tier has everything.
Start here for any game-adjacent style research.

**The Art of [Game Title] books** — PAID
Published art books from major game productions contain the style
documentation that shipped with the game. Naughty Dog, Santa Monica
Studio, Guerrilla Games, CD Projekt Red, and others have published these.
Primary tier for understanding the rules of those specific productions.

**ArtStation Challenges** — FREE
Competitive art challenges with style constraints reveal how many
different artists interpret the same style brief. The variance shows
which style elements are genuinely rule-governed (low variance = real rule)
and which are vague (high variance = not an extractable rule).

**Developer Art Blogs / Breakdown Posts** — FREE
Many studios publish technical art breakdowns on their websites or on
ArtStation. Riot Games, Bungie, Epic Games, Insomniac, and others have
published detailed style documentation. Search "[studio name] art
breakdown" or "[game title] technical art".

---

## Layer 5 — Lighting Context

**Polyhaven (HDRI Haven)** — FREE (CC0)
Real-world HDRI environments at multiple resolutions. Every HDRI is
labeled by lighting conditions (studio, outdoor overcast, outdoor sunny,
golden hour, indoor, etc.). Use to understand how materials read under
specific conditions. Also the standard source for free production HDRIs.

**Quixel Megascans** — FREE with UE5
Photogrammetry-scanned real-world surfaces. The preview images show
real material response under real-world lighting. Even if not using the
assets, the previews are primary-tier reference for material calibration
under the conditions they were photographed in.

**UE5 Content Examples** — FREE (with UE5)
Epic's official example scenes show material calibration under real
Lumen conditions. Use these as calibration reference for UE5-target
assets — they show what is achievable in the delivery pipeline.

**ShotDeck** — PAID
Searchable film still database with filtering by lighting mood, color
palette, and scene conditions. Strong for Layer 5 when the target
is a specific cinematographic look. Subscription required.

---

## Layer 6 — Material & Surface

**Quixel Megascans** — FREE with UE5
The highest-quality source of real-world material documentation in the
industry. Every scan includes reference images showing the material in
context, at various distances, and in multiple conditions. PBR values
are documented. Use as both reference and (optionally) as production assets.

**Polyhaven Textures** — FREE (CC0)
CC0 PBR materials with full channel documentation. The material descriptions
note the real-world equivalent and the conditions under which the material
was photographed. Good for understanding the relationship between real
material properties and PBR channel values.

**YouTube: "How It's Made" / Manufacturing Videos** — FREE
Shows construction process, material behavior under manufacturing stress,
assembly logic and joint types. Layer 6 primary reference for understanding
how things are built and how they fail.

**Matweb / MatBase** — FREE
Material science databases. Physical properties for manufactured materials:
density, hardness, thermal behavior, surface properties. Technical Layer 6
reference for understanding why materials behave the way they do.

---

## Layer 7 — Precision Detail

**Polyhaven** — FREE (CC0)
High-resolution macro surface photography included with many material
scans. Free for commercial use.

**Quixel Megascans** — FREE with UE5
Close-up detail reference at photogrammetry quality. The best source
for understanding how real surfaces look at proximity. Surface variation,
micro-detail frequency, pore distribution, wear patterns at proximity.

**Unsplash / Pexels** — FREE (CC0)
Search `[material] macro` or `[surface type] texture close up` for
high-resolution photography. Less curated than Megascans but much larger
catalog. Good supplementary source for unusual materials.

**Smithsonian Open Access / British Museum Collection** — FREE
Museum collections with high-resolution photography of historical
artifacts. Exceptional for aged materials, patina, historical wear
patterns. CC0 or CC-BY licensed. Search by material type or object category.

---

## Pipeline-Specific Sources

### Unreal Engine 5
- UE5 Documentation (rendering, materials, Lumen) — primary tier
- Fab Marketplace (formerly Quixel Bridge + UE Marketplace) — reference quality assets
- Unreal Online Learning — FREE course content including art direction

### Blender
- Blender Studio Open Movies (Sprite Fright, Charge, etc.) — style reference and breakdown
- Blender Artists Forum breakdowns — community technical art documentation

### ZBrush (Sculpting)
- Michael Pavlovich's anatomy series — FREE YouTube, primary anatomy reference
- Scott Eaton's anatomy courses — PAID, best-in-class for character anatomy reference

### Substance (Texturing)
- Adobe Substance 3D Assets — reference material presets with documented values
- ArtStation Learning Substance breakdowns — style-specific texturing workflows

---

## Reference Organization Tools

**Kanvaz** — FREE (MIT)
Offline infinite canvas reference board for Windows. Built specifically
for VFX/3D pre-production workflows. No subscription, no internet required.
Download: [github.com/p4inz-code/kanvaz](https://github.com/p4inz-code/kanvaz)

**PureRef** — FREE
The industry-standard reference board tool. Lightweight, fast, supports
large boards. Available on Windows, Mac, Linux. Cross-reference with
Kanvaz for workflow differences.

**AI Skill Pack** — FREE (MIT)
3d-ref-skills v3.1.0 implements the full Reference Engineering methodology
for 3D pre-production as AI agent skills. Works with Claude Code, Cursor,
Codex, Gemini. 9 skills covering the complete workflow.
Download: [github.com/p4inz-code/3d-ref-skills](https://github.com/p4inz-code/3d-ref-skills)

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
