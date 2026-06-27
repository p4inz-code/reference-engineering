# Game Development — Reference Sources

Best sources for Reference Engineering in game development, by Pyramid layer.

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Core Loop and Genre Context

**The reference games themselves** — PRIMARY METHOD
Play comparable games with deliberate intent. Time the core loop.
Count sessions. Note what the player does in the first 30 seconds.
Document what the game withholds and what it gives immediately.
No secondary source replaces playing the actual game with measurement intent.

**GDC Vault** — FREE / PAID
gdcvault.com — the largest archive of game development talks.
Designers from shipped games discuss their design decisions, including
core loop design, player fantasy, and mechanic rationale. Primary-tier
Layer 1 reference when the designer discusses their own game's design intent.

**Game Maker's Toolkit (YouTube)** — FREE
Mark Brown's analysis channel. Deep mechanic analysis of specific games
with clear extraction of design rules. Strong Layer 1 and Layer 4 reference.
Secondary-tier (analysis, not designer's own words) but high quality.

**Deconstructor of Fun** — FREE
deconstructorfun.com — mobile game design analysis. Focuses on monetization,
retention loops, and core loop design for mobile. Primary-tier for mobile
game Layer 1 reference.

---

## Layer 2 — Pacing and Economy

**Playing reference games with a stopwatch** — PRIMARY METHOD
Timer the core loop duration. Timer the session before the first save point.
Time how long before the player gets their first resource. These are
measurable in any game and primary-tier when measured directly.

**Game Economy Design (book — Josh Bycer)** — PAID
Dedicated resource on game economy design with case studies. Layer 2
primary reference for economy design.

**GDC: Economy Design talks** — FREE / PAID
Multiple GDC talks address economy design specifically for various game types.
Search GDC Vault for "economy design" filtered by game type.

---

## Layer 3 — Stage Reference

**Board game / card game analogs** — FREE / PAID
For paper prototype stage: board games and card games that share mechanical
logic with the digital game being designed. Pandemic for cooperative mechanics.
Dominion for deck-building loops. Settlers of Catan for resource economy.
Playing comparable board games tests mechanic logic at zero implementation cost.

**Itch.io game jams** — FREE
itch.io has thousands of small games built in 48–72 hours. Useful for finding
simple implementations of specific mechanics to reference at the grey-box stage.
The simplicity of jam games makes mechanical logic visible.

**Design Documents from shipped games** — FREE (where published)
Some developers have published or discussed their original design documents.
These are rare but valuable — they show what the design intent was before
implementation. Search "[game title] game design document" or GDC talk by
the designer.

---

## Layer 4 — Governing Rules

**YouTube: Frame-by-frame analysis** — FREE
Record gameplay of reference games and step through frame-by-frame in
a video editor. Count coyote time frames. Count hit pause frames.
Measure screen shake duration. This is the primary measurement method
for Layer 4 game feel parameters.

**Game Feel (book — Steve Swink)** — PAID
The definitive resource on game feel as a design discipline. Documents
the specific parameters that constitute game feel and provides a framework
for analysis. Layer 4 and Layer 7 reference.

**"Math for Game Developers" (YouTube — Jorge Rodriguez)** — FREE
Physics and math used in game mechanics explained at an implementation level.
Primary reference for understanding why specific parameter values produce
specific feel outcomes.

**Celeste GDC Talk (Maddy Thorson)** — FREE (GDC Vault)
"Designing Celeste" — one of the most detailed public discussions of
platformer feel parameters. Documents specific values for coyote time,
jump buffering, and other Layer 7 parameters in a shipped game.

---

## Layer 5 — Platform Context

**Apple Human Interface Guidelines (Games)** — FREE
developer.apple.com/design — guidelines for iOS game design including
touch input, Game Center integration, and session design for mobile.

**Xbox Accessibility Guidelines** — FREE
docs.microsoft.com/gaming — comprehensive accessibility reference for
console games. Also covers controller input model and remapping expectations.

**Google Play Game Services Documentation** — FREE
developer.android.com/games — Android game development reference including
input model, save game design, and session context.

**Steam Hardware Survey** — FREE
store.steampowered.com/hwsurvey — real hardware distribution for PC gaming.
Primary-tier Layer 5 reference for minimum PC spec decisions.

---

## Layer 6 — Behavior and Construction

**Box2D Documentation** — FREE
box2d.org — the most widely used 2D physics engine. Primary-tier for
understanding 2D physics parameters and their real-world equivalents.

**Unity / Unreal Physics Documentation** — FREE
docs.unity3d.com / docs.unrealengine.com — physics system documentation.
Primary-tier for engine-specific physics behavior.

**AI for Games (book — Ian Millington)** — PAID
Comprehensive reference for game AI implementation. Layer 6 primary
reference for behavior tree design, pathfinding, and enemy AI patterns.

**Blueprints Visual Scripting (UE5)** — FREE
docs.unrealengine.com/5.0/en-US/blueprints-visual-scripting-in-unreal-engine
Primary-tier for UE5 AI and behavior implementation reference.

---

## Layer 7 — Game Feel

**Juice It or Lose It (GDC 2012)** — FREE (YouTube)
Martin Jonasson and Petri Purho's classic talk on game feel. Demonstrates
the specific parameters of screen shake, hit pause, sound feedback, and
visual feedback that produce the "juice" feel. Essential Layer 7 reference.

**The Art of Screenshake (GDC 2013)** — FREE (YouTube)
Jan Willem Nijman's talk on screen shake parameters. Documents specific
values and their effect on game feel. Layer 7 primary reference for
screen shake design.

**Vlambeer Game Feel resources** — FREE
Rami Ismail and Jan Willem Nijman of Vlambeer have produced extensive
public content on game feel. Search "Vlambeer game feel" on YouTube.

**Input Latency Measurement tools** — FREE
NVIDIA LDAT, Blur Busters' input lag testing resources. Used to measure
actual input latency in reference games and in your own implementation.
Primary-tier measurement tool for Layer 7 input latency targets.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
