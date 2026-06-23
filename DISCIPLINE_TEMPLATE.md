# Discipline Template

Use this file as the exact structure for any new discipline section.
Copy the five file templates below into `disciplines/[your-discipline]/`.
Do not rename the files. Do not change the section headers.
Fill in every section. PR will be returned if any section is empty or marked TODO.

---

## File 1: README.md

```markdown
# Reference Engineering — [Discipline Name]

> One sentence: what this discipline is and who it's for.

**Discipline:** [Name]
**Contributed by:** [Your Name / Handle]
**Last updated:** [YYYY-MM-DD]

---

## Who This Is For

[2–3 sentences describing the specific practitioner this section serves.
Be specific — not "anyone who does [discipline]" but the type of work
and production context this guide is optimized for.]

---

## What Reference Engineering Solves in [Discipline]

[2–3 sentences describing the most common reference failure mode in this
discipline and what the methodology prevents.]

---

## The Pre-Production Questions This Discipline Must Answer

[List 5–10 specific production questions that [discipline] practitioners
need reference to answer before production starts. These should be the
actual questions, not categories. Example: "What is the viewport hierarchy
of this UI — which elements are primary, secondary, tertiary?" not just
"visual hierarchy".]

- [ ] [Question 1]
- [ ] [Question 2]
- [ ] [Question 3]
- [ ] [Question 4]
- [ ] [Question 5]

---

## Pyramid Layer Map for [Discipline]

| Pyramid Layer | What It Means in [Discipline] |
|---|---|
| Layer 1 — Function & Context | [what Layer 1 means specifically for this discipline] |
| Layer 2 — Scale & Proportion | [what Layer 2 means specifically for this discipline] |
| Layer 3 — Production Stage | [what stages exist in this discipline] |
| Layer 4 — Style Rules | [what style rule extraction looks like in this discipline] |
| Layer 5 — Lighting Context | [equivalent for this discipline — may not be lighting literally] |
| Layer 6 — Material & Surface | [equivalent for this discipline] |
| Layer 7 — Hero Detail | [what hero detail means in this discipline] |

---

## Contents

| File | What's in it |
|---|---|
| `REFERENCE_GUIDE.md` | Full methodology for [discipline] |
| `mistakes.md` | [N] discipline-specific failure modes |
| `checklist.md` | Printable pre-production checklist |
| `sources.md` | Best reference sources for [discipline] |

---

## Related

- [Link to relevant ai-skills/ pack if one exists]
- [Link to related discipline if applicable]

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
```

---

## File 2: REFERENCE_GUIDE.md

```markdown
# [Discipline] — Reference Engineering Guide

Full methodology for gathering, analyzing, and organizing reference
for [discipline] pre-production.

**Contributed by:** [Your Name / Handle]
**Last updated:** [YYYY-MM-DD]

---

## Layer 1 — Function & Context

**What to find:**
[3–5 specific types of reference to gather for function and context
in this discipline. Not generic — specific to what this discipline builds.]

**Discipline-specific questions:**
- [Question this discipline needs Layer 1 to answer]
- [Question this discipline needs Layer 1 to answer]
- [Question this discipline needs Layer 1 to answer]

**Where to look:** [2–3 specific sources from sources.md]

---

## Layer 2 — Scale & Proportion

**What to find:**
[3–5 specific types of scale and proportion reference for this discipline.]

**Discipline-specific questions:**
- [Question this discipline needs Layer 2 to answer]
- [Question this discipline needs Layer 2 to answer]

**Where to look:** [2–3 specific sources from sources.md]

---

## Layer 3 — Production Stage Reference

**Stages in [discipline]:**

| Stage | What you're building | Reference needed |
|---|---|---|
| [Stage 1 name] | [what this stage produces] | [specific reference type] |
| [Stage 2 name] | [what this stage produces] | [specific reference type] |
| [Stage 3 name] | [what this stage produces] | [specific reference type] |
| [Stage 4 name] | [what this stage produces] | [specific reference type] |

---

## Layer 4 — Style Rules

**Extractable parameters for [discipline]:**

[List 5–8 specific style parameters that can be extracted from reference
in this discipline. These should be concrete and measurable where possible,
not vague vibes.]

**How to extract them:**
[Brief methodology for how a practitioner in this discipline should extract
and document style rules from their reference. What to measure, what to write down.]

---

## Layer 5 — [Lighting Context equivalent for this discipline]

[Name this layer what it actually means in this discipline. For web development
this might be "Rendering Context." For security research this might be
"Environment Constraints." For music production this might be "Listening Context."]

**What to find:**
[Specific reference types for this layer in this discipline.]

---

## Layer 6 — [Material & Surface equivalent for this discipline]

[Name this layer what it means in this discipline.]

**What to find:**
[Specific reference types for this layer in this discipline.]

---

## Layer 7 — Hero Detail

**What hero detail means in [discipline]:**
[Translate Layer 7 to the specific high-resolution, fine-craft reference
this discipline needs in late production.]

**What to find:**
[Specific reference types for Layer 7 in this discipline.]

---

## The [Discipline] Reference Brief

[Provide a structured template or set of questions that a practitioner
in this discipline should fill out for each project. This is the discipline's
version of a reference brief. Should take 30–60 minutes to complete.]

---

## When to Re-Run Reference Work

[List the specific triggers in this discipline that should prompt a brief
audit and reference update. Be specific to this discipline's workflow.]

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
```

---

## File 3: mistakes.md

```markdown
# [Discipline] — Reference Engineering Mistakes

[5–10 discipline-specific failure modes. Follow the card format exactly.
Each mistake needs: a name, a quote, a symptom, a cause, a fix, and a
production cost. Collapsible detail section is optional but encouraged.]

---

## MISTAKE 01 — [Name]

> *"[The thing a practitioner says when they have this problem]"*

**Symptom:** [What the practitioner observes. Specific, not vague.]

**Cause:** [Why this happens. What pre-production decision or non-decision caused it.]

**Fix:** [Specific, actionable fix. What to do, not what to avoid.]

**Production cost:** [What it costs in time and rework when not caught early.]

<details>
<summary>Full explanation</summary>

[2–4 paragraphs explaining the mistake in depth. Why it happens. Why it's
a discipline-specific problem. What the full cost looks like. Optional but
recommended for the top 3–5 mistakes.]

</details>

---

[Repeat for each mistake, numbered 01 through N]

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
```

---

## File 4: checklist.md

```markdown
# [Discipline] — Reference Engineering Checklist

Printable pre-production checklist for [discipline].
Run before production. Run again at each major milestone.

Mark each item: ✓ Complete / ~ Partial / ✗ Missing / N/A Not applicable

---

## Section 1 — Function & Context

- [ ] [Specific checklist item for this discipline]
- [ ] [Specific checklist item for this discipline]
- [ ] [Specific checklist item for this discipline]

---

## Section 2 — Scale & Proportion

[Continue for each Pyramid layer, adapted to this discipline's vocabulary]

---

## [Discipline]-Specific Checks

[Add checks specific to this discipline that don't map cleanly to
universal Pyramid layers. Examples: for 3D art — topology and rigging
requirements. For web dev — accessibility and browser support. For
security research — scope confirmation.]

---

## Board Health Check (Run at Each Milestone)

- [ ] [Milestone-appropriate check]
- [ ] [Milestone-appropriate check]
- [ ] [Milestone-appropriate check]

---

## Common Gaps for [Discipline]

[3–5 most commonly missing layers or checks for this discipline,
based on your experience.]

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
```

---

## File 5: sources.md

```markdown
# [Discipline] — Reference Sources

Best sources for Reference Engineering in [discipline].
Organized by Pyramid layer.

Last updated: [YYYY-MM-DD]
Contributed by: [Your Name / Handle]

---

## Layer 1 — Function & Context

[Source name] — FREE / FREEMIUM / PAID
[One sentence: what it provides that other sources don't]
[URL if applicable]

---

[Continue for each relevant Pyramid layer]

---

## [Discipline]-Specific Source Categories

[Any source categories specific to this discipline that don't map to
universal Pyramid layers.]

---

## Tools

[Software, apps, or services specifically useful for reference gathering
in this discipline.]

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
```

---

## PR Checklist for New Discipline Sections

Before opening a PR, confirm:

- [ ] All 5 files present with exact filenames (README.md, REFERENCE_GUIDE.md, mistakes.md, checklist.md, sources.md)
- [ ] No file has empty sections or TODO placeholders
- [ ] mistakes.md has minimum 5 entries in the card format
- [ ] checklist.md has items for every Pyramid layer
- [ ] sources.md has minimum 5 sources with layer annotations
- [ ] README.md pyramid layer map is filled in for every layer
- [ ] Authorship credit (Your Name / Handle) appears in README.md
- [ ] Attribution footer appears in all 5 files
- [ ] PR description includes one paragraph on your domain expertise for this discipline

---

*Northbyte Studios — Atharva Patil — 2026*
