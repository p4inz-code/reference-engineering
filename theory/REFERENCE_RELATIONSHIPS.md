# Reference Relationships

**Part of:** Reference Engineering Theory Layer
**Relates to:** Principle 5 — Relationships matter more than storage

References do not exist in isolation. The relationships between references
are first-class data in Reference Engineering — as important as the
references themselves, and more valuable than the storage system that holds them.

A reference system with strong relationship mapping is qualitatively different
from a reference system without it. The relationships tell you things that
no individual reference can tell you: what is confirmed, what is contradicted,
what is constrained, what is still missing.

---

## Why Relationships Matter

Consider two scenarios:

**Scenario A — No relationship mapping:**
Reference board contains 40 images organized by visual category. Practitioner
looks at them before making each decision. Each decision draws on whatever
feels most relevant at the moment of decision.

**Scenario B — Relationship-mapped references:**
Reference board contains 40 images organized by the decision each answers,
with relationship annotations. The practitioner knows that Reference 7
confirms Reference 3, that Reference 12 constrains what Reference 7 implies,
and that the gap between References 3 and 12 is unanswered and will become
a production question in the next phase.

Scenario B produces decisions of higher confidence, catches contradictions
before they become production conflicts, and identifies gaps before they
become production blocks. The 40 references are the same. The relationship
map is what makes them useful.

---

## The Five Relationship Types

### 1. Confirmation

**Definition:** Reference B confirms Reference A. Both sources agree on a
parameter or observation independently.

**Value:** Decisions derived from confirmed references carry higher confidence
than decisions from a single source. Confirmation reduces the risk that a
decision is based on an idiosyncratic property of one source.

**How to document:**
```
[REF-03] confirms [REF-07] on: concrete roughness range (0.85–0.95)
Both sources: Pripyat documentation (T1) and Metro Exodus art bible (T2)
Decision confidence: HIGH — cross-tier confirmation
```

**Minimum confirmation threshold:**
- Foundational decisions: 3 confirming sources
- Structural decisions: 2 confirming sources
- Detail decisions: 1 source acceptable, flag as unconfirmed

### 2. Constraint

**Definition:** Reference B constrains what Reference A implies. Reference A
suggests a range of possible decisions; Reference B narrows that range.

**Value:** Constraint relationships prevent decisions that would be valid
in the abstract but are incorrect for this specific subject given what
another reference establishes.

**Example:** Reference A (style analysis) implies bevels can be any width
between 1–5mm. Reference B (specific product in the same style) shows
bevels are always at the narrow end of this range. Reference B constrains
Reference A's implication to the 1–2mm range.

**How to document:**
```
[REF-12] constrains [REF-07]:
REF-07 implies bevel width 1–5mm (style analysis)
REF-12 constrains to 1–2mm (specific product in same style)
Applied decision: 1.5mm maximum bevel width
```

### 3. Gap

**Definition:** Reference A answers a question that reveals an adjacent
question that Reference B would need to answer — but Reference B has not
been gathered.

**Value:** Gap relationships are the mechanism by which Reference Engineering
finds the gaps that matter. They are more valuable than gaps identified
abstractly because they arise from actual reference work — from what the
gathered reference tells you is missing.

**Example:** Reference A establishes the external material properties of
a building. This reveals a gap: what happens to those materials at interior
surfaces where condensation is different? Reference B (interior material
documentation) has not been gathered.

**How to document:**
```
GAP identified from [REF-04]:
REF-04 answers: exterior concrete aging at 15 years
Gap revealed: interior concrete aging (different humidity, no UV)
Reference needed: interior documentation of same building type
Priority: HIGH — interior surfaces are visible through broken windows
Status: OPEN
```

### 4. Contradiction

**Definition:** Reference B contradicts Reference A. Both sources address
the same parameter but give different or incompatible values.

**Value:** Contradictions must be surfaced and resolved before the decision
that depends on them is made. An unresolved contradiction produces an
undocumented assumption disguised as a reference-backed decision.

**Resolution priority:**
1. Higher tier wins (Tier 1 over Tier 2, Tier 2 over Tier 3)
2. More specific wins (reference specific to the exact subject over reference to the general category)
3. More recent wins (for subjects that change over time)
4. If unresolvable by rule: document the contradiction and state the rationale for the choice made

**How to document:**
```
CONTRADICTION: [REF-08] vs [REF-11]
REF-08 (T2): roughness range 0.70–0.80 for aged steel
REF-11 (T1): roughness range 0.75–0.90 for aged steel (same material, measured)
Resolution: Tier 1 precedence — applied REF-11 range (0.75–0.90)
Note: REF-08 may reflect studio-calibrated values, not physical measurement
```

### 5. Temporal

**Definition:** Reference A and Reference B both address the same subject
but at different points in time. The temporal relationship affects which
reference is more applicable to current conditions.

**Value:** Temporal relationships prevent applying outdated reference to
subjects that have changed — technical standards that have been revised,
software behavior that has changed with an update, styles that have shifted.

**Not all references age at the same rate.** Physical material behavior
reference from 1990 is still valid for current concrete. UI design pattern
reference from 2015 may be obsolete. Know the staleness rate of your reference
category before assuming temporal order matters.

**How to document:**
```
TEMPORAL: [REF-06] (2018) vs [REF-14] (2024)
Both address: browser rendering behavior for CSS grid
Temporal precedence: REF-14 — more recent, reflects current browser support
REF-06 retained as: historical context for legacy support considerations
```

---

## Relationship Mapping in Practice

### Minimum Viable Relationship Map

For small projects or rapid reference sessions, a minimal relationship map
is sufficient. At minimum, document:

- **Confirmations** for all foundational decisions
- **Contradictions** for all cases where sources disagree (before deciding)
- **Gaps** revealed by the gathered references

Constraint and temporal relationships can be documented when they arise
rather than systematically mapped.

### Full Relationship Map

For large projects, long-running reference systems, or institutional
reference libraries, a full relationship map is valuable. This can be
maintained as:

- Annotation within the reference brief (inline relationship notes)
- A separate relationship register (table of all documented relationships)
- A visual map (nodes for references, edges for relationships — useful for
  complex systems with many inter-reference dependencies)

### Relationship Map Template

```
REFERENCE RELATIONSHIP REGISTER
Project: [name]
Last updated: [date]

[REF-ID] | [REF-ID] | RELATIONSHIP TYPE | PARAMETER | RESOLUTION/STATUS
---------|----------|-------------------|-----------|------------------
REF-03   | REF-07   | CONFIRMATION      | Roughness range | Confirmed: 0.85–0.95
REF-07   | REF-12   | CONSTRAINT        | Bevel width | Constrained to 1–2mm
REF-04   | [MISSING]| GAP               | Interior concrete | OPEN — HIGH priority
REF-08   | REF-11   | CONTRADICTION     | Steel roughness | Resolved: Tier 1 precedence
REF-06   | REF-14   | TEMPORAL          | CSS grid behavior | REF-14 current
```

---

## Relationships Across Projects

In a long-term reference library, relationships extend across projects.
A reference gathered for Project A may confirm, constrain, or contradict
a reference gathered for Project B. These cross-project relationships are
among the most valuable connections a long-term reference system builds.

They are also the connections most likely to be lost without deliberate
practice. Cross-project relationship mapping requires:
- Stable reference identifiers that persist across projects
- A shared relationship register maintained across the library
- Periodic audits to identify new cross-project relationships as the library grows

---

## What Relationship Mapping Prevents

| Failure Mode | How Relationships Prevent It |
|---|---|
| Style Drift | Constraint relationships lock governing rules against micro-decision creep |
| Single-Source Bias | Confirmation relationships require multiple sources before high-confidence decisions |
| Contextless Collection | Gap relationships make missing reference visible and actionable |
| Contradictory Decisions | Contradiction relationships surface conflicts before decisions are locked |
| Stale Reference Application | Temporal relationships flag which references have age-dependent credibility |

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
