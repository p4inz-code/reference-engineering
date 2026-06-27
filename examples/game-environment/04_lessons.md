# Game Environment — Lessons

**Brief final version:** 1.1
**Decisions documented:** 13 primary, 3 open gaps, 2 flagged assumptions
**Reference items used:** 18 (8 T1, 7 T2, 3 T3)
**Contradictions resolved:** 0 (sources were consistent — unusual; note for future)
**Pyramid layer coverage at close of pre-production:**

| Layer | Status |
|---|---|
| 1 — Function & Context | ✅ Complete |
| 2 — Scale & Proportion | ✅ Complete |
| 3 — Stage Reference | ✅ Complete (silhouette + blockout; UV and detail deferred correctly) |
| 4 — Governing Rules | ~ Partial (desaturation not locked — Gap 03) |
| 5 — Contextual Conditions | ✅ Complete (Lumen spec confirmed — subject to A01) |
| 6 — Behavior & Construction | ✅ Complete |
| 7 — Precision Detail | ✅ Pre-gathered, deferred to mid-production (correct) |

---

## What Reference Engineering Prevented

**The diagonal damage cut**
Without explicit structural analysis of how these buildings actually fail,
the default would have been to add diagonal damage for visual variety.
The Pripyat documentation makes clear that diagonal clean cuts are
structurally incorrect for this building type. That error would have
been invisible during production and would have read as subtly wrong
to any structural-literacy viewer. Primary reference caught it before
it was built.

**The wrong scale**
Soviet-era floor-to-floor height (2.5m) is meaningfully lower than
Western residential (2.7m) and commercial (3.0m+). Without documentation,
the floor height would have defaulted to whatever felt right — which for
a practitioner trained on Western reference would have been 0.2–0.5m too
tall. At environment scale, this compounds across multiple floors and
produces a building that reads as subtly wrong without viewers identifying
the specific error.

**The wrong rust albedo**
The counterintuitive darkness of iron oxide in linear color space (0.04–0.12)
is frequently incorrect in artist work. Rust is perceived as orange and
is painted as orange — which in linear space is far too bright and
produces incorrect Lumen GI interactions. PBR documentation caught this
before any materials were built.

**The Pinterest problem**
The brief structure forced the exclusion of generic "post-apocalyptic"
Pinterest reference. That reference is predominantly American/Western
in building type, frequently stylized, and calibrated to different
weathering and climate conditions. The brief's requirement for
question-specific reference prevented its inclusion — keeping the
board clean for the Pripyat documentation that was actually useful.

---

## What to Do Differently

**Lock Gap 03 before starting the brief**
The desaturation level should have been an art director decision made
before pre-production, not a gap left open after it. For any project
with a style decision that will affect material production, that decision
needs to be a hard input to the brief, not a soft output of it.
Action for next project: add "art direction locked?" as a pre-brief
requirement check.

**Research Gap 01 (module count) at the start of pre-production, not after**
The modular kit module count is a scope decision that affects the entire
production plan. It should have been researched before the brief was
written — not left as a gap to be resolved before production scope is
locked. The correct workflow: research comparable marketplace kits as
part of project initiation, not as part of reference gathering.

**Test interior visibility (Gap 02) earlier**
The interior visibility gap was correctly identified but deferred. The
problem is that interior content decisions affect what UV space is
needed for interior surfaces — which affects UV planning, which
affects the Stage 3 reference pass. This dependency means Gap 02
should be resolved earlier than mid-production.

---

## Transferable Lessons

**1. Chernobyl/Pripyat is one of the best primary reference sources in existence for post-Soviet post-apocalyptic environments.** Timeline match (15–20 years at time of documentation), building type match (Khrushchyovka), climate match (Eastern European continental), and documentation quality are all exceptional. Future projects in this genre should begin here.

**2. Construction documentation (SNiP standards for Soviet-era buildings) is primary reference that most practitioners overlook.** Searching architecture databases and construction standards instead of only visual reference produced the most important scale and proportion decisions in this brief.

**3. Cross-tier confirmation is more valuable than same-tier confirmation.** The concrete roughness range was supported by T2 (Metro Exodus) and T3 (materials science principle). A T1 + T2 confirmation would be better. The gap — the absence of a primary measured source — was correctly flagged as a reason to seek Megascans data.

**4. "What this design NEVER does" is more actionable during production than positive style rules.** The prohibition on diagonal damage cuts, uniform aging, and concrete specular was checked more frequently during production than the positive style descriptions. Negative constraints are faster to verify.

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
