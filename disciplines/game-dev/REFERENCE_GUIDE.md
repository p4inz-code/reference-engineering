# Game Development — Reference Engineering Guide

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Function & Context

### What to Find

**Core loop documentation:** The core loop is the 30-second action that
the player repeats most frequently. Every game has one. Reference comparable
games' core loops — not as descriptions ("you fight enemies and collect
loot") but as timed sequences ("combat engagement: 8–15 seconds. Loot
collection: 3–5 seconds. Movement to next encounter: 10–20 seconds.
Full loop: 21–40 seconds."). Timing the core loop of reference games
with a stopwatch is primary-tier Layer 1 reference.

**Player fantasy documentation:** What does the player believe they are
doing, as distinct from what they are mechanically doing? A tower defense
game mechanically involves placing units and watching numbers resolve.
The player fantasy is "I am a brilliant strategist defending my territory."
The fantasy governs what feedback the game must provide (strategic information,
visible success against enemies, clear territory ownership). Reference
comparable games and document how their mechanics serve the stated player fantasy.

**Genre convention reference:** Every genre has conventions that players
expect. An FPS player expects iron sights aiming. A roguelite player expects
permadeath. A puzzle game player expects undo. Departing from genre conventions
requires explicit justification — the convention exists because players
built a mental model from every other game in the genre.

**Platform context:** Mobile games have different session length expectations
than console games. PC games have different control precision than console
games. The platform defines the context that governs session design, UI
density, and control mapping.

---

## Layer 2 — Scale & Proportion (Pacing and Economy)

### What to Find

**Session length and loop timing:** How long is a typical play session for
this game type? How many core loops fit in a session? Mobile: 5–15 minutes.
Roguelite: 30–90 minutes per run. Open world: 60–180 minutes.
The session length governs content density, save point design, and
progression pacing.

**Economy balance reference:** Any game with resources, currencies, or
progression has an economy. Reference comparable games' economy design:
what is the earn rate? What is the spend rate? What is the scarcity/abundance
balance at early/mid/late game? These are measurable from playing the
reference game with deliberate attention.

**Level scale vs. player speed:** How large is a level relative to how
fast the player can traverse it? This ratio governs exploration pacing,
enemy density, and content distribution. Measure it in comparable games:
how many seconds does it take to traverse the width of a standard level?

---

## Layer 3 — Stage Reference

### Game Development Production Stages

| Stage | What You're Building | Reference Needed |
|---|---|---|
| Concept | Core loop definition, player fantasy | Genre analysis, comparable game documentation |
| Paper prototype | Mechanic rules on paper | Board game and card game analogs for mechanic clarity |
| Grey-box | Playable mechanic test | Comparable game feel parameters for calibration |
| Alpha | Full mechanic set, content sample | Difficulty curve reference, onboarding reference |
| Beta | Full content, balance | Economy reference, progression pacing reference |
| Polish | Game feel, juice | Input latency targets, feedback parameters |

### Stage-Appropriate Reference Practice

**At paper prototype stage:** Reference should answer whether the mechanic
makes sense on paper. Comparable board games and card games that implement
similar mechanics are useful reference here — they show whether the logic
is sound before the implementation cost is incurred.

**At grey-box stage:** Game feel reference becomes active. What are the
specific input response parameters (coyote time, jump buffer, input latency)
that make comparable games feel good? These are Layer 7 reference that
should be gathered at grey-box stage to inform implementation, not after
implementation is complete.

**At alpha stage:** Difficulty curve and onboarding reference are active.
Document how comparable games introduce mechanics: what is shown in level 1,
what is introduced in levels 2–5, what is withheld until the player
demonstrates competence?

---

## Layer 4 — Governing Rules

### The Mechanic Analysis Framework

The primary Layer 4 practice in game development is mechanic analysis:
taking a comparable game and extracting its specific mechanical rules
as documented parameters, not as descriptions.

**Mechanic Analysis Format:**

```
GAME: [title]
MECHANIC: [specific mechanic being analyzed]
DATE ANALYZED: [when you played and measured this]

MEASURED PARAMETERS:
[Parameter]: [measured value]
[Parameter]: [measured value]

EXTRACTED RULES:
1. [Rule stated as a design constraint]
2. [Rule stated as a design constraint]

WHAT THIS GAME NEVER DOES:
- [Negative constraint]
- [Negative constraint]

TRANSFERABLE TO OUR GAME:
- [What transfers]
NOT TRANSFERABLE:
- [What doesn't transfer and why]
```

**Example — Jump Mechanic Analysis (platformer):**

```
GAME: Celeste (2018)
MECHANIC: Jump feel
DATE ANALYZED: 2026-06

MEASURED PARAMETERS:
Coyote time: ~6 frames (100ms at 60fps)
Jump buffer: ~6 frames (100ms)
Jump height (tiles): ~3.5 tiles
Jump duration (frames to apex): ~25 frames
Variable jump height: yes (hold for full height, tap for short)
Air control: high (near-instant direction change)
Gravity on ascent: lower than on descent

EXTRACTED RULES:
1. Coyote time makes the jump forgiving without feeling wrong
2. Variable height gives skilled players control while novices still jump
3. Asymmetric gravity (lower on ascent, higher on descent) creates
   the "floaty then snappy" feel characteristic of precise platformers

WHAT CELESTE NEVER DOES:
- Locks player direction on jump initiation
- Makes jump feel punishing — every system adds forgiveness

TRANSFERABLE: Coyote time, jump buffer, variable height
NOT TRANSFERABLE: Air control level depends on level design — Celeste's
tight level design requires high air control; our more open level design
may need less
```

### Style Rules for Game Feel

Layer 4 in game development includes the written rules for game feel —
how the game responds to player input. These are specific and measurable:

- Input latency target (frames from input to visual response)
- Screen shake: duration, intensity, falloff curve
- Hit pause: duration (frames), which interactions trigger it
- Sound feedback: latency from action to audio response
- Camera follow: lag (frames), lead distance, shake behavior

---

## Layer 5 — Contextual Conditions

### Platform Input Reference

Each platform's input model constrains what is achievable and what
players expect. Document the input model before designing controls:

**Mobile:**
- Touch: tap, swipe, hold, pinch. No precision pointing.
- No keyboard or mouse unless external peripheral.
- Sessions interrupted frequently — must be pauseable at any moment.
- One hand or two? Portrait or landscape? Both must be designed for.

**Console (controller):**
- Analog sticks: precision varies by player and stick wear.
- Face buttons: 4 + triggers + bumpers. Remapping increasingly expected.
- Vibration/haptic feedback: use it — it's a communication channel, not decoration.
- Couch distance: UI must read at 3m+ from a TV.

**PC:**
- Mouse + keyboard: highest precision input.
- WASD + mouse is the genre-specific convention for most PC genres.
- Key remapping is expected — do not hardcode keys.
- Monitor distance: ~60–80cm. Much higher UI density than console.

### Session Context Reference

Different session contexts require different design approaches:

| Context | Typical session | Design implication |
|---|---|---|
| Mobile commute | 5–10 min | Short loops, instant pause, progress save per interaction |
| Console evening | 60–120 min | Longer loops, checkpoint save, social features |
| PC gaming session | 60–180 min | Deepest systems, highest complexity acceptable |
| Mobile casual | 2–5 min | Extremely short loop, clear immediate feedback |

---

## Layer 6 — Behavior & Construction

### Physics Parameters

If the game uses physics simulation, document the target parameters before
implementation. Common parameters requiring reference:

- Gravity: what real-world equivalent does this gravity correspond to?
  (Moon gravity, Earth gravity, exaggerated gravity for arcade feel)
- Player mass and friction: how does the player interact with surfaces?
- Projectile behavior: does it follow real ballistics or arcade ballistics?
- Collision response: rigid body? Soft body? Ragdoll?

### AI Behavior Documentation

Enemy AI behavior should be documented as rules before implementation:

- Aggression range: at what distance does the enemy engage?
- Attack pattern: what is the attack sequence? What signals the attack?
- Recovery time: after attacking, how long before the enemy can attack again?
- Group behavior: do enemies coordinate? How?

Documenting AI behavior as rules before implementation enables reference
comparison: does the implemented AI actually match the documented rules?

---

## Layer 7 — Precision Detail (Game Feel)

Game feel is the Layer 7 of game development. It is the precision craft
that makes a game feel good to play rather than merely function correctly.

### Key Game Feel Parameters to Reference and Document

**Coyote time:** Frames after leaving a platform edge during which the
player can still jump. Reference: 6–8 frames is the standard in
precision platformers. More forgiving games: 10–12 frames.

**Jump buffer (input buffer):** Frames before landing during which a
jump input is registered and executed on landing. Standard: 6–10 frames.

**Hit pause (hitstop):** Frames of frozen time on a successful hit.
Standard: 2–4 frames for light hits, 6–10 for heavy hits. Creates
the "weight" of combat.

**Screen shake:** Duration: 8–12 frames. Intensity: decreasing curve,
not constant. Direction: randomly distributed or physically motivated.

**Input latency target:** Time from player input to visual response.
Target: under 3 frames (50ms) for responsiveness. Over 5 frames (83ms)
starts to feel sluggish to experienced players.

**Sound feedback latency:** Sound should trigger within 1–2 frames of
the action it responds to. Sound that arrives late disrupts feel more
than graphics that arrive late.

---

## The Game Development Reference Brief

```
PROJECT: [game title]
GENRE: [genre]
PLATFORM: [platform(s)]
DATE: [brief version date]

LAYER 1 — FUNCTION & CONTEXT
Core loop (timed): [describe with frame/second counts]
Player fantasy:
Genre conventions that must be honored:
Top 3 reference games:

LAYER 2 — PACING & ECONOMY
Target session length:
Core loop duration:
Economy earn/spend rates (if applicable):

LAYER 3 — CURRENT STAGE
[ ] Concept  [ ] Paper prototype  [ ] Grey-box  [ ] Alpha  [ ] Beta  [ ] Polish
Stage reference gathered:

LAYER 4 — GOVERNING RULES
Mechanic analyses completed:
Key extracted rules:
What this game NEVER does:

LAYER 5 — PLATFORM CONTEXT
Target platform:
Input model:
Session context (mobile commute / console evening / other):
UI read distance:

LAYER 6 — BEHAVIOR & CONSTRUCTION
Physics parameters:
AI behavior rules (if applicable):
Save/checkpoint model:

LAYER 7 — GAME FEEL PARAMETERS
Input latency target (frames):
Coyote time (frames):
Jump buffer (frames):
Hit pause (frames):
Screen shake (duration/intensity):

GAPS:
Critical:
High:

BRIEF VERSION: [v1.0 / v2.0 / vFinal]
```

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
