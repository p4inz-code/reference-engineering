# Game Development — Reference Engineering Mistakes

Seven failure modes specific to game development reference practice.

---

## MISTAKE 01 — "It Should Feel Like [Game]"

> *"Make it feel like Dark Souls."*

**Symptom:** Design brief based on feel reference to an existing game with
no extracted mechanical rules. Team members implement their own interpretation
of "Dark Souls feel." Results diverge because there is no shared specific
reference. Client or director says "this doesn't feel like the reference"
with no specific critique possible.

**Cause:** Layer 4 (Governing Rules) reference was stated as an emotional
impression rather than extracted as specific mechanical parameters. "Feel
like Dark Souls" is not a design specification. The specific rules that
produce the Dark Souls feel — death state behavior, stamina economy, hitbox
precision, enemy aggression patterns, item scarcity — are design specifications.

**Fix:** For every feel reference game, run a mechanic analysis (see
REFERENCE_GUIDE.md). Extract the specific parameters: what are the actual
numbers? What does the game actually do mechanically that produces the
stated feel? Write the rules down before any implementation begins.

**Production cost:** Iterative feel adjustments without a clear target.
Can consume 30–50% of a polish milestone chasing a feel that was never
defined specifically enough to hit.

---

## MISTAKE 02 — Reference from Memory

> *"I've played that game a hundred times. I know how it works."*

**Symptom:** Mechanic analysis based on remembered experience rather than
deliberate measurement. Parameters are estimated ("I think the coyote time
is about half a second") rather than measured (counting frames in footage).
Implemented mechanics feel slightly off from the reference without a clear
reason why.

**Cause:** Tier assignment error. Experienced gameplay knowledge is at best
Secondary reference — it is the practitioner's memory of a Secondary source.
It was treated as Primary. Human memory of game feel is unreliable for
specific parameter values.

**Fix:** Play the reference game with deliberate measurement intent, not
from memory. Record gameplay and count frames. Use a stopwatch for timing.
Document measured values, not remembered impressions. Even games played
hundreds of times should be re-played with a reference sheet in hand.

**Production cost:** Parameters calibrated to memory rather than measurement
produce a mechanic that almost feels right. The almost is noticed by players
and is described as "something feels off" — hard to diagnose without the
documented baseline.

---

## MISTAKE 03 — Genre Convention Ignored

> *"We thought making it different would be a feature."*

**Symptom:** Players find the game confusing despite it being internally
consistent. Support tickets and reviews say things like "the controls feel
backwards" or "I don't understand how to do X." The game doesn't feel
wrong to the developers who built it. It feels wrong to players who bring
genre expectations.

**Cause:** Layer 1 (Function & Context) genre convention reference was
absent or dismissed. The conventions were treated as optional rather than
as the mental model the target audience already has.

**Fix:** Before departing from any genre convention, document it explicitly.
"FPS players expect iron sights on right-click. We are departing from this
because [specific reason]. The alternative [specific alternative] is used
instead." Convention departures should be deliberate decisions with reference
support, not default oversights.

**Production cost:** Onboarding redesign and tutorial investment to compensate
for broken player expectations. In some cases, convention violations are
too deep to fix without a fundamental mechanic change.

---

## MISTAKE 04 — Economy Balance Without Reference

> *"We'll tune the economy during beta."*

**Symptom:** Economy that feels wrong in ways the team can't precisely diagnose.
Players grind too much or progress too fast. Resources feel either scarce
to frustration or abundant to meaninglessness. Beta tuning takes longer
than planned because there is no reference target to tune toward.

**Cause:** Layer 2 (Scale & Proportion) economy reference was absent.
The earn and spend rates were designed without reference to comparable
games' documented economies. Beta tuning is trying to find a target that
was never defined.

**Fix:** Before designing any economy, measure comparable games' economies
with deliberate play sessions. Document earn rate (resources per minute
of play), spend rate (resources per meaningful purchase), and the resulting
scarcity/abundance ratio at early/mid/late game. Use these measurements
as the design targets, not as inspiration.

**Production cost:** Extended beta balance phase. In extreme cases, economy
redesign late in development when the wrong balance produces the wrong
player experience.

---

## MISTAKE 05 — Difficulty Without Curve Reference

> *"Players are dropping off in level 3. We don't know why."*

**Symptom:** Player retention curve drops at a specific point that corresponds
to a difficulty spike. The team didn't see the spike during development
because developers are not representative players. The spike was not visible
because no difficulty curve reference was used as a design target.

**Cause:** Layer 3 (Stage Reference) difficulty curve reference was absent
at the alpha stage. The difficulty curve was designed from developer intuition
rather than from documented curves in comparable games.

**Fix:** Before designing level difficulty, map the difficulty curve of
3+ comparable games: what is the complexity introduced per level? What is
the first moment the player is allowed to fail? What is the steepest difficulty
increase between any two consecutive levels? Use these curves as reference
targets, not as inspiration.

**Production cost:** Level redesign post-launch or post-testing to address
retention spikes. If level design is tightly integrated with content (story,
art), difficulty redesign cascades.

---

## MISTAKE 06 — Game Feel as Afterthought

> *"We'll add the juice in polish."*

**Symptom:** Polish milestone takes longer than planned. Game feel parameters
(screen shake, hit pause, camera behavior, input buffering) are implemented
without reference targets, requiring iterative tuning. The feeling of
"complete" is never reached because there is no documented target.

**Cause:** Layer 7 (Precision Detail / Game Feel) reference was not gathered
before implementation. Game feel parameters were treated as decoration to
add at the end rather than as design specifications to gather before
implementation begins.

**Fix:** Layer 7 game feel parameters should be documented at the grey-box
stage. What are the coyote time, jump buffer, hit pause, screen shake,
and input latency targets? These come from mechanic analysis of reference
games. Implementation targets the documented values. Polish adjusts from
a documented baseline.

**Production cost:** Extended polish milestone without a clear endpoint.
Game feel tuning without reference is subjective and unstable — changes
are made, reverted, and remade without progress toward a defined target.

---

## MISTAKE 07 — Platform Input Assumptions

> *"We designed on PC. Port to mobile later."*

**Symptom:** Mobile or console port that requires fundamental redesign
rather than surface-level control remapping. Core mechanics designed for
mouse precision don't work with touch or analog stick. UI designed for
60cm monitor distance doesn't read at 3m TV distance.

**Cause:** Layer 5 (Contextual Conditions) platform input reference was
absent for the secondary platform. The game was designed for one platform's
input model and ported to another's without the porting platform's input
constraints in the original brief.

**Fix:** If multi-platform is planned, gather platform input reference for
all target platforms before core mechanic design begins. Some mechanics
are fundamentally incompatible with certain input models — discovering
this before implementation is far less expensive than discovering it
during porting.

**Production cost:** Mobile port that requires redesigning core mechanics.
In the worst case: planned platform is canceled because the port cost
exceeds revenue potential after the redesign scope becomes clear.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
