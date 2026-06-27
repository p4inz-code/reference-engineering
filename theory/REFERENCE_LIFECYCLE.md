# Reference Lifecycle

**Part of:** Reference Engineering Theory Layer
**Relates to:** Principle 6 — Knowledge compounds · Principle 7 — Systems outperform memory

References have a lifecycle. They are not static objects that exist in the
same state from collection to disposal. Understanding the lifecycle of a
reference — how it is created, how it ages, when it becomes stale, and how
it should be archived — is essential to maintaining a reference system that
remains useful over time.

---

## The Lifecycle Stages

```
        IDENTIFIED
             │
             ▼
        COLLECTED ──── annotation applied at this stage ────┐
             │                                              │
             ▼                                              ▼
          ACTIVE ─── in use, informs current decisions     ANNOTATION
             │         (question, tier, relationships)
             ▼
       ┌─────┴─────┐
       ▼           ▼
     STALE      ARCHIVED
  (superseded)  (retained for
                historical context)
```

### Stage Definitions

**Identified:** The reference has been recognized as potentially relevant
but not yet collected. The identification stage is brief — either collect
it or decide not to. Do not maintain long "to gather" lists without acting on them.

**Collected:** The reference has been acquired and is in the reference system.
Collection without annotation is incomplete — a collected but unannotated
reference is in a degraded state that reduces its future value.

**Active:** The reference is annotated, connected to a question, tiered,
and in active use. Active references are the working materials of current production.

**Stale:** The reference has been superseded by higher-quality reference,
the production question it answered has been resolved and closed, or the
reference's information has become outdated. Stale references should be
marked as such and moved out of the active working set — not deleted.

**Archived:** The reference is retained in the system but no longer active.
It serves historical context: what was known at a specific point in
production, what decisions were made from it, and why those decisions were
correct given the information available at the time.

---

## Reference Aging

### What Makes a Reference Go Stale

Not all references age at the same rate. The rate of staleness depends on
the nature of the reference's content:

| Reference Type | Staleness Rate | Staleness Trigger |
|---|---|---|
| Technical specifications | Medium — updates when standards change | Standard revision, platform update |
| Visual style reference | Low — stylistic periods are stable | Major style shift in the domain |
| Tool/software reference | High — updates with software versions | Software version change |
| Real-world material documentation | Very low — materials behave the same | New research changes understanding |
| Competitor/market reference | High — products change | Product update, competitor launch |
| User behavior reference | Medium — behaviors shift gradually | Platform change, audience shift |
| Physical measurement/dimension | Very low — dimensions don't change | Error discovery, scope change |

### The Staleness Audit

At every major project milestone, existing references should be audited
for staleness. The staleness audit asks:

- Is the information in this reference still accurate?
- Has a higher-tier reference been found that supersedes this one?
- Has the production question this reference answers been resolved and closed?
- Has the project scope changed in a way that makes this reference no longer applicable?

References that pass the audit remain active. References that fail are
moved to stale and replaced if necessary.

---

## Brief Versioning

A reference brief is not a static document. It is a versioned artifact that
evolves as production progresses and as the Core Loop is re-run at each milestone.

### Version Naming

```
Brief v1.0 — pre-production (initial)
Brief v1.x — pre-production revisions (within the same production phase)
Brief v2.0 — post-[first major milestone] (significant update)
Brief v2.x — revisions within the second phase
Brief vFinal — delivery/handoff
```

### What Changes Between Versions

**v1.0 → v2.0 (after first milestone):**
- Gaps revealed by the first production phase are filled
- Stale references from v1.0 are marked and replaced
- Stage-appropriate reference for the new phase is added (Layer 3 update)
- New relationships discovered during production are documented

**v2.0 → vFinal:**
- All Pyramid layers should be covered for all phases completed
- All critical gaps should be resolved or documented as accepted risks
- All decisions should trace to a reference (or be documented as undocumented assumptions)
- Retrospective notes added: what would be gathered differently next time

### Version Control for Reference Briefs

Reference briefs should be version-controlled in the same system as the
production work they support. A reference brief stored only in a personal
document and not version-controlled is at risk of loss and cannot support
the historical audit function.

Minimum version control requirements:
- Date-stamped versions at each major milestone
- A changelog entry noting what changed and why
- The brief accessible to all team members who make decisions it governs

---

## The Frozen Brief

The Frozen Brief is the most common lifecycle failure mode. It occurs when
a brief is written once at the start of a project and never updated.

### Why Briefs Freeze

- The practitioner treats reference work as a one-time pre-production task
- The production phase creates time pressure that crowds out brief maintenance
- No milestone audit trigger is scheduled
- The brief is stored in a format that makes updating difficult

### Why Frozen Briefs Fail Production

Production always reveals what pre-production missed. The gap between what
was known at v1.0 and what is known at mid-production is not a failure of
the initial brief — it is an expected property of production. The initial
brief could not have known what the production process would reveal.

A frozen brief means those gaps are discovered by production stalls rather
than by audits. The cost is measured in rework and delay rather than in
the thirty to sixty minutes a milestone audit requires.

### Prevention

Schedule milestone audits in the project plan before production begins.
Make them non-optional. Treat a brief update as a production deliverable,
not an optional maintenance task.

---

## Long-Term Reference Systems

### Beyond the Project

Reference Engineering compounds across projects when references are retained
and made retrievable beyond their originating project. A reference system
maintained across projects accumulates:

- Source knowledge (where to find specific types of reference quickly)
- Connection patterns (which reference types tend to confirm or contradict each other)
- Failure mode recognition (which gap patterns appear repeatedly)
- Calibrated judgment (how to weight references from different tiers in different domains)

### Personal Reference Libraries

A personal reference library is a long-term reference system maintained by
an individual practitioner across projects and across time. It differs from
a project reference brief in scope and purpose:

| | Project Reference Brief | Personal Reference Library |
|---|---|---|
| Scope | Single project | All projects, all time |
| Purpose | Inform current decisions | Build compounding reference capital |
| Lifecycle | Created per project, archived | Continuously maintained |
| Organization | By Pyramid layer for this project | By domain, subject, and relationship |
| Access | Project team | Individual (or team with shared library) |

Building a personal reference library is not required. It is the long-term
compounding behavior that converts Reference Engineering from a per-project
practice into a career-spanning asset.

---

## Institutional Reference Memory

When Reference Engineering is practiced at a team or organization level,
the reference system becomes institutional reference memory: the accumulated
reference capital of the organization that exists independently of any
individual practitioner's tenure.

Institutional reference memory requires:
- Shared reference systems accessible to all practitioners
- Documented brief versioning for all projects (not stored in personal files)
- Onboarding processes that transfer reference system knowledge to new practitioners
- Archiving practices that retain briefs in retrievable form after project close

Organizations without institutional reference memory restart from zero on
every project and with every new hire. Organizations with it compound.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
