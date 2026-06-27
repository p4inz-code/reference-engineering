# UI Redesign — Problem & Brief

**Project:** B2B Fintech Analytics Dashboard Redesign
**Stage:** Pre-production / wireframe stage
**Date:** [project start]
**Brief version:** 1.0

---

## Production Questions This Brief Must Answer

These are the questions that reference needs to answer before a single
wireframe is drawn. Each question maps to a Pyramid layer.

### Layer 1 — Function & Context

- [ ] What is the primary task a financial analyst performs in this dashboard in the first 60 seconds of a session?
- [ ] What data does a portfolio manager need to see without scrolling on arrival?
- [ ] What actions are performed most frequently vs. most critically (not the same thing)?
- [ ] What is the physical viewing context — is this used on a desktop monitor, a laptop on the go, or a second screen?
- [ ] What does the user do *immediately before* opening this dashboard and *immediately after*? (surrounding workflow context)
- [ ] What are the two or three decisions this dashboard is supposed to make easier?

### Layer 2 — Scale & Proportion (Information Hierarchy)

- [ ] How many data points are genuinely primary (visible at all times, above fold)?
- [ ] How many are secondary (visible on the main screen but not dominant)?
- [ ] How many are tertiary (require interaction to surface)?
- [ ] What viewport sizes cover 90% of the target user base?
- [ ] What is the minimum readable text size at the furthest realistic viewing distance?

### Layer 3 — Production Stage (Wireframe)

*At wireframe stage, reference needed is: information architecture reference,
layout pattern reference, navigation model reference. Not visual style.*

- [ ] What navigation model does the category leader in this space use?
- [ ] What layout pattern handles the combination of summary metrics + detailed charts?
- [ ] How do the top 3 competitors handle the "overview → drill-down" navigation pattern?

### Layer 4 — Style Rules

- [ ] What visual parameters define "authoritative" vs "flashy" in this product category?
- [ ] What typography decisions communicate precision and trust in B2B financial products?
- [ ] What data visualization conventions are standard in financial contexts (colors for positive/negative, chart types, grid density)?
- [ ] What does this style *never* do? (constraints define the style as much as examples)

### Layer 5 — Rendering/Display Context

- [ ] What is the primary ambient lighting condition where this product is used? (office, home office, variable)
- [ ] Does the product need to work in both light and dark modes, or is one primary?
- [ ] Are there display calibration standards that financial industry users expect (color accuracy for data)?
- [ ] What monitor quality range covers the target user base?

### Layer 6 — Framework Behavior

- [ ] What component library or design system is this being built on?
- [ ] What constraints does the chosen framework impose on layout and interaction patterns?
- [ ] What browser/OS rendering differences are relevant at the target viewport sizes?

### Layer 7 — Hero Detail (Defer to mockup stage)

*These questions will be answered in Brief v2 at the mockup stage:*
- What micro-interactions reinforce the "precise and authoritative" feel?
- What loading states exist and what do they communicate?
- What empty states exist and how should they be handled?

---

## Reference Tier Plan

| Question category | Expected tier | Notes |
|---|---|---|
| Industry conventions | Primary | Real products exist; use them |
| "Authoritative" style rules | Secondary | No single authoritative standard — extract from 3+ competitors |
| Trust signals | Tertiary | Extract from adjacent fields (legal, medical, aerospace UI) |

---

## Gap Risk Assessment

| Gap | Risk if unresolved | Priority |
|---|---|---|
| Primary user task unclear | High — layout will be wrong at structure level | CRITICAL |
| Viewport size distribution unknown | Medium — may design for wrong breakpoints | HIGH |
| "Authoritative vs flashy" line unclear | High — visual direction will be contested | HIGH |
| Framework constraints unknown | Medium — components chosen may not exist | MEDIUM |

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
