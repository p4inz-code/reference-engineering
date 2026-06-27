# Game Art — Reference Sources

Best sources for Reference Engineering in game art, by Pyramid layer.

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Gameplay Function and Readability

**The target game itself** — PRIMARY METHOD
Play the game you are making art for. Capture gameplay screenshots at the
actual camera distance and angle. These screenshots are the primary Layer 1
reference — not promotional material, not close-up renders. The actual
in-game view at the conditions the art will be seen in.

**Comparable shipped game screenshots** — FREE
Steam, PSN, Xbox screenshots. Filter for gameplay screenshots (not promotional).
Reddit game communities frequently have gameplay screenshot threads.
Look for screenshots taken in the same lighting conditions and camera
angle as your target game.

**Steam Deck / portable screenshots** — FREE
Steam Deck screenshots at portable resolution show game art under
compressed display conditions — useful reference for mobile and portable targets.

---

## Layer 2 — Technical Budget

**Engine documentation (UE5, Unity)** — FREE
Official engine documentation for asset specifications, LOD setup, and
texel density tools. Primary-tier for engine-specific budget implementation.

**Fab / Unity Asset Store (top-selling packs)** — FREE to inspect
Top-selling environment and character packs on Fab (formerly UE Marketplace)
show what polygon counts and texture resolutions the market accepts.
Their store page descriptions frequently list triangle counts and texture sizes.

**Game Reverse Engineering Community** — FREE
Communities that extract and analyze game assets (NexusMods, Deviantart
game rip sections, GameBanana). Useful for understanding the actual
polygon counts and texture sizes of shipped game assets. Use for
reference research only — do not distribute extracted assets.

**UE5 Content Examples** — FREE (with UE5)
Epic's official sample projects include assets with documented specifications.
Primary-tier for UE5 budget and texel density standards.

---

## Layer 3 — Stage Reference

**ArtStation** — FREE / PAID (Pro)
The primary portfolio platform for game artists. Filter by "3D", by game
engine, and by art type. Use for concept and blockout stage reference.
Caution: ArtStation reference is optimized for portfolio renders, not
for gameplay context. Use it for style direction, not for gameplay calibration.

**80.lv** — FREE
Game development technical art resource. Articles and breakdowns from
working game artists. Strong for understanding production pipeline
and stage-appropriate workflows.

**Realtimecolors / Game Art Institute** — FREE / PAID
Game art tutorial resources. Useful for understanding production-standard
workflows at each stage.

**Polycount Forum** — FREE
polycount.com/forum — the longest-running game art community forum.
Critique threads show assets at every production stage with production
context. WIP threads are particularly useful for understanding how
professional game artists approach each stage.

---

## Layer 4 — Governing Rules

**GDC: Art Direction and Visual Development talks** — FREE / PAID
GDC Vault talks from art directors and lead artists of major games.
The most valuable Layer 4 sources — they explain the specific rules that
governed visual decisions for a shipped game. Search by game title.

**"The Art of [Game]" books** — PAID
Art books from major game productions include concept art, style guides,
and design intention documentation. Primary Layer 4 reference for
understanding the rules of a specific game's visual style.

**Developer Art Blogs:**
- Riot Games Technology Blog — FREE
- Naughty Dog graphics programming blogs — FREE
- Insomniac Games tech blog — FREE
- CD Projekt Red dev insights — FREE

These include specific technical and artistic decisions with rationale —
the written rules behind the visual output.

**Game Asset Reviews (NPC / Environment / Character)** — FREE
YouTube channels that analyze game art quality (Corridor Crew for film VFX,
equivalent channels for game art). Note: review these critically — not
all analysis is accurate. Cross-reference against developer statements.

---

## Layer 5 — Lighting Context

**UE5 / Unity Scene Lighting Documentation** — FREE
Primary-tier reference for how the engine renders materials under various
lighting configurations. Lumen documentation, HDRP documentation, URP
documentation — match to your delivery renderer.

**Engine Showcase Projects** — FREE
Epic and Unity distribute showcase projects that demonstrate high-quality
art in the actual engine. Valley of the Ancient (UE5), Enemies demo (UE5),
Book of the Dead (Unity). These show what is achievable in the delivery renderer.

**Mobile Game Screenshots** — FREE
For mobile targets: screenshots from top-grossing mobile games in your genre.
App Store and Google Play screenshots are often closer to real gameplay than
promotional material on other platforms.

---

## Layer 6 — LOD and Construction

**Houdini LOD Tools Documentation** — FREE
sidefx.com/docs — LOD reduction workflows in Houdini. Primary-tier for
understanding what automatic LOD tools preserve and what they destroy.

**UE5 Nanite Documentation** — FREE
docs.unrealengine.com — Nanite removes traditional LOD requirements for
supported geometry. Primary-tier reference for UE5 LOD strategy.

**Simplygon / Polygon Cruncher Documentation** — FREE / PAID
Automatic LOD generation tools. Documentation explains how automatic
reduction works — useful for planning topology that reduces cleanly.

**Game Character Rigging Resources (GDC, ArtStation Learning)** — FREE / PAID
Character deformation reference. Multiple published GDC talks address
topology for deformation in specific game engines.

---

## Layer 7 — Precision Detail

**Quixel Megascans** — FREE with UE5
Photogrammetry-scanned real-world surfaces. The highest quality surface
reference available. Use for understanding real micro-texture at hero
detail level, even if using stylized art — the physical behavior is
the same.

**ArtStation Marketplace** — FREE / PAID
High-resolution reference packs, alpha brushes, and texture libraries.
Useful for hero detail reference on specific material types.

**Smithsonian Open Access** — FREE
High-resolution photography of historical artifacts. Exceptional for
aged materials, patina, and historical wear. CC licensed.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
