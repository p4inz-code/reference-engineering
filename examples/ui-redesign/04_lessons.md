# UI Redesign — Lessons

**Brief final version:** 1.1
**Decisions documented:** 13 primary, 4 deferred, 3 blocked
**Reference items used:** 14 (7 primary tier, 5 secondary, 2 tertiary)
**Reference items gathered and excluded:** 3

---

## What Reference Engineering Prevented

**Premature visual style decisions**
Without the brief structure, the first instinct would have been to gather
visual inspiration (Dribbble, Behance) and start making layout decisions
from aesthetic preference. The Layer 1 questions forced the user task analysis
first — which directly changed the layout (session resume vs. forced home,
inline drill-down vs. slide-in).

**Green/red debate**
In many UI projects, there is a stakeholder request to use brand colors
for positive/negative data (e.g., "our brand is orange — can we use orange
for gains?"). The reference work establishes this as a primary-tier industry
convention with user error implications. That conversation is resolved before
it happens.

**Slide-in panel pattern adoption**
The Robinhood slide-in pattern is visually clean and popular on Dribbble.
Without explicit reference analysis including the "does this transfer to
our use case" evaluation, it would have been a natural default. The analysis
caught that it breaks the comparison workflow that is central to our Layer 1 user task.

---

## What Reference Engineering Could Not Prevent

**Gap 01 (primary user task data model)** required stakeholder/product input,
not reference work. Reference Engineering correctly identified the gap and
flagged it as critical. Resolving it required a conversation that reference
work cannot replace.

**Gap 04 (light/dark mode priority)** required client data. Same pattern.
Reference Engineering identified the assumption and its risk level. It could
not provide the answer.

---

## What to Do Differently

**Gather Layer 5 (display context) earlier**
The viewport and display context reference was gathered after the information
architecture reference. In practice, display context constraints (minimum
viewport, ambient lighting) should inform information density decisions
at the start, not be filled in after. Next time: Layer 5 before Layer 2.

**Establish framework constraints (Layer 6) in the brief, not post-analysis**
Layer 6 was left as an open gap. For UI/UX projects specifically, the
framework/component library constraint is not a "nice to know" — it
directly constrains what is buildable. It should be a required input
before wireframes begin, not a parallel track.

**Three secondary sources is the minimum for style rule extraction**
In this example, "authoritative vs. flashy" rules were extracted from four
sources (Bloomberg, Refinitiv, FactSet, Morningstar). The consistency across
all four gave high confidence. Had we used only one or two, the rules would
have been idiosyncratic to those specific products. Three is the minimum —
four or more is better for contested style parameters.

---

## Transferable Lessons

1. Layer 1 questions (function) should always precede visual reference gathering.
   The layout decisions in this example were directly changed by Layer 1 findings.

2. The "what this style NEVER does" list is as useful as the positive style rules.
   Negative constraints are faster to check than positive rules.

3. Excluding reference items explicitly (with reasoning) is as important as
   including them. The crypto trading platform exclusion prevented a specific
   wrong-register risk.

4. Hierarchy tier tracking is most valuable for contested decisions. The
   green/red convention is primary tier — end of discussion. The light mode
   assumption is tertiary tier — flag and verify. The tier label tells you
   how much to fight for the decision.

---

## Brief Status at Close of Pre-Production

| Layer | Status |
|---|---|
| 1 — Function & Context | ✅ Complete |
| 2 — Scale & Proportion | ~ Partial (viewport not confirmed) |
| 3 — Production Stage | ✅ Complete for wireframe stage |
| 4 — Style Rules | ✅ Complete |
| 5 — Display Context | ~ Partial (light/dark not confirmed) |
| 6 — Framework Behavior | ✗ Open gap |
| 7 — Hero Detail | ✗ Deferred (correct — not needed at this stage) |

**Brief v2 triggers:** Gap 01 and Gap 03 resolution. Mockup stage start.

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
