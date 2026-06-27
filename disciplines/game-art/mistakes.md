# Game Art — Reference Engineering Mistakes

Seven failure modes specific to game art reference practice.

---

## MISTAKE 01 — Building for Portfolio, Not Gameplay

> *"It looks incredible in Marmoset. Why does it look flat in-game?"*

**Symptom:** Asset looks exceptional in portfolio renders and mediocre
in gameplay. The art direction was correct. The surface quality was correct.
In the game engine, under game lighting, at game camera distance, it reads
as flat and generic.

**Cause:** Reference was gathered from ArtStation portfolio renders — close-up,
hero-lit, high-quality renders — rather than from in-engine gameplay screenshots
at the actual camera distance and lighting conditions. Layer 5 (Lighting Context)
reference was calibrated to the wrong production environment.

**Fix:** Before any asset development begins, gather Layer 1 reference from
in-game screenshots of comparable games at the actual camera distance and
lighting conditions. Evaluate all visual decisions against this reference,
not against portfolio renders. The question is never "does this look good
in Marmoset?" — it is "does this look correct at gameplay distance in-engine?"

**Production cost:** Material and texture revision pass calibrated to
in-engine conditions. If the surface quality is fundamentally wrong for
the rendering pipeline, re-texturing. Time lost: 1–3 days per asset.

---

## MISTAKE 02 — Readability Failure

> *"Players can't tell where the enemy is."*

**Symptom:** Players fail to distinguish enemies from environment, or
interactive objects from decorative ones. Gameplay reviews cite confusion.
The art is technically correct — readability was never designed for.

**Cause:** Layer 1 (Function & Context) gameplay readability reference
was absent. The asset was designed to look good in the art style without
explicit reference to how it needs to read at gameplay distance among
competing visual elements.

**Fix:** Before designing any asset's visual appearance, document its
readability requirement: what must the player correctly identify at gameplay
distance? Gather reference from comparable games showing how they solve
the same readability problem. Apply the readability solution as a Layer 4
governing rule, not as an afterthought.

**Production cost:** Redesign of visual language for the failing asset class.
If multiple assets share the readability problem (all enemies vs. environment),
a full visual language revision. Level design compensation for art readability
failures is always more expensive than fixing the art.

---

## MISTAKE 03 — LOD Chain as Afterthought

> *"The LOD transitions look terrible. Players can see the assets pop."*

**Symptom:** Visible LOD transitions in gameplay — assets that visibly
change shape, lose significant detail, or change silhouette at LOD distance.
Players notice. Art director notices. Fix is expensive.

**Cause:** Layer 2 (Scale & Proportion) LOD chain reference was absent.
LOD was not planned from the start of asset production. The LOD chain
was created by decimating the completed high-detail asset, producing
transitions that don't preserve silhouette and remove the wrong details.

**Fix:** Before building the LOD0 (hero) asset, plan the full LOD chain.
Reference comparable game assets at each LOD distance: what detail is
retained, what is removed, what is the silhouette at each LOD? Build the
LOD0 with the LOD chain in mind — topology and detail placement should
consider what will survive to LOD1 and LOD2.

**Production cost:** LOD chain rebuild for the affected assets. If the
LOD0 topology was not built for LOD reduction, the LOD chain must be
rebuilt from scratch rather than refined. 0.5–2 days per asset.

---

## MISTAKE 04 — Texel Density Inconsistency

> *"Some props look sharp and some look blurry and we can't explain why."*

**Symptom:** Visual inconsistency in the game scene — some objects read
sharply and others look soft at the same camera distance. The textures
are technically correct resolutions. The inconsistency is texel density.

**Cause:** Layer 2 (Scale & Proportion) texel density standard was not
established as a governing rule before production began. Different artists
applied different texel densities to different assets. The variation is
visible in-game.

**Fix:** Before any texturing begins, establish the texel density standard
for each asset class at the primary camera distance. Document it in pixels
per centimeter (or per world unit). All assets must match the standard.
Enforce it with in-engine texel density visualization during production.

**Production cost:** Re-UV mapping and re-texturing of assets that don't
meet the standard. If the standard was never defined, establishing it
retroactively requires auditing every asset.

---

## MISTAKE 05 — Color Architecture Without Function

> *"The player got confused about which faction they belong to."*

**Symptom:** Players can't distinguish between friendly and enemy factions,
or between player-owned and enemy-owned territory. The color palette is
beautiful but doesn't communicate gameplay information.

**Cause:** Layer 4 (Governing Rules) color architecture was designed for
aesthetics rather than extracted from comparable games' functional color
systems. Color is a communication channel in games — every color decision
should answer: what does this color tell the player?

**Fix:** Before designing the color system, gather reference for how
comparable games use color to communicate gameplay information. Extract
the rules: player faction color, enemy faction color, interactive element
indicator, terrain ownership signal. Apply these as functional rules,
then tune aesthetically within the rules.

**Production cost:** Color redesign for faction-identifying elements.
If the color confusion is in core UI, may affect HUD, map, and 3D art
simultaneously.

---

## MISTAKE 06 — Style Rules Applied by Feel, Not Specification

> *"The environment art and the character art look like they're from different games."*

**Symptom:** Art consistency problems between asset types produced by
different artists or at different times. Characters and environments share
the game but don't share a cohesive visual style. The problem is diagnosed
as "style" but the underlying cause is absent written style rules.

**Cause:** Layer 4 (Governing Rules) style rules were communicated as
visual inspiration (mood boards, reference images) rather than as written
specification. Different artists interpreted the inspiration differently.
Without written rules, there is no shared standard to calibrate against.

**Fix:** Extract style rules as written parameters before production begins.
The rules must be specific enough that two different artists produce
consistent results by following them — not by looking at the same mood board
but by applying the same bevel width, the same roughness range, the same
detail density distribution. If two artists would interpret the rule
differently, the rule is not specific enough.

**Production cost:** Art consistency review and revision pass. For large
art sets: significant rework to bring outliers into the defined style.
Prevention cost: one additional day of style rule documentation at the
start of production.

---

## MISTAKE 07 — Mobile Lighting Mismatch

> *"It looks completely different on mobile."*

**Symptom:** Art produced and reviewed on PC or console looks correct,
and looks significantly different on the mobile build. Usually: too dark,
wrong contrast, material response is completely different.

**Cause:** Layer 5 (Lighting Context) reference was calibrated to the
development platform's rendering pipeline. Mobile often uses baked lighting,
simpler shadow models, and different gamma handling than PC. Art calibrated
to PC dynamic lighting does not translate to mobile baked lighting.

**Fix:** If targeting mobile, all art review must be done in the mobile
build, not in the PC build. Layer 5 reference must be from mobile games
with comparable visual targets, not from PC or console games.
Establish a mobile lighting test scene from the start of production
and require all assets to pass review in it.

**Production cost:** Mobile lighting pass — texture adjustment, baked
lighting recalibration, material parameter adjustment across all assets.
Can be the most expensive platform-specific pass in cross-platform development.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
