# Reference Engineering — Game Development

> Systematic pre-production reference methodology for game developers designing mechanics, systems, and player experiences.

**Discipline:** Game Development
**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Who This Is For

Game developers designing and implementing game mechanics, systems, and
player experiences. Covers indie solo developers through small teams.
Focus on the reference work that governs design decisions — mechanic feel,
system balance, difficulty curve, onboarding — rather than art production
(see `disciplines/game-art/`) or technical implementation.

---

## What Reference Engineering Solves in Game Development

Game development has a specific reference failure that no other discipline
shares: playtesting is the primary validation mechanism, but playtesting
is expensive, late, and cannot cover all decisions. Reference Engineering
in game development is the discipline of answering as many design questions
as possible from the documented experience of comparable games before
a single playtest is run.

The most common reference failure in game design: the designer references
only games they love, and references them by feel rather than by extracted
rules. "It should feel like Dark Souls" is not a design brief — it is
an undocumented assumption about what "Dark Souls feel" means. Extracting
the specific mechanical rules that produce the Dark Souls feel — death
state behavior, enemy aggression patterns, stamina economy, hitbox
precision — is Reference Engineering.

---

## The Pre-Production Questions Game Dev Must Answer

- [ ] What is the core loop? (the 30-second action the player repeats most)
- [ ] What is the player fantasy? (what does the player feel they are doing, not what they are mechanically doing?)
- [ ] What comparable games have solved a similar core loop? What are their specific mechanical rules?
- [ ] What does "game feel" mean for this game — in specific, measurable parameters?
- [ ] What is the difficulty curve and what reference documents it?
- [ ] What is the onboarding sequence and what comparable games do it well?
- [ ] What is the failure state behavior and how does the player learn from failure?
- [ ] What platform conventions govern input and control mapping?

---

## Pyramid Layer Map for Game Development

| Pyramid Layer | What It Means in Game Development |
|---|---|
| Layer 1 — Function & Context | Core loop, player fantasy, genre conventions, platform context |
| Layer 2 — Scale & Proportion | Pacing (session length, loop duration), economy balance, level size vs. player speed |
| Layer 3 — Stage Reference | Paper prototype reference; grey-box reference; playtest reference per milestone |
| Layer 4 — Governing Rules | Extracted mechanical rules from reference games — specific numbers, not feelings |
| Layer 5 — Contextual Conditions | Target platform input model, screen size, session context (mobile: short; console: long) |
| Layer 6 — Behavior & Construction | Physics parameters, hitbox behavior, AI behavior documentation |
| Layer 7 — Precision Detail | Game feel: coyote time, jump buffer, screen shake parameters, input latency targets |

---

## Contents

| File | What's in it |
|---|---|
| [`REFERENCE_GUIDE.md`](./REFERENCE_GUIDE.md) | Full methodology — all seven layers, mechanic analysis framework, brief template |
| [`mistakes.md`](./mistakes.md) | 7 game-dev-specific failure modes |
| [`checklist.md`](./checklist.md) | Pre-production checklist, stage-organized |
| [`sources.md`](./sources.md) | Best game development reference sources |

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
