# Kanvaz UI v2.0 — Reference Audit

*First-person account of what reference work was actually done.*

---

## What Reference Was Gathered

**PureRef:** I use PureRef regularly. My knowledge of it is experiential —
I know how I use it, not how VFX professionals in production use it.
I did not analyze PureRef's UI systematically. I did not document what
PureRef does well, what it does poorly, or what Kanvaz needs to do
differently to offer a genuine alternative.

**Screenshot collection:** I saved screenshots of a few canvas applications
I had seen (Miro, Milanote, one other I no longer remember) at the start
of the v2.0 design process. These were saved to a Figma file with no
annotations, no extracted rules, and no specific questions they were
gathered to answer. I looked at them at the start and did not consult
them during production.

**Discord user requests:** The v2.0 feature set was partially informed by
feature requests from the Northbyte Studios Discord. These represent user
stated preferences, not user workflow analysis. "I want autosave" is
not the same as "here is how autosave should work in this specific context."

**Nothing else.** That is the complete reference audit. For a UI design
project with a specific competitive position and a specific target user,
the reference gathered was: experiential knowledge of one competitor,
unannotated screenshots of three products, and user feature requests.

---

## How Reference Was Used

The screenshot collection was consulted once (at the start of the design
process) and not again during production. Every subsequent design decision
was made from my own judgment, iterative visual testing, and responses
to "this doesn't feel right" feedback from my own use of the application.

The Discord feature requests were used to prioritize the feature list.
They were not used to understand the workflow those features needed to fit into.

All production design decisions were, in Reference Engineering terms,
undocumented assumptions.

---

## What Reference Was Not Gathered

**Layer 1 — Who is the actual user and what is their actual workflow?**
I assumed the user was a 3D/VFX artist who works like I work. I am a
student developer who uses reference boards differently from a production
artist at a studio with a specific pipeline and a specific set of software
integrations. The actual target user's workflow was never researched.

**Layer 1 — What does PureRef's user actually use PureRef for?**
PureRef has a specific power-user workflow that its community has developed.
What features are essential to that workflow? What does PureRef do that
cannot be replicated without understanding the workflow? I never asked these
questions with reference to answer them.

**Layer 4 — What are the visual rules for this application category?**
"Cleaner and more professional" is not a visual rule. What specific
parameters define the visual register of professional creative tools
in this category? What do the best-regarded tools in this space do
consistently? I never extracted written rules from the competitor landscape.

**Layer 5 — What display conditions does the target user actually work in?**
VFX and 3D artists typically work with color-calibrated displays, often
multiple monitors, in varied lighting conditions (dark rooms for color
grading, normal office lighting for general work). My development machine
(i9/RTX 4060, single 1080p monitor) is not representative of this user's
display environment. I calibrated the UI to my display and shipped it
to a different display environment.

**Layer 6 — How does canvas application state behave under autosave conditions?**
Autosave in a canvas application is a state management problem with
well-documented failure modes. I did not research how other canvas
applications implement autosave — specifically how they handle the
conflict between autosave state and user-saved state. This gap directly
produced the autosave bug that shipped in v2.0.0.

---

## Pyramid Layer Audit (Actual State)

| Layer | What Was Gathered | What Was Missing |
|---|---|---|
| 1 — Function & Context | Experiential knowledge of one competitor | Systematic user workflow analysis, competitor workflow analysis |
| 2 — Scale & Proportion | None explicitly | UI component sizing standards for this application type |
| 3 — Stage Reference | None — no stage structure used | Stage-appropriate reference for wireframe / visual design / implementation |
| 4 — Governing Rules | None — no written rules | Visual rules for professional creative tool UI |
| 5 — Contextual Conditions | None — calibrated to one display | Display range for target users, ambient condition range |
| 6 — Behavior & Construction | None for autosave | Autosave state management patterns, canvas application state behavior |
| 7 — Precision Detail | Some — icon set, color fine-tuning | Not a gap at this stage |

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
