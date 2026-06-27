# UI/UX Design — Reference Engineering Mistakes

Seven failure modes specific to UI/UX reference practice.

---

## MISTAKE 01 — Designing the Product, Not the Task

> *"The design covers all the features. Why do users say it's hard to use?"*

**Symptom:** Interface that is feature-complete and task-incomplete. The
user can find everything eventually but the primary task requires too many
steps, too much search, too much reading. The design was optimized for
demonstrating features, not for completing the user's job.

**Cause:** Layer 1 (Function & Context) reference was product-focused
rather than task-focused. "What does this product do?" was answered.
"What does the user come here to accomplish and how fast?" was not asked.

**Fix:** Before any design work, define the primary task in terms of
user outcome (not product capability). Define the minimum viable interaction
for that task — the fewest steps in the best comparable product. Make
that count the design target.

**Production cost:** Information architecture redesign. If the navigation
structure was built around features rather than tasks, restructuring it
requires changes throughout the product.

---

## MISTAKE 02 — Inspiration Without Extraction

> *"I pulled reference from Dribbble and built from that direction."*

**Symptom:** Design that looks inspired by comparable products and behaves
differently from them in subtle ways that create user friction. The visual
reference was gathered; the behavioral rules were not. The design looks
like the reference and works differently from it.

**Cause:** Layer 4 (Governing Rules) reference was gathered as visual
inspiration (screenshots) without extracting the behavioral rules those
visuals imply. A design that looks like a well-regarded product will create
user expectations calibrated to that product's behavior. If the behavior
differs, the visual similarity makes the friction worse — the user expected
one behavior and got another.

**Fix:** For every visual reference used, also extract and document the
behavioral rules: what does each interaction do? What is the timing?
What is the feedback? The visual reference is incomplete without the
behavioral rules that make it function.

**Production cost:** Behavioral revision in prototype or implementation
phase when user testing reveals the mismatch between expected behavior
(from visual reference) and actual behavior (from undocumented implementation).

---

## MISTAKE 03 — The Unchecked Convention Departure

> *"We thought the swipe gesture would be intuitive. Users kept doing the wrong thing."*

**Symptom:** Users consistently fail to use the interaction as designed.
The interaction is internally logical and makes sense to the team who
built it. Users who have not been told how it works do not discover it.

**Cause:** Layer 1 (Mental Model) reference was absent or dismissed. A
gesture or interaction was designed without checking whether it conflicts
with the mental model the target users bring from comparable products.
Convention departures require explicit onboarding investment proportional
to how far they depart. Without that investment, users apply their existing
mental model and fail.

**Fix:** For any interaction that departs from platform convention, document
the departure explicitly, note what users will expect based on comparable
products, and design the onboarding that closes the gap. Or reconsider
the departure — convention exists because users already know it.

**Production cost:** Onboarding redesign, tooltip investment, user education
content. If the gesture conflict is severe, the interaction must be redesigned.

---

## MISTAKE 04 — Contrast Calibrated to the Designer's Display

> *"It looks fine on my monitor. Why are users reporting it's hard to read?"*

**Symptom:** Text or UI elements that appear readable on the design monitor
and are reported as hard to read by users on different displays or in
different ambient conditions. Typically: contrast that passes on a
calibrated studio monitor and fails on a high-brightness mobile display
in daylight.

**Cause:** Layer 5 (Contextual Conditions) reference was absent. The design
was calibrated to the design team's display environment, which is almost
always better than the target user's environment. WCAG contrast ratios
are the documented minimum — but they assume a standard display. Real
users use displays at various brightness settings.

**Fix:** WCAG 4.5:1 is the floor, not the target. Calibrate contrast ratios
against the high end of the target user's display brightness range.
For mobile: test in bright ambient light with display brightness at
maximum. For consumer apps: test on the cheapest screen in the target
device range.

**Production cost:** Color system revision across all components. If design
tokens were used correctly, this is a variable change. If colors were
hardcoded, it's a component-by-component audit.

---

## MISTAKE 05 — States as Afterthoughts

> *"The empty state just shows a blank screen. The error state just says 'Error'."*

**Symptom:** Shipped product with incomplete states: empty states that
give users no guidance, error states that don't explain what happened
or what to do, loading states that don't indicate progress, success
states that don't confirm what completed.

**Cause:** Layer 7 (Precision Detail) state reference was absent from
the design process. States were treated as edge cases to be handled
by developers, not as designed experiences requiring reference and specification.

**Fix:** Before any component or screen is marked complete, document and
design all states: empty, loading, error, success, and partial (partially
loaded content). Reference comparable products' state designs explicitly.
The best products treat every state as a designed experience, not an
edge case.

**Production cost:** State design and implementation added retroactively.
If states were not specified, developers implement them by default — which
produces "Error" messages and blank screens. Retroactive state design
requires implementation changes after QA.

---

## MISTAKE 06 — Accessibility as Compliance Checkbox

> *"We have an accessibility section in the spec. Why did we fail the audit?"*

**Symptom:** Accessibility audit reveals failures despite having
accessibility requirements in the spec. Common: focus states that are
specified but not implemented correctly, contrast ratios that pass on
the design but fail in implementation due to opacity or overlay, keyboard
navigation flows that were never tested.

**Cause:** Accessibility was included as Layer 4 written rules but not
validated as Layer 5 contextual conditions through actual testing.
Rules that are not tested are not implemented. Accessibility requirements
must be validated with assistive technologies, not just measured in Figma.

**Fix:** Accessibility is a Layer 5 contextual condition that requires
active testing, not just specification. The design spec includes the
requirements. The validation checklist includes: keyboard navigation
test, screen reader test, contrast check in implementation (not in
Figma), and reduced-motion test.

**Production cost:** Post-implementation accessibility remediation is
3–5× more expensive than designing accessible from the start.
Legal risk in regulated industries.

---

## MISTAKE 07 — Design System Without Governance

> *"The design system exists but nobody uses it consistently."*

**Symptom:** Design system components exist. Shipped product contains
one-off variations of those components — buttons at slightly different
sizes, cards with different border radii, typography that doesn't match
the type scale. The design system has rules but the rules aren't enforced.

**Cause:** Layer 4 (Governing Rules) was documented but not designed with
enforcement in mind. The design system rules existed as a reference document
but not as a production constraint. Without enforcement (design review,
linting, Figma component structure that prevents divergence), rules drift.

**Fix:** Design system rules must be enforced at the component level, not
documented and trusted. In Figma: locked components with constrained
properties prevent the most common rule violations. In code: design
token enforcement through linting. In process: design review that explicitly
checks component compliance, not just visual appearance.

**Production cost:** Design consistency audit and standardization pass
across the product. For a large product: multiple weeks. For a small
product: days. Prevention cost: upfront component structure and review
process that takes hours, not days.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
