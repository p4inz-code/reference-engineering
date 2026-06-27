# Reference Hierarchy

**Part of:** Reference Engineering Theory Layer
**Relates to:** Principle 4 — Reference has a hierarchy

The Reference Hierarchy is the credibility model of Reference Engineering.
It defines three tiers of reference authority and governs how decisions
derived from references should be weighted, documented, and validated.

---

## The Three Tiers

```
┌─────────────────────────────────────────────────────────┐
│  TIER 1 — PRIMARY                                       │
│  Direct documentation of the exact subject              │
│  Highest credibility · Apply without translation        │
│  Validation: none required                              │
├─────────────────────────────────────────────────────────┤
│  TIER 2 — SECONDARY                                     │
│  Close analog sharing significant properties            │
│  High credibility for extractable principles            │
│  Validation: explicit translation required              │
├─────────────────────────────────────────────────────────┤
│  TIER 3 — TERTIARY                                      │
│  Distant analog · Extracted principle                   │
│  Moderate credibility · Domain knowledge required       │
│  Validation: confirm against production results         │
└─────────────────────────────────────────────────────────┘
```

---

## Tier 1 — Primary Reference

### Definition

Primary reference is direct documentation of the exact subject being produced.
Photographs, technical specifications, engineering drawings, footage, or
measurements of the specific thing.

### Properties

- **Credibility:** Highest. No translation step required.
- **Availability:** Lowest. For fictional, speculative, or novel subjects,
  primary reference is often unavailable.
- **Application:** Apply directly to decisions without intermediate steps.
- **Documentation:** Note the source, date, and what decision it informs.
  No translation note required.

### Examples by Domain

| Domain | Example of Primary Reference |
|---|---|
| 3D Art | Photograph of the exact prop being modeled |
| UI/UX | Usability test recordings of the exact user task being designed |
| Architecture | Survey drawings of the existing building being renovated |
| Game Dev | Play recordings of the exact mechanic being referenced |
| Security Research | Direct enumeration of the specific target system |
| Brand Design | Brand guidelines document from the exact client brand |

### When Primary Reference Does Not Exist

For fictional subjects (a sci-fi weapon that has never existed), speculative
subjects (a building type not yet built), or novel subjects (a new product
category), primary reference is unavailable. This does not stall Reference
Engineering — it triggers the secondary reference process.

---

## Tier 2 — Secondary Reference

### Definition

Secondary reference is close analog material — things that share significant
properties with the subject but are not identical. A secondary reference
informs decisions about the subject by analogy. It requires an explicit
translation step: identifying what transfers and what does not.

### Properties

- **Credibility:** High for transferable principles. Translation is mandatory.
- **Availability:** High. Most subjects have identifiable close analogs.
- **Application:** Extract the transferable principle. Document the translation.
  Flag what was translated so downstream decisions can be reviewed if the
  translation is challenged.
- **Documentation:** Note the source, the analog relationship, what transfers,
  and what does not.

### The Translation Step

The translation step is what distinguishes professional secondary reference
use from amateur secondary reference use. Amateur: look at the analog, apply
what looks right. Professional: explicitly state what property of the analog
applies to the subject and why, and what property does not apply and why.

Translation documentation format:

```
Source: [reference source]
Analog relationship: [how is this similar to the subject?]
Transfers: [what specific property can be applied directly?]
Does not transfer: [what is specific to the analog and not the subject?]
Translation applied: [what decision was made using the transferred principle?]
```

### Examples by Domain

| Domain | Subject | Secondary Reference | What Transfers |
|---|---|---|---|
| 3D Art | Sci-fi energy pistol | Real handgun mechanisms | Grip proportion, trigger guard placement, weight distribution logic |
| UI/UX | B2B analytics dashboard | Bloomberg Terminal | Information density standards, color conventions for financial data |
| Architecture | Contemporary library | Precedent libraries from same climate | Daylighting strategy, structural bay logic |
| Game Dev | Alien movement system | Insect locomotion footage | Weight shift patterns, limb sequencing |
| Security Research | New web application | Similar applications in same stack | Common vulnerability classes, authentication patterns |

---

## Tier 3 — Tertiary Reference

### Definition

Tertiary reference is extracted principle from a distant analog. It does not
document the subject or a close analog — it captures a principle from a
category that shares an underlying rule with the subject.

### Properties

- **Credibility:** Moderate. Requires domain knowledge to apply correctly.
- **Availability:** Highest. Principles can often be found when specific
  reference is unavailable.
- **Application:** Identify the underlying principle. Verify it applies to
  the subject's category. Apply provisionally. Validate against production results.
- **Documentation:** Note the source, the distant analog, the principle
  extracted, and flag for production validation.

### When to Use Tertiary Reference

Tertiary reference is the practitioner's tool of last resort — used when
primary and secondary reference are unavailable or insufficient. It requires
enough domain knowledge to recognize which principles transfer across
category boundaries and which do not. Using tertiary reference without
this knowledge produces plausible-sounding but incorrect decisions.

### Examples

| Extracted Principle | Source Category | Applied to |
|---|---|---|
| "Interfaces that reduce cognitive load use progressive disclosure" | Cognitive psychology | Dashboard design for complex data |
| "Structural members in tension can be thinner than those in compression" | Structural engineering | Visual design of UI layout hierarchy |
| "Camouflage works by breaking silhouette, not by matching texture" | Military design | Game environment visual break-up |
| "Older materials show wear at points of contact and friction first" | Materials science | Aging any surface in 3D art |
| "Systems under stress fail at the point of highest constraint" | Systems engineering | Security vulnerability assessment |

---

## Tier Assignment in Practice

### Tier Is Decision-Relative

The tier of a reference is not fixed. It depends on what decision it is
being used to inform. A technical drawing of a real building is:

- **Primary** when making decisions about that specific building's appearance
- **Secondary** when making decisions about similar buildings of the same era
- **Tertiary** when making decisions about the general principles of how
  masonry construction looks under a certain weathering condition

Always assign tier relative to the specific decision, not the reference in isolation.

### Tier Conflicts

When two references of different tiers disagree, higher tier takes precedence
as a default. But document the conflict:

```
Conflict: [Reference A] (Tier 1) implies X. [Reference B] (Tier 2) implies Y.
Resolution: Tier 1 precedence — applied X.
Note: If X proves incorrect in production, revisit Reference B's implication.
```

When two Tier 1 references disagree, the conflict cannot be resolved by
tier alone. Resolve by recency (more current wins), specificity (more
specific to the subject wins), or credibility of source (primary source
over secondary reporting). Document the resolution rationale.

### Minimum Source Requirements

| Decision weight | Minimum tier | Minimum sources |
|---|---|---|
| Foundational (affects all downstream decisions) | Tier 1 or 2 | 3 sources |
| Structural (affects a major section) | Tier 1, 2, or 3 | 2 sources |
| Detail (affects a single element) | Any tier | 1 source |

Decisions made from a single Tier 3 source should always be flagged as
provisional until validated in production.

---

## The Missing Primary Problem

### When Primary Reference Does Not Exist

For fictional, speculative, or novel subjects, primary reference is often
unavailable. This is one of the most common situations Reference Engineering
must handle — and the most common point at which practitioners stall.

The professional response is not to wait for primary reference that will
never exist. It is to engineer answers systematically from the tiers that
are available.

### The Missing Primary Protocol

1. **Accept the gap.** Primary reference does not exist for this subject.
   This is not a failure — it is a condition. Document it.

2. **Identify the closest secondary analogs.** What exists that shares the
   most significant properties with the subject? List them by the properties
   they share, not by how they look.

3. **Extract transferable principles from each analog.** For each secondary
   reference: what specifically transfers? What does not? Why?

4. **Fill remaining gaps with tertiary reference.** What underlying principles
   govern how things in this category behave? Apply provisionally.

5. **Flag all tertiary decisions for production validation.** These are the
   decisions most likely to need revision when production tests them against
   reality.

6. **Build the subject from the engineered brief.** The brief is less certain
   than one built from primary reference — but it is far better than no brief
   at all.

---

## Documenting Tier in Practice

Every reference item in a reference brief should have its tier noted. This
does not require elaborate annotation — a simple label is sufficient:

```
[T1] Photograph of actual Khrushchyovka apartment block, Pripyat, 2003
     → Answers: concrete aging at 15-20 years, Eastern European climate

[T2] S.T.A.L.K.E.R. 2 environment screenshots (GSC Game World, 2024)
     → Answers: target desaturation level, style rules for abandoned Soviet structures
     → Transfers: color palette, material read
     → Does not transfer: UE5 Lumen behavior (game uses different pipeline)

[T3] General principle: concrete carbonates at ~1mm/year in temperate climates
     → Source: materials science literature
     → Applied to: surface texture aging depth at 15-year mark
     → FLAG: validate against production render at mid-production milestone
```

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
