# Kanvaz UI v2.0 — Reference Engineering Analysis

---

## Failure Modes Identified

### Failure 1: Autosave Shipped Broken

**What happened:** The autosave feature — the most-requested community
feature — shipped in v2.0.0 with a failure mode where autosave could
overwrite a user's intentional save with an intermediate auto-saved state.
A v2.0.1 patch addressed the most critical form of this. Other autosave
edge cases remain in the queue.

**RE root cause:** Layer 6 (Behavior & Construction) reference was
completely absent. The autosave implementation was designed from first
principles without researching how other canvas applications handle
the state management problem that autosave creates.

**Which Pyramid layer was missing:** Layer 6 — Behavior & Construction
(specifically: how does this category of application handle state
under autosave conditions?)

**Which failure mode this matches:**
*Mistake 08 — Frozen Brief* (partial match) — but more precisely, this
is a new failure mode not in the current list:

**New Failure Mode Candidate: The Unresearched Implementation**
> *"I know how this feature should work from a user perspective."*
>
> Symptom: A feature is implemented based on the developer's mental model
> of user needs without research into how the technical behavior of that
> feature has been solved in comparable applications.
>
> Cause: Treating user-stated requirements ("I want autosave") as sufficient
> specification for implementation, without researching the implementation
> patterns that have solved the same technical problem in other products.
>
> Fix: For any feature that involves state management, data persistence,
> or conflict resolution — research how at least three comparable
> applications implement the same feature before writing a line of code.
>
> Production cost: Shipping broken features that were the project's highest-priority
> deliverable.

---

### Failure 2: Toolbar Layout Through Four Revisions

**What happened:** The primary toolbar layout was revised four times during
v2.0 development. No revision was driven by reference — each was driven
by the feeling that the current version "wasn't right." The final version
was chosen when time ran out, not when a reference-backed answer was found.

**RE root cause:** Layer 4 (Governing Rules) reference was absent.
No written visual rules governed toolbar behavior. Without rules, there
is no basis for evaluating whether a design decision is correct — only
whether it feels correct. "Feels correct" is not stable between revision
cycles.

**Which Pyramid layer was missing:** Layer 4 — Governing Rules

**Which failure mode this matches:**
*Mistake 03 — Style Drift*: Reference gathered as images (the unannotated
screenshots), zero written rule extraction. Every revision was a style drift
correction attempt with no fixed reference point to return to.

---

### Failure 3: Dark Theme Off on Some Displays

**What happened:** Multiple users reported the dark theme has insufficient
contrast on high-brightness displays or in bright ambient conditions.
The application was calibrated to my specific display and shipped to a
user population with a wider display range.

**RE root cause:** Layer 5 (Contextual Conditions) reference was absent.
I know my display conditions. I did not research the display conditions
of VFX/3D artists in production environments.

**Which Pyramid layer was missing:** Layer 5 — Contextual Conditions

**Which failure mode this matches:**
*Mistake 10 — Discipline Mismatch* (partial match): I used my display
as the reference condition, which is a different "discipline" of use
than the target user's color-calibrated, high-brightness, multi-monitor
professional setup.

---

### Failure 4: PureRef Compatibility Not Addressed

**What happened:** Kanvaz is positioned as a PureRef alternative. PureRef
has a community-developed workflow and a file format that users' existing
reference boards are stored in. Kanvaz's file format is not compatible
with PureRef. This is a migration barrier that was never identified
as a design decision because PureRef's workflow was never analyzed.

**RE root cause:** Layer 1 (Function & Context) reference was insufficient.
Experiential use of PureRef ≠ systematic workflow analysis of PureRef.

**Which Pyramid layer was missing:** Layer 1 — Function & Context

**Which failure mode this matches:**
*Mistake 05 — The Missing Analog*: The analog (PureRef) was used but
not engineered from. Surface-level familiarity was treated as sufficient
reference. The specific workflow advantages of the analog were never
extracted, which means Kanvaz v2.0 could not be specifically designed
to surpass them.

---

## Hierarchy Analysis

The reference that was gathered (experiential PureRef knowledge, unannotated
screenshots) was used without tier assignment.

- Experiential PureRef knowledge: this is Tier 2 (Secondary) at best —
  it is my use of the product, not systematic analysis of how target users
  use the product. It was treated as Tier 1 (Primary).
- Screenshot collection: this is Tier 3 (Tertiary) — distant analogs
  gathered without translation. It was treated as ambient Tier 1, consulted
  once, and then functioned as justification rather than reference.

No reference in the project was correctly tiered. The result is that no
decision in the project has a documented tier, which means no decision
can be audited for reference quality.

---

## Gap Patterns

The gap pattern in Kanvaz v2.0 is not unusual — it is the most common
pattern in solo developer projects:

**Layer 1 is assumed from personal experience, not researched.**
The developer uses the tool they are building. They know what they
want. They build what they would want to use. The gap is everything
that the target user wants that differs from what the developer wants —
and that gap is never measured.

**Layer 4 is absent because no one demanded it.**
Visual rules are only forced when there is a design review, a client,
or a team member who asks "why did you make this choice?" Solo development
has none of these forcing functions. Without a written rule set, visual
decisions accumulate from personal preference with no documented standard.

**Layer 5 is assumed from the development machine.**
This is near-universal in solo development. The developer tests on
their machine. The machine is the reference. The target user's machine
is never examined.

---

## Unexpected Findings

**The autosave failure was not primarily a technical failure — it was a
reference failure that manifested as a technical failure.**

My initial assumption when analyzing this case study was that the autosave
bug was a development quality problem: insufficient testing, insufficient
edge case coverage. The RE analysis reveals it was a reference problem:
the failure mode that shipped is a known, documented failure pattern in
canvas application state management that prior art research would have
identified. The implementation was correct for the mental model I was
working from. The mental model was wrong because it was not built from
reference to how this category of application actually behaves.

This is an important finding: **technical failures that appear to be
implementation errors are often reference failures in disguise.** The
implementation was executed correctly. The specification was wrong.
The specification was wrong because the reference that would have
corrected it was never gathered.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
