# Kanvaz UI v2.0 — What Reference Engineering Would Have Changed

---

## Counterfactual 1: Autosave Implementation

**Decision that was made:** Implement autosave as a background timer that
writes to a separate autosave file, independent of the user's manual save.

**Production cost:** The feature shipped broken in v2.0.0. Emergency patch
required (v2.0.1). The highest-priority community request shipped as the
highest-profile bug. Community trust cost is harder to measure but real.

**What reference was missing:** Layer 6 — Behavior & Construction.
Specifically: how do canvas applications (Figma, Miro, PureRef-equivalent
tools) implement autosave? What are the known failure modes? What does
"autosave" mean in terms of user expectation about save state?

The specific reference to gather:
- Figma's version history model (continuous save, explicit version naming)
- Affinity Designer's backup model (timed backups, separate from save)
- Community discussions in canvas application forums about autosave expectations

**What decision would have been made:** The reference would have revealed
that canvas application users distinguish between "autosave" (continuous
background save to the working file) and "auto-backup" (periodic copy
to a separate location). The failure mode in v2.0.0 was building
"auto-backup" behavior while calling it "autosave" — which violated
user expectations established by the category.

The correct implementation (which reference would have specified):
Write directly to the working file on a short interval (30 seconds).
Maintain a separate versioned backup directory with user-accessible
restore. This is the pattern the category has converged on.

**Confidence in counterfactual:** HIGH
The research is straightforward. The failure mode is well-documented in
developer community discussions. The corrected implementation is clear
from category analysis.

**Time cost of reference:** 2–3 hours of canvas application autosave
pattern research.
**Time cost of shipping wrong:** 4–6 hours of bug investigation and patch
development, plus ongoing community management.

---

## Counterfactual 2: Toolbar Layout

**Decision that was made:** Toolbar layout revised four times, final version
selected at time pressure, not reference.

**Production cost:** ~8 hours of revision time across four passes, with no
clear improvement trajectory and no reference anchor.

**What reference was missing:** Layer 4 — Governing Rules.
Specifically: what visual rules govern professional creative tool toolbars?
What does the best-regarded reference board tool in this category do, and why?

The specific reference to gather:
- PureRef toolbar analysis (systematic, not experiential): what is in the
  toolbar, in what order, at what size, with what iconography?
- Comparable creative tool toolbar analysis: Affinity Designer, Clip Studio
  Paint, DaVinci Resolve (for panel tool patterns)
- Extraction: what rules are consistent across three or more products?

**What decision would have been made:** The reference would have produced
written rules before the first toolbar design was built:
- Tools that create objects are left-most in the toolbar
- Tools that modify existing objects are center
- View controls are right-most
- The most-used tools are always in the toolbar, never in a submenu
- Icon size at this type of tool: 20px with 8px padding

With these rules written, the toolbar question is answerable on the first pass.
The four revision cycles would not have occurred because there was no
standard to iterate toward. With the standard, the first design can be
evaluated against it and either passes or fails with a clear resolution.

**Confidence in counterfactual:** HIGH
Toolbar organization is well-documented. The pattern analysis is straightforward.
The rule extraction is achievable in one research session.

**Time cost of reference:** 3–4 hours.
**Time cost of shipping wrong:** 8 hours of revision, plus ongoing
user confusion about toolbar organization that persists in v2.0.1.

---

## Counterfactual 3: Dark Theme Calibration

**Decision that was made:** Dark theme calibrated on development machine
(single 1080p monitor, typical office conditions).

**Production cost:** User reports of insufficient contrast on high-brightness
displays. Known issue, not yet patched. Community trust cost ongoing.

**What reference was missing:** Layer 5 — Contextual Conditions.
Specifically: what display conditions do VFX/3D artists work in?

The specific reference to gather:
- Display survey: what monitors do 3D/VFX artists use? (Forums, community
  polls — this data exists)
- Color calibration standards: VFX artists frequently use color-calibrated
  displays at specific brightness levels
- Accessibility contrast standards: WCAG contrast ratios for dark themes
  on the range of brightness settings typical in the target environment

**What decision would have been made:** The reference would have established
a minimum contrast ratio that passes at the high end of the display brightness
range used by the target user. Rather than calibrating to my display, the
calibration would have used WCAG AA as the floor and a higher standard
(4.5:1 on a 400cd/m² display) as the design target.

The specific change: background would be #1A1A1A rather than #242424 (darker),
and primary text would be #E8E8E8 rather than #D0D0D0 (lighter). A 12%
change in both values that would have resolved the reported contrast issues
without changing the visual character of the theme.

**Confidence in counterfactual:** HIGH
The contrast issue is measurable. The fix is calculable. The reference
(display brightness survey + WCAG standards) is available.

**Time cost of reference:** 1–2 hours.
**Time cost of shipping wrong:** Ongoing user experience cost, future patch cycle.

---

## Counterfactual 4: PureRef Compatibility

**Decision that was made:** Kanvaz file format designed from scratch,
no PureRef import/export.

**Production cost:** User friction for PureRef migrators. The positioning
("PureRef alternative") creates an expectation of migration path that the
product does not deliver. This is a retention and adoption cost that is
difficult to quantify but real.

**What reference was missing:** Layer 1 — Function & Context.
Specifically: systematic PureRef workflow analysis.

The specific reference to gather:
- PureRef documentation and community resources: what does the power-user
  workflow actually look like?
- PureRef file format: is it documented? Is import/export feasible?
- PureRef user community discussions: what do users most want from a PureRef
  alternative that PureRef doesn't provide?

**What decision would have been made:** The research would have revealed
whether PureRef format import is feasible (it is, based on community reverse-engineering).
If yes: a PureRef import feature becomes a v1.0 priority, not a future roadmap item.
The positioning as "PureRef alternative" would have a concrete migration path.

Additionally: the PureRef workflow analysis would have produced a specific
list of PureRef capabilities to match before claiming "alternative" positioning.
Some features Kanvaz v2.0 is missing (right-click paste from clipboard in
specific edge cases, the Google Image Search integration) are PureRef
capabilities that the target user expects from a "PureRef alternative."

**Confidence in counterfactual:** MEDIUM
The PureRef format research may have concluded that import is more complex
than the community reverse-engineering suggests. The positioning question
(what does "alternative" require?) would definitely have been asked and
answered differently.

---

## Summary: Estimated Cost of Missing Reference

| Counterfactual | Reference time | Production cost avoided |
|---|---|---|
| Autosave pattern | 2–3 hours | 4–6 hours dev + ongoing trust |
| Toolbar rules | 3–4 hours | 8 hours revision + UX issues |
| Display calibration | 1–2 hours | Patch cycle + user experience |
| PureRef workflow | 4–6 hours | Adoption friction (hard to quantify) |
| **Total** | **10–15 hours** | **12–14 hours minimum + intangibles** |

The ROI case for 10–15 hours of Reference Engineering on this project
is a break-even on measurable time costs alone. The intangible costs
(shipped autosave bug, ongoing contrast issues, adoption friction) are
not quantified but are real.

---

## What This Case Study Proves About Reference Engineering

This case study supports the following specific RE claims:

**1. Technical failures are often reference failures in disguise.**
The autosave bug appeared to be an implementation error. The RE analysis
shows it was a specification error that would have been prevented by
Layer 6 (Behavior & Construction) reference. Implementation quality
cannot compensate for specification quality.

**2. Solo developers are the highest-risk RE case, not the lowest.**
Teams have design reviews, client feedback, and multiple perspectives
that provide some of the forcing functions that Reference Engineering
formalizes. Solo developers have none of these. Without the RE discipline,
every decision defaults to personal judgment — which is not wrong, but
is not informed by the breadth of reference that the target user's
actual use conditions require.

**3. Experiential knowledge of a competitor is not competitive analysis.**
Using PureRef is not the same as analyzing PureRef. The difference is
Layer 1 (Function & Context) reference: what does the target user's
PureRef workflow look like, not what does my PureRef workflow look like.

**4. Display calibration to the development machine is a universal failure mode.**
This case study is not unusual in this respect. It is the norm.
The RE Layer 5 (Contextual Conditions) requirement — gathering reference
for the actual conditions the product will be used in, not the developer's
conditions — addresses the most common UI calibration failure mode in
solo and small-team development.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
