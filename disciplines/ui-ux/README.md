# Reference Engineering — UI/UX Design

> Systematic pre-production reference methodology for UI/UX designers working on digital products and interfaces.

**Discipline:** UI/UX Design
**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Who This Is For

UI/UX designers working on digital product interfaces: mobile apps, web apps,
SaaS products, consumer apps, and enterprise tools. The methodology covers
research through delivery — from understanding the user's task to validating
the final interaction in production conditions. Equally applicable to
product designers working within an existing design system and to designers
establishing a design system from scratch.

---

## What Reference Engineering Solves in UI/UX

The most expensive failures in UI/UX are discovered in user testing or
post-launch. Reference Engineering front-loads the questions that user
testing would answer — using competitor analysis, pattern libraries, and
platform conventions as reference that answers design questions before
the first wireframe is drawn.

The most common reference failure in UI/UX: gathering visual inspiration
without extracting behavioral rules. Saving Dribbble screenshots answers
"what does this look like?" Reference Engineering asks "what rules produce
this look and behavior?" — and writes those rules down before implementation.

---

## The Pre-Production Questions UI/UX Must Answer

- [ ] What is the user's primary task? Not what the product does — what job the user hires it for?
- [ ] What is the user's mental model entering this interface? What do they already know?
- [ ] What are the three most common user errors in comparable products?
- [ ] What platform conventions apply? (iOS HIG, Material Design, Web standards)
- [ ] What are the written visual rules — not the mood, the measurable parameters?
- [ ] What accessibility standard applies, and is it a floor or a target?
- [ ] What does "success" look like for this interface — what does the user accomplish and feel?
- [ ] What is the minimum viable interaction — the fewest steps to complete the primary task?

---

## Pyramid Layer Map for UI/UX

| Pyramid Layer | What It Means in UI/UX Design |
|---|---|
| Layer 1 — Function & Context | User's primary task, mental model, context of use, emotional state on arrival |
| Layer 2 — Scale & Proportion | Information hierarchy, viewport range, content density, reading distance |
| Layer 3 — Stage Reference | Research reference; wireframe/IA reference; visual design reference; prototype reference |
| Layer 4 — Governing Rules | Design system parameters, interaction model rules, platform convention compliance — written values |
| Layer 5 — Contextual Conditions | Device and browser range, display conditions, platform rendering behavior |
| Layer 6 — Behavior & Construction | Component library behavior, animation framework constraints, platform interaction model |
| Layer 7 — Precision Detail | Micro-interactions, copy precision, focus states, empty states, transition timing |

---

## Contents

| File | What's in it |
|---|---|
| [`REFERENCE_GUIDE.md`](./REFERENCE_GUIDE.md) | Full methodology — all seven layers, interaction pattern analysis, brief template |
| [`mistakes.md`](./mistakes.md) | 7 UI/UX-specific failure modes |
| [`checklist.md`](./checklist.md) | Stage-organized checklist from research through delivery |
| [`sources.md`](./sources.md) | Best UI/UX reference sources by layer |

---

## Related

- **Example:** [`examples/ui-redesign/`](../../examples/ui-redesign/) — complete worked example for a B2B analytics dashboard
- **Discipline:** [`disciplines/web-dev/`](../web-dev/) — implementation methodology (UI/UX governs design; web-dev governs build)
- **Discipline:** [`disciplines/app-dev/`](../app-dev/) — app-specific platform conventions

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
