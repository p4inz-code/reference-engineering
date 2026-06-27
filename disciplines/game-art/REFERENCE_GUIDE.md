# Game Art — Reference Engineering Guide

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## The Gameplay Context Principle

All game art reference must be gathered and evaluated against the gameplay
context — the actual camera distance, lighting conditions, and competing
visual elements of the game — not against ArtStation render standards.

Before gathering any other reference, document the gameplay context:

```
GAMEPLAY CONTEXT DOCUMENT
Camera distance to asset: [close / mid / far / variable]
Camera angle: [FPS / TPS / isometric / top-down / side-scrolling]
Competing visual elements: [what else is on screen when this asset is visible?]
Primary lighting condition: [outdoor sun / indoor dramatic / dynamic / mobile unlit]
Target frame rate: [60fps / 30fps]
Primary display: [console TV / PC monitor / mobile screen]
```

This document is filled out before the first reference image is collected.
Every reference image gathered after this point is evaluated against it.

---

## Layer 1 — Function & Context

### Gameplay Function Reference

**Readability requirement:** Can the player correctly identify this asset
at gameplay camera distance under dynamic lighting conditions? Readability
is a Layer 1 requirement, not a Layer 7 nicety. An asset that reads
incorrectly in gameplay has failed regardless of its technical quality.

Readability requirements by asset type:
- **Player character:** Must be identifiable at all camera distances and
  in all lighting conditions. Cannot be confused with enemies.
- **Enemy characters:** Must be readable as enemy type (melee vs. ranged vs. boss)
  at the distance where the player needs to respond to them.
- **Interactive props:** Must read as "interactable" — visually distinct
  from environmental dressing. Glowing, different material, silhouette cue.
- **Environmental dressing:** Must NOT read as interactive or important.
  Should recede visually relative to interactive elements.
- **Cover objects:** Must read as "cover" at the distance where the player
  makes the decision to take cover behind them.

**Gameplay camera reference:** Capture screenshots from comparable games
at the exact camera distance and angle that your game uses. This is the
primary visual reference for what "looks correct" in your game — not
ArtStation renders.

### What to Find

**In-game screenshots at target camera distance:** Not promotional screenshots
(close-up, hero-lit, cinematic angle). Actual gameplay screenshots from
the closest comparable game, at the camera settings your game uses.

**Comparable game art style documentation:** GDC talks from the art team
of the reference game, art of books, breakdown posts from the artists.
These provide the written rules, not just the visual output.

---

## Layer 2 — Scale & Proportion (Technical Budget)

### Technical Reference by Asset Class

Different game art asset classes have different budget standards. These
are not absolute — they vary by platform, engine, and game type — but
they provide the starting reference point before the project-specific
budget is defined.

**Characters (real-time, hero, console/PC):**
- Polygon count: 15,000–80,000 triangles (hero), 5,000–15,000 (secondary)
- Texture: 2048×2048 or 4096×4096 (hero), 1024×1024 (secondary)
- Texel density: 10–15 pixels/cm at primary LOD (hero camera distance)

**Characters (mobile):**
- Polygon count: 1,500–5,000 triangles
- Texture: 512×512 or 1024×1024
- Texel density: 5–8 pixels/cm

**Props (real-time, hero, console/PC):**
- Polygon count: 1,000–10,000 triangles (hero prop), 200–2,000 (background)
- Texture: 512×512–2048×2048 depending on camera distance
- Texel density: 10 pixels/cm at closest camera distance

**Environment (modular, real-time):**
- Polygon count: 500–5,000 per module (highly variable)
- Texture: tiling textures at 2048×2048, unique decals at 512×512
- Texel density: consistent across the set at the primary viewing distance

### Scale Relative to Player Character

Every prop, environment element, and enemy must be scaled against the
player character as the primary anchor. Collect scale reference from
comparable games: screenshots with the player character next to reference
objects (doors, crates, vehicles) establish the correct scale relationship.

---

## Layer 3 — Stage Reference

### Game Art Production Stages

| Stage | What You're Building | Reference Needed |
|---|---|---|
| Concept | Silhouette, color, tone | Style reference, silhouette studies |
| Blockout | Primary mass, polygon budget | Comparable game blockout, scale reference |
| High-poly (if used) | Detail sculpt | Real-world detail reference |
| Retopo/low-poly | Efficient topology | LOD reference, deformation reference (characters) |
| UV | Layout efficiency | Texel density standard, tiling vs. unique areas |
| Texture/surface | In-engine material | In-engine render reference at gameplay distance |
| In-engine validation | Final appearance in context | Gameplay screenshot at target conditions |
| LOD chain | Reduced complexity | Comparable LOD chains from similar assets |

### In-Engine Validation — The Most Skipped Stage

The final stage before delivery must be in-engine validation: the asset
placed in the actual game scene, under actual game lighting, at the actual
camera distance, with the actual competing visual elements present.

Most game art problems are discovered here — if they are discovered at all.
Reference Engineering requires that in-engine validation has its own reference:
comparable assets in comparable games, under comparable conditions.

---

## Layer 4 — Governing Rules

### Style Rules for Games

Game art style rules must address gameplay readability explicitly,
not just aesthetics. The rules format:

```
GAME: [title]
ART STYLE: [name/description]
DATE ANALYZED: [date]

SILHOUETTE RULES:
- Player character silhouette must read at [distance] in all lighting
- Enemy type silhouettes are differentiated by [specific element]
- Interactive elements are identified by [specific rule]

SURFACE QUALITY RULES:
- Primary materials: roughness range [X–Y], albedo range [X–Y]
- Wear and aging: [specific rules]
- Specularity: [rules — important for readability at distance]

DETAIL DENSITY RULES:
- Hero elements (close camera): [density rule]
- Mid-range elements: [density rule]
- Background dressing: [density rule]

WHAT THIS STYLE NEVER DOES:
- [Negative constraint 1]
- [Negative constraint 2]

COLOR ARCHITECTURE RULES:
- Player: [color rule that differentiates from enemies]
- Enemies: [color rule]
- Interactive: [color rule]
- Environment: [color rule]
```

### Color Architecture as Readability Tool

Color is used in game art to communicate gameplay information, not just
aesthetics. Reference the color architecture of comparable games:

- **Player character:** Usually highest saturation, or specific hue
  distinct from the environment
- **Enemies:** Consistent signaling color (red is common, but game-specific)
- **Interactive objects:** Frequently use warm colors (gold, orange) against
  cooler environments to create visual contrast
- **Background dressing:** Frequently desaturated relative to foreground elements

Extract these rules from comparable games before designing the color system.

---

## Layer 5 — Lighting Context (In-Engine)

### In-Engine Validation Reference

The primary Layer 5 reference for game art is in-engine test renders
at the target lighting conditions. Not Marmoset. Not Blender Cycles.
The actual game engine with the actual scene lighting.

Gather reference from:
- The closest comparable game (screenshots at similar lighting conditions)
- The engine's own showcase content (shows what is achievable)
- Any existing assets in your project (establishes the visual standard)

### Mobile vs. Console/PC Lighting

Mobile games often use simpler lighting models — frequently unlit or
with baked lighting only. Assets that look correct under Lumen or HDRP
look incorrect under a simpler mobile lighting model.

If the game targets mobile:
- Gather reference from mobile games with comparable visual targets
- Test assets under the mobile renderer, not the full-quality renderer
- Baked lighting reference is different from dynamic lighting reference

---

## Layer 6 — Behavior & Construction

### LOD Chain Reference

Every asset in a game typically needs multiple levels of detail. The LOD
chain must be planned from the start — not added as an afterthought.

LOD reference: find comparable assets in comparable games and examine
their LOD transitions. What is the polygon count at each LOD? At what
distance does each LOD transition occur? What detail is removed first?

**LOD transition principles:**
- Silhouette-preserving simplification first: reduce internal geometry
  before reducing outline geometry
- Remove detail that doesn't read at LOD transition distance before reducing
  fundamental form
- LOD0 (hero): full detail. LOD1: 50–70% of LOD0. LOD2: 20–40% of LOD0.
  LOD3+: <10% of LOD0 (billboard or impostor acceptable)

### Character Deformation Reference

For animated characters, topology decisions must account for deformation:
- Gather reference for the specific joints that will deform for this character
  (shoulder, elbow, knee, spine, wrist)
- Reference from comparable rigged characters in the same engine
- Test topology at the range of deformation before committing to high-poly

---

## Layer 7 — Precision Detail

In game art, Layer 7 is context-dependent:

**For cutscene / marketing quality:** Standard hero detail — micro-texture,
pore detail, wear patterns. Same as general 3D art Layer 7.

**For gameplay camera distance:** Layer 7 is the in-engine detail that reads
at the closest camera approach the player will make. This is usually much
less detail than portfolio render quality.

**For background assets:** Layer 7 may not exist — background assets rarely
need hero detail and investing in it is wasted production time.

**The Layer 7 budget rule:** Before any hero detail is added, confirm the
camera will ever be close enough for it to read. If the answer is "only
in cutscenes," budget hero detail for cutscene quality separately from
gameplay quality.

---

## The Game Art Reference Brief

```
PROJECT: [asset name]
TYPE: [character / environment / prop / VFX / UI]
GAME STYLE: [style description]
PLATFORM: [console/PC / mobile / cross-platform]
DATE: [brief version date]

GAMEPLAY CONTEXT
Camera distance: [close / mid / far / variable]
Camera angle: [FPS / TPS / isometric / side]
Readability requirement: [what must this asset communicate at gameplay distance?]
Competing visual elements: [what else is on screen?]

LAYER 1 — GAMEPLAY FUNCTION
Asset's gameplay function:
Readability requirement (specific):
Comparable game screenshots gathered at target camera distance: [ ]

LAYER 2 — TECHNICAL BUDGET
Triangle budget (LOD0):
Texture resolution:
Texel density target:
LOD chain: LOD0  LOD1  LOD2  LOD3

LAYER 4 — GOVERNING RULES
Style rules (written, not described):
Color architecture role (player/enemy/interactive/dressing):
What this asset NEVER looks like:

LAYER 5 — IN-ENGINE CONTEXT
Target renderer:
Scene lighting conditions:
In-engine test render completed: [ ]

LAYER 6 — CONSTRUCTION
LOD chain reference gathered: [ ]
Deformation reference gathered (if character): [ ]

LAYER 7 — PRECISION DETAIL
Cutscene/marketing quality required: [ ]
Gameplay camera closest approach distance:
Hero detail zones (where camera will approach):

GAPS:
Critical:
High:

BRIEF VERSION: [v1.0 / v2.0 / vFinal]
```

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
