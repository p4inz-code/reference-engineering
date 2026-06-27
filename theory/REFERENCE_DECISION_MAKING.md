# Reference Decision Making

**Part of:** Reference Engineering Theory Layer
**Relates to:** Core definition — references applied to improve decision quality

Reference Engineering exists because references are collected to inform
decisions. The connection between reference practice and decision quality
is the discipline's core claim. This document makes that connection explicit.

---

## The Central Claim

Better reference practice produces better decisions.

This is not a vague assertion. It has a specific mechanism:

1. A decision made from a higher-tier reference is more likely to be correct
   than one made from a lower-tier reference or from memory.
2. A decision made from multiple confirmed references is more likely to be
   correct than one made from a single source.
3. A decision made after gap analysis is less likely to be blocked by an
   unanswered question than one made without it.
4. A decision that can be traced to a reference can be audited, challenged,
   and revised with evidence — a decision made from memory cannot.

Reference Engineering improves decisions not by replacing judgment but by
giving judgment better material to work from.

---

## Reference-Backed Decisions vs Undocumented Assumptions

Every production decision is either reference-backed or an undocumented assumption.

### Reference-Backed Decision

A decision is reference-backed when:
- It was made from reference of a known tier
- The reference's tier and any translation applied are documented
- The decision was checked for consistency with the governing rules extracted
  from the reference set
- The decision was audited against other active references for contradiction

A reference-backed decision can be:
- **Audited:** Is this decision consistent with the reference it came from?
- **Challenged:** Is this the right reference to be making this decision from?
- **Revised:** If better reference is found, the decision can be revisited with evidence
- **Transferred:** A new team member can understand why the decision was made

### Undocumented Assumption

A decision is an undocumented assumption when:
- It was made from memory, preference, or intuition without reference support
- No reference is cited for the decision
- The reasoning is not documented

An undocumented assumption cannot be audited, cannot be challenged with
evidence (because there is no evidence), and cannot be transferred — when
the practitioner who made it is no longer available, the reasoning is gone.

### The Goal

Reference Engineering does not eliminate undocumented assumptions. All
production involves some — there are always decisions that must be made
faster than reference can be gathered, or where reference does not exist.

The goal is:
1. Minimize undocumented assumptions in decisions where reference is available
2. Make explicit which decisions are undocumented assumptions so they can be
   flagged as higher-risk and revisited when time or information allows
3. Convert undocumented assumptions to reference-backed decisions over time
   as the reference system matures

---

## Decision Confidence Levels

Decision confidence is a function of the reference support behind a decision.
Reference Engineering defines four confidence levels:

```
LEVEL 1 — CONFIRMED
  Multiple Tier 1 sources agree.
  Cross-tier confirmation (T1 + T2 or T2 + T2 from independent sources).
  Decision: lock it. Revisit only if new T1 reference contradicts.

LEVEL 2 — SUPPORTED
  Single Tier 1 source, or two Tier 2 sources in agreement.
  Translation step documented for T2 sources.
  Decision: proceed. Flag for confirmation if additional reference is found.

LEVEL 3 — PROVISIONAL
  Single Tier 2 or Tier 3 source.
  Translation documented but not cross-checked.
  Decision: proceed but mark as provisional. Validate against production results.

LEVEL 4 — ASSUMED
  No reference support. Made from memory, preference, or intuition.
  Decision: document as assumption. Seek reference to confirm or revise.
  Flag as higher-risk in project risk register.
```

---

## The Decision Trace

Every significant production decision should have a decision trace: a
brief record of what reference supported it, at what confidence level,
and what alternatives were considered and rejected.

### Decision Trace Format

```
DECISION: [what was decided]
Reference: [REF-ID] — [brief description]
Tier: [1/2/3]
Confidence: [CONFIRMED / SUPPORTED / PROVISIONAL / ASSUMED]
Translation (if T2/T3): [what was translated from the analog]
Alternatives considered: [what else was considered and why rejected]
Constraint relationships: [which other references constrain this decision]
Review trigger: [what would cause this decision to be revisited]
```

### Lightweight Decision Trace

For small projects or lower-stakes decisions, a lightweight trace is acceptable:

```
D-01: Bevel width = 1.5mm
  From: REF-12 (T1), confirmed by REF-07 (T2)
  Confidence: CONFIRMED
```

### When to Document

Not every decision requires a decision trace. The discipline of deciding
which decisions to document is itself a Reference Engineering skill.

Document when:
- The decision is foundational (affects many downstream decisions)
- The decision will be challenged (by client, by team member, by your future self)
- The decision was made from Tier 3 or assumed (higher risk)
- The decision affects a significant time investment (reworking it is expensive)

Do not document when:
- The decision is easily reversible with no downstream cost
- The decision is obvious from the reference (no reasoning to preserve)
- The project is so small that documentation overhead exceeds value

---

## Reference Engineering and Judgment

Reference Engineering improves the material that judgment works from.
It does not replace judgment.

A practitioner with excellent reference and poor judgment will make poor
decisions. A practitioner with excellent judgment and no reference will
make decisions constrained by what they already know.

The practitioner with excellent reference *and* excellent judgment makes
the best decisions — because their judgment is operating on better material.

This is why Reference Engineering is a discipline, not a system. A system
could theoretically operate without judgment. A discipline develops
judgment through practice. The experienced Reference Engineer does not
just gather better reference — they develop better judgment about what
reference to gather, what it means, and how to apply it.

---

## Common Decision-Making Failures Traced to Reference Practice

### Failure: "It looked right"

**What happened:** Decision made from visual intuition, not reference.
**Reference Engineering diagnosis:** Undocumented assumption. The practitioner
is working from aesthetic memory rather than extracted governing rules.
**Fix:** Extract governing rules (Pyramid Layer 4) before making style decisions.
Write them down. Make decisions from the written rules, not from looking at
the reference images and feeling.

### Failure: "The reference said to do it this way"

**What happened:** Decision made from a single source applied directly
without tier assessment or translation.
**Reference Engineering diagnosis:** Single-source application, tier not assessed.
If the source was Tier 2 or 3, the decision may be applying properties of
the analog that don't transfer to the subject.
**Fix:** Assign tier before applying. Document any translation. Cross-check
with a second source before locking foundational decisions.

### Failure: "We didn't know we needed that"

**What happened:** A production question arose mid-production that pre-production
reference didn't anticipate.
**Reference Engineering diagnosis:** Gap audit was not run, or was run
insufficiently. The gap was present in the reference set but not identified.
**Fix:** Run a gap audit after every reference session, not just at the end
of pre-production. Gap identification requires actively asking "what question
does this reference reveal that I haven't answered yet?" — not just reviewing
what has been gathered.

### Failure: "Everyone thought someone else had figured that out"

**What happened:** A decision was made by assumption in a team context.
Everyone assumed the decision had reference support. It did not.
**Reference Engineering diagnosis:** Undocumented assumption mistaken for
reference-backed decision in a team handoff.
**Fix:** Decision traces. When a decision is handed off between team members,
the reference support must be documented or the decision must be flagged
as an assumption that the recipient needs to verify.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
