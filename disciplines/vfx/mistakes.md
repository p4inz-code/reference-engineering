# VFX — Reference Engineering Mistakes

Seven failure modes specific to VFX reference practice.

---

## MISTAKE 01 — CG Reference for CG Output

> *"I looked at other VFX breakdowns as reference."*

**Symptom:** The finished VFX looks like VFX. Not like the real phenomenon —
like digital art approximating the phenomenon. The tell is always in the
motion: CG-referenced CG has the motion of CG VFX, not the motion of
fire or water or explosions.

**Cause:** Other VFX was used as primary reference instead of real-world
footage. The reference was Secondary or Tertiary tier, used without
translation, as if it were Primary.

**Fix:** For any simulation of a real-world phenomenon, real-world footage
is the only Primary reference. Other VFX is Secondary at best — useful
for understanding how an effect was achieved technically, not for understanding
how the phenomenon actually behaves.

**Production cost:** Re-simulation after client review rejects the effect
as "feeling CG." Timing, density, and turbulence parameters that were
calibrated to other CG must be recalibrated to real-world behavior.

---

## MISTAKE 02 — Missing Phase Reference

> *"I have great reference for the explosion. The onset looks wrong though."*

**Symptom:** Effect looks correct at peak and wrong at onset and/or
dissipation. Client approves the hero frame and asks for fixes on the
twenty frames before it.

**Cause:** Reference was gathered for the peak state only. The phase
structure was not used as an organizing principle for reference gathering.
Onset and dissipation were simulated from memory or intuition because
no reference existed for them.

**Fix:** Before any reference board is built, define the three phases and
gather reference for each phase separately. The onset reference and
dissipation reference are as important as the peak reference.
A sim that gets all three phases right is a convincing sim.

**Production cost:** Re-simulation or heavy manipulation of onset and
dissipation segments. If the sim parameters were tuned for peak, changing
them for onset may break peak. Multiple re-sim iterations.

---

## MISTAKE 03 — Timing from Feeling

> *"It felt too slow so I sped it up."*

**Symptom:** Effect timing that doesn't match the scale. A small explosion
that takes as long as a large one. Fire that rises too slowly because
"slow looks more dramatic." Smoke that dissipates too fast because "it
was getting boring."

**Cause:** Layer 2 (Scale & Proportion) timing reference was absent.
Timing was adjusted by aesthetic feel rather than by real-world measurement.
Real phenomena have scale-dependent timing: small fires burn faster
than large ones. Small explosions resolve faster than large ones.

**Fix:** Count frames in real-world footage for the specific scale of
effect. Document timing as frame counts at the target frame rate.
Apply those frame counts as constraints, not as starting points.
Aesthetic adjustments should be made from a documented baseline,
with the delta from reality explicitly noted.

**Production cost:** Timing corrections after the composite is built
require re-renders and re-composites. If timing is wrong, all downstream
work (secondary elements, audio sync, lighting response) is wrong.

---

## MISTAKE 04 — Wrong Color Model

> *"I made the fire orange because fire is orange."*

**Symptom:** Fire that reads as cartoon-orange. Explosions that don't
have the correct color progression. Smoke that is the wrong gray.
The effect passes a quick glance but fails under scrutiny because the
color doesn't follow the real physical behavior.

**Cause:** Color was applied from memory ("fire is orange") rather than
from real-world reference documenting the actual color behavior of the
phenomenon. Real fire follows blackbody radiation: the hottest part
is near-white or blue-white, not orange. Orange is the cooler outer flame.

**Fix:** For every effect, gather color reference per phase and per zone
(core vs. edge). Document colors as hex values from real footage using
a color picker. Apply the documented values as Layer 4 governing rules,
not as personal aesthetic choices.

**Production cost:** Color correction across the full effect after
client review. If the color is wrong at the simulation level (not just
at the composite level), re-simulation required.

---

## MISTAKE 05 — Composite Context Ignored

> *"The effect looked great in preview. It looks wrong in the shot."*

**Symptom:** VFX that looks correct in isolation and wrong in the final
composite. Common specific problems: color temperature mismatch between
VFX and plate, edge behavior that doesn't match the plate's motion blur,
exposure mismatch where the VFX is too bright or too dark relative to
the plate's real-world lighting.

**Cause:** Layer 5 (Contextual Conditions) reference — the composite
environment — was not gathered. The effect was developed in isolation
against a neutral background. The real plate was not in the reference
board.

**Fix:** From the start of development, use the actual background plate
(or a close proxy) as the Layer 5 reference. Every visual parameter
of the VFX should be validated against the plate: color temperature,
exposure, edge behavior, motion blur. If the plate is not available
early, use a representative frame from a comparable shot as proxy.

**Production cost:** Composite-level corrections can address some mismatches
but not all. Fundamental color temperature or scale mismatches require
re-simulation or re-render.

---

## MISTAKE 06 — Real-Time Budget Discovered Mid-Development

> *"It runs at 12fps on the target platform."*

**Symptom:** Real-time VFX effect that looks correct but cannot run at
target frame rate on target hardware. Performance budget is discovered
after the effect is fully developed.

**Cause:** Layer 5 (Contextual Conditions) reference for real-time
performance budget was absent. Particle count, overdraw, and draw call
constraints were not documented before development began.

**Fix:** Before any real-time VFX is developed, document the performance
budget: maximum particle count, maximum overdraw, draw call limit.
Profile comparable effects from shipped games on the target platform
to establish realistic baselines. Design to the budget, then add detail.

**Production cost:** Optimization pass that may require fundamental
redesign of the effect to hit budget. Low-detail fallback that doesn't
match the design intent. Platform-specific variants that duplicate work.

---

## MISTAKE 07 — Looping Without Loop Reference

> *"The loop point is really obvious."*

**Symptom:** Looping ambient VFX (fire, smoke, magic effects) with a
clearly visible loop point. The effect resets visibly at the loop.
Users notice and it breaks immersion.

**Cause:** Layer 7 (Precision Detail) looping reference was absent.
The loop technique was not researched before implementation. Common
approaches (cycle offset, crossfade, multiple instance stagger) were
not referenced and applied.

**Fix:** Before building any looping effect, gather reference for how
comparable looping effects achieve invisible loops. The primary techniques:
cycle offset (particles start at different points in the sim), instance
stagger (multiple instances of the same effect offset in time),
crossfade (blend between loop end and loop start). Research which
is appropriate for this effect type.

**Production cost:** Loop redesign after the effect is otherwise complete.
Depending on the technique required, this may require resimulating
with a different particle system structure.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
