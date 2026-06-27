# Character Design — Lessons

**Brief versions:** v1 (pre-production) → v2 (post-blockout)
**Decisions documented:** 17 primary, 2 open assumptions
**Reference items used:** 22 (9 T1, 10 T2, 3 T3)
**V2 updates to v1 decisions:** 3 (hat brim size, lapel geometry, strap offset)

---

## What the Brief Lifecycle Demonstrated

This example shows exactly why reference briefs are versioned, not static.

**v1 was correct at the time it was written.** The hat brim at 15cm was
a reasonable decision from silhouette reference. The lapel geometry as
single mesh was a reasonable default. The satchel strap without offset
was a reasonable starting point.

**Production revealed what pre-production could not know.** The camera clip
at climbing animation was not guessable from static reference — it required
an in-engine test. The lapel chin intersection was not visible in blockout
images — it appeared at the first animation test. The strap artifact was
not visible at rest — it appeared at full shoulder deformation.

Three decisions changed between v1 and v2. All three changes were
improvements. All three were production-revealed, not pre-production-foreseeable.

**The lesson is not that v1 was wrong.** The lesson is that v2 was necessary.
A frozen brief at v1 would have delivered a character with a clipping hat,
intersecting lapels, and a visible strap artifact. The brief versioning
practice is what prevented those from reaching delivery.

---

## What Reference Engineering Prevented

**Archetype Drift**
The historical reality of 1930s archaeologists (scholars, not action heroes)
was researched and explicitly set aside in favor of the pulp fiction version.
This is not ignorance — it is a documented design decision. The character
knows what it is departing from and why. That departure is now a design
rule, not an accident.

Without this research, the character would have drifted toward either:
(a) a generic "rugged outdoors" character with no specific archetype
(b) an accidental parody of the Indiana Jones archetype through copying
    without analysis

**The proportion trap**
7.1 heads is a specific number with a specific reference basis. Without
proportion reference, "slightly exaggerated" would have meant whatever
the modeler's intuition produced — which in practice tends to drift toward
what they have modeled most recently. The reference anchors the decision.

**Decorative wrinkles**
"Folds follow function logic only" is a rule that prevents the most common
character costume mistake: wrinkles added for visual interest rather than
physical accuracy. Decorative wrinkles look right in still renders and
wrong in motion — they don't animate correctly because they were never
placed for physical reasons. Primary reference (real garment photography)
makes the function logic clear.

**The back-of-character detail trap**
Without the camera zone analysis, the natural tendency is to invest equal
detail across the full character. The reference (UE5 camera distance test)
establishes that the back of the character is rarely seen at primary camera
angles — which redirects texel budget to zones that actually matter. This
is not an obvious decision. It requires camera testing, not intuition.

---

## Cross-Reference Findings

**Pulp illustration (T1) + comparable games (T2) converged on the same proportions.**
The 20–25% shoulder exaggeration range appeared in both the pulp source
material and in modern stylized game characters. This cross-tier confirmation
— T1 historical source and T2 contemporary execution agreeing — gave the
proportion decisions CONFIRMED confidence without needing additional validation.

**Historical reality (T1) contradicted pulp (T1) — and the contradiction was design information.**
Real 1930s archaeologists do not look like pulp adventurers. Both are T1
sources. The contradiction between them is not a reference problem — it is
the core design decision: which version of reality is this character?
Documenting the contradiction explicitly produced a clearer brief than
ignoring it would have.

---

## Transferable Lessons

**1. For archetype-based characters, research the reality AND the myth — and document the gap between them.** The gap is design information. The decision about where on the reality-to-myth spectrum the character lives is one of the most important design decisions, and it is made better with explicit reference than with intuition.

**2. Silhouette reference must be validated at primary gameplay poses, not just T-pose.** T-pose silhouette analysis is necessary but not sufficient. A character that reads well in T-pose and fails at climbing or combat is a character that was designed for the wrong reference context.

**3. The camera zone analysis is one of the highest-ROI reference passes in character production.** Thirty minutes of camera distance testing redirects weeks of texel budget investment. It is always worth doing before hero detail begins.

**4. Brief v2 is not optional — it is where production-revealed gaps are closed.** Budget the time for a post-blockout brief update. It takes two to three hours and prevents problems that would each take longer than that to fix at delivery.

**5. Cloth and deformation reference should be gathered at v1, not discovered at v2.** The lapel and strap issues were foreseeable with rig deformation reference at the pre-production stage. They were not gathered because Layer 6 was underweighted in v1. Next time: Layer 6 reference (deformation behavior) is mandatory pre-production, not post-blockout.

---

## Pyramid Layer Status at v2 Close

| Layer | Status | Notes |
|---|---|---|
| 1 — Function & Context | ✅ Complete | Archetype, gameplay function, narrative role |
| 2 — Scale & Proportion | ✅ Complete | Head count, exaggeration rules, all locked |
| 3 — Stage Reference | ✅ Complete | Silhouette + blockout; detail deferred correctly |
| 4 — Governing Rules | ✅ Complete | Shape language, style rules, NEVER list |
| 5 — Contextual Conditions | ✅ Complete | Camera zones, lighting, LOD |
| 6 — Behavior & Construction | ✅ Complete | All deformation zones addressed (v2 additions) |
| 7 — Precision Detail | ✅ Complete | Skin, wear zones, costume detail (v2) |

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
