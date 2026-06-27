# Case Study Format

A case study is a retroactive analysis of a real project through the
Reference Engineering lens. It differs from an example in direction:
examples move forward (brief → decisions → outcome). Case studies move
backward (outcome → analysis → what RE would have changed).

Case studies are the primary proof layer of Reference Engineering — they
demonstrate the framework against real projects with real outcomes,
not constructed demonstrations.

---

## What Makes a Valid Case Study

A valid Reference Engineering case study requires:

1. **A real project** — not constructed or hypothetical
2. **A known outcome** — the project was completed; results are observable
3. **Honest analysis** — failures and missed opportunities are documented,
   not hidden. A case study that only shows what went right is not useful.
4. **Access to the actual process** — the analyst must have direct knowledge
   of what reference work was (or wasn't) done. Inferring process from
   outcome alone produces speculation, not analysis.

The most valuable case studies are self-analyses of your own projects —
where you have full access to what actually happened.

---

## Case Study File Structure

```
case-studies/[project-name]/
├── README.md          — project context and what this case study demonstrates
├── 01_project.md      — what the project was, what was built, what the outcome was
├── 02_reference_audit.md  — what reference work was done (or not done)
├── 03_analysis.md     — RE framework analysis: which failure modes occurred,
│                          which Pyramid layers were missing, what gaps caused problems
└── 04_counterfactual.md  — what RE would have changed: specific decisions that
                            would have been different with better reference practice
```

---

## File 1: README.md Template

```markdown
# Case Study: [Project Name]

**Project type:** [what was built]
**Discipline:** [the primary field]
**Analyst:** [who is analyzing — first-person or credited third party]
**Date of project:** [when the project happened]
**Date of analysis:** [when this case study was written]
**Access level:** [first-person (I worked on this) / second-person (I know someone who did) / documented (public record)]

## Why This Project

[1–2 sentences: what makes this project an interesting case study for RE.
What failure mode or success does it demonstrate?]

## What This Case Study Shows

[The specific RE lessons this case study produces. Written before the
analysis so the reader knows what to look for.]
```

---

## File 2: 01_project.md Template

```markdown
# [Project] — Project Record

## What Was Built

[Description of the project: scope, scale, timeline, output. Be specific.
"A mobile app" is not specific. "A B2C iOS app for personal finance tracking,
12-week build, solo developer, shipped to App Store" is specific.]

## The Brief

[What the project was supposed to be. If the brief changed during production,
document both the original and final brief.]

## The Outcome

[What was actually delivered. Be honest — if it shipped late, say so.
If it shipped with known defects, say so. If it was never finished, say so.
The case study is only useful if the outcome is accurately recorded.]

## What Worked

[Specific things that went well in this project. Required — a case study
that only documents failures is not balanced and produces the wrong lessons.]

## What Failed or Was Harder Than It Should Have Been

[Specific failures, rework episodes, production blocks, or delays.
These are the raw material for the RE analysis in 03_analysis.md.]
```

---

## File 3: 02_reference_audit.md Template

```markdown
# [Project] — Reference Audit

A reference audit documents what reference work was actually done on this
project — not what should have been done, not what would ideally have
been done. What actually happened.

## What Reference Was Gathered

[List what reference materials were collected, how they were organized,
and whether they were annotated or just saved. Be honest — "saved to
a Figma board with no notes" is a valid answer.]

## How Reference Was Used

[Describe the actual reference practice: were references consulted
during production decisions? Were decisions made from the board or from
memory? Were gaps identified or did they surface as production problems?]

## What Reference Was Not Gathered (That In Retrospect Should Have Been)

[This is the core of the audit. What questions arose during production
that pre-production reference should have answered? What Pyramid layers
were completely absent?]

## Pyramid Layer Audit (Actual State)

| Layer | What Was Gathered | What Was Missing |
|---|---|---|
| 1 — Function & Context | [actual] | [missing] |
| 2 — Scale & Proportion | [actual] | [missing] |
| 3 — Stage Reference | [actual] | [missing] |
| 4 — Governing Rules | [actual] | [missing] |
| 5 — Contextual Conditions | [actual] | [missing] |
| 6 — Behavior & Construction | [actual] | [missing] |
| 7 — Precision Detail | [actual] | [missing] |
```

---

## File 4: 03_analysis.md Template

```markdown
# [Project] — Reference Engineering Analysis

## Failure Modes Identified

[Match the specific production failures from 01_project.md to the named
failure modes from core/REFERENCE_MISTAKES.md. Not every failure will
match a named mode — document those as new failure mode candidates.]

For each failure:
**[Failure Mode Name or Description]**
What happened: [the specific production event]
RE root cause: [which reference gap or practice failure caused it]
Which Pyramid layer was missing: [Layer N — name]
Which failure mode this matches: [Mistake NN from REFERENCE_MISTAKES.md, or "New: [description]"]

## Hierarchy Analysis

[Were the references that were used correctly tiered? Were T2 references
applied without translation? Were T3 references treated as T1?]

## Gap Patterns

[What gaps recurred — arose more than once or blocked production more than
once? These are the most valuable findings for future projects.]

## Unexpected Findings

[Anything the analysis revealed that wasn't in the initial hypothesis
about what went wrong. Required section — if the analysis produced no
surprises, it wasn't deep enough.]
```

---

## File 5: 04_counterfactual.md Template

```markdown
# [Project] — What Reference Engineering Would Have Changed

A counterfactual is not speculation — it is a specific, traceable argument
for how a specific decision would have been different with better reference practice.

Format for each counterfactual:

**Decision that was made:** [what was decided, with no reference support or poor reference]
**Production cost:** [what this decision cost when it was wrong — rework time, delay, quality impact]
**What reference was missing:** [specific reference that was absent — specific enough that someone could go gather it]
**What decision would have been made:** [the specific different decision, with the reference support stated]
**Confidence in counterfactual:** [HIGH / MEDIUM / LOW — how certain are you this reference would have changed the decision?]

## Summary: Estimated Cost of Missing Reference

[Total estimate — if these counterfactuals had been executed, what would
have been saved in time, rework, or quality?]

## What This Case Study Proves About Reference Engineering

[The specific RE claim that this case study supports. What can someone
conclude from this case study about the value of the framework?]
```

---

## Quality Bar for Case Studies

A case study is ready to publish when:

- [ ] The project outcome is honestly documented (including failures)
- [ ] The reference audit reflects what actually happened, not what should have happened
- [ ] At least three specific production failures are traced to specific reference gaps
- [ ] At least three specific counterfactuals are documented with MEDIUM or HIGH confidence
- [ ] The analyst has first-person or well-documented second-person access to the actual process
- [ ] No failure is attributed to reference practice when the actual cause was something else
  (budget, time, team, technology — not everything is a reference problem)

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
