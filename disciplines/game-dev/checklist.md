# Game Development — Reference Engineering Checklist

Run before first implementation. Run again at each production milestone.
Mark: ✓ Complete / ~ Partial / ✗ Missing / N/A Not applicable

---

## CONCEPT STAGE

### Layer 1 — Core Loop and Fantasy
- [ ] Core loop described with timing (not just description — frame/second counts)
- [ ] Player fantasy stated in one sentence
- [ ] Genre conventions listed and each tagged: honor / depart / why
- [ ] Top 3 reference games identified
- [ ] Top 3 reference games played with deliberate measurement intent (not from memory)

### Layer 2 — Pacing and Economy
- [ ] Target session length documented
- [ ] Core loop duration measured in reference games
- [ ] Economy earn/spend rates measured in reference games (if applicable)

---

## PAPER PROTOTYPE STAGE

- [ ] Core mechanic describable in rules on paper
- [ ] Mechanic analyses completed for top 3 reference games
- [ ] Extracted rules documented as specific parameters (not as feelings)
- [ ] "What this game NEVER does" list written
- [ ] Difficulty curve reference gathered for comparable games

---

## GREY-BOX STAGE

### Layer 7 — Game Feel (gather NOW, not at polish)
- [ ] Input latency target documented (frames)
- [ ] Coyote time documented (frames) — if platformer
- [ ] Jump buffer documented (frames) — if platformer
- [ ] Hit pause documented (frames) — if combat
- [ ] Screen shake parameters documented (duration/intensity/falloff)
- [ ] Sound feedback latency target documented

### Layer 5 — Platform Context
- [ ] Target platform input model documented
- [ ] Session context documented (mobile commute / console evening / PC session)
- [ ] UI minimum read distance confirmed
- [ ] Control mapping documented against platform conventions

---

## ALPHA STAGE

- [ ] Onboarding sequence mapped against comparable games
- [ ] Difficulty curve documented against comparable reference curves
- [ ] All genre conventions checked: honor or document departure with reason
- [ ] Economy balance targets set from reference game measurements
- [ ] AI behavior documented as rules (if applicable)
- [ ] Physics parameters documented against real-world or reference equivalents

---

## BETA STAGE

- [ ] Economy balance validated against documented targets (not tuned blindly)
- [ ] Difficulty curve validated against reference targets
- [ ] Retention data (if available) checked against difficulty curve reference
- [ ] All platform variants tested against platform-specific input model

---

## POLISH STAGE

- [ ] Game feel parameters implemented to documented targets
- [ ] Parameters adjusted from documented baseline (changes are traceable)
- [ ] Audio feedback latency confirmed within target
- [ ] Input latency profiled and confirmed within target
- [ ] Brief vFinal written with lessons

---

## COMMON GAPS IN GAME DEVELOPMENT BY GAME TYPE

| Game Type | Most Commonly Missing |
|---|---|
| Platformer | Layer 7 (coyote time, jump buffer), Layer 4 (platform convention analysis) |
| Roguelite | Layer 2 (run duration pacing), Layer 1 (progression vs. randomness balance) |
| RPG | Layer 2 (economy earn/spend rates), Layer 3 (difficulty curve) |
| Mobile casual | Layer 5 (session context — very short loops), Layer 1 (retention hook) |
| Action/combat | Layer 4 (hitbox and timing analysis), Layer 7 (hit pause) |
| Puzzle | Layer 1 (genre conventions — undo), Layer 3 (difficulty introduction pace) |
| Open world | Layer 2 (level scale vs. traversal speed), Layer 1 (player fantasy clarity) |

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
