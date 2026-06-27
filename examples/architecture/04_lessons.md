# Architecture — Lessons

---

## What Reference Engineering Prevented

**The concrete color match attempt**
Without explicit research into new vs old concrete behavior, the natural
instinct is to specify "concrete to match existing" and assume this is
achievable. It is not. New concrete will not match 60-year-old weathered
concrete, and specifying it as if it will produces an embarrassing result
that appears to be a failed attempt at matching rather than a deliberate
design decision. The materials science reference (T1) converted this from
an assumption into a documented decision: the color difference is the point,
not a problem to solve.

**The approach selection problem**
Three approaches to new/old legibility exist (contrast, complement,
continuation). Without precedent research, the default is usually approach A
(contrast — "make it clearly different") because it is the easiest to argue.
The precedent analysis showed that approach B (complement) is more appropriate
for this building type and brief — because full contrast risks reading as
an apology for the existing concrete, which is the opposite of the brief's
intent to "celebrate" the brutalist character.

**The solar angle miscalculation risk**
Shading device depth is almost always underspecified from intuition.
Designers tend to specify shading that looks right rather than shading
that works at the actual solar angles for the actual latitude. At this
latitude, the required horizontal projection (1.9m) is larger than most
intuition would suggest — because the summer sun angle (58°) at temperate
latitudes is lower than the tropical-climate examples that dominate
architectural photography. The solar angle calculation produced a different
number than intuition would have.

**The datum blindness**
The 900mm raised floor datum is the most important element of the existing
building. It is also the cause of the entrance problem the community
identified. Without explicit analysis of the existing building's organizational
principles, the datum might not have been identified as the primary reference
dimension for the extension. Working from photographs rather than analysis
would have produced an extension that responded to the building's surface
rather than its organizational logic.

---

## Architecture's Specific Reference Challenge

Architecture manages reference from more simultaneous domains than almost
any other discipline. In this project, active reference domains included:

- Historical (what this building was designed to be)
- Technical/structural (how this building actually works)
- Material/physical (how concrete ages, performs thermally, responds acoustically)
- Regulatory (what planning authority and heritage designation require)
- Community/cultural (what this building means to the people who use it)
- Environmental (climate, solar, acoustic)
- Precedent/typological (how others have solved this problem)

Each domain has its own sources, its own tier structure, and its own
update frequency. Regulatory reference changes when planning policy changes.
Material science reference is stable. Community relationship reference
is specific to this project and cannot transfer.

The Reference Engineering discipline's requirement that all Pyramid layers
be covered prevents the common failure of heavy coverage in one domain
(usually visual/aesthetic) and light coverage in others (usually technical
and regulatory) — which produces work that looks right and performs wrong.

---

## Cross-Reference Findings

**Community consultation (T1) confirmed the architectural historian's analysis (T1)** on the entrance problem. Two independent primary sources identified the same failure — the datum line overwhelming the entrance — from different perspectives (community experience and architectural analysis). This cross-source confirmation gave D04 (the courtyard decision) CONFIRMED confidence.

**Climate data (T1) produced a different answer than visual reference would have.** The required brise-soleil depth (1.9m) is larger than the shading devices visible in published precedent images from similar projects. The published images are drawn at a scale where the depth difference is not visible. Only the climate calculation produced the correct number.

---

## Transferable Lessons

**1. In architecture, the existing building is always the primary reference.** No amount of precedent research is more important than thorough analysis of the specific building being worked on. The specific building's datum, grid, structural system, material rules, and organizational logic are all T1 primary reference — they govern the project more than any external precedent.

**2. Calculate, don't look.** Solar angles, acoustic isolation requirements, U-values, and structural loads are all calculable from T1 data. Using visual reference to estimate these values produces wrong answers. Reference Engineering's requirement for Layer 5 (Contextual Conditions) and Layer 6 (Behavior & Construction) reference forces the calculation pass that visual reference skips.

**3. Community consultation is primary reference.** The community's relationship to a building — their experience of its failures and their attachment to its qualities — is T1 data that no external source can provide. It belongs in the brief alongside structural surveys, not as a soft consultation note at the end.

**4. The NEVER list is a planning document, not just a design constraint.** In architecture, "what this building never does" becomes a checklist item in the design review. Every scheme development check includes a pass against the NEVER list.

---

## Pyramid Layer Status at Schematic Close

| Layer | Status | Notes |
|---|---|---|
| 1 — Function & Context | ✅ Complete | Program, community, existing building |
| 2 — Scale & Proportion | ✅ Complete | Datum, bay, mass, height |
| 3 — Stage Reference | ✅ Complete | Schematic precedents, approach selection |
| 4 — Governing Rules | ✅ Complete | Specific rules, NEVER list |
| 5 — Contextual Conditions | ✅ Complete | Climate, solar, acoustic |
| 6 — Behavior & Construction | ✅ Complete | Concrete condition, thermal, new/old |
| 7 — Precision Detail | ✗ Deferred | DD stage — joint details, specifications |

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
