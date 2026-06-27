# Web Development — Reference Engineering Guide

Full methodology for gathering, analyzing, and organizing reference across
the complete web development production arc.

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Function & Context

### What to Find

**User task reference:** Documentation of what the user is actually trying
to accomplish — not what the page is supposed to offer, but what the user
arrives needing. Sources: user research, usability test recordings, customer
support logs, search query data, competitor reviews that describe what users
come for. The user's task is the Layer 1 anchor for every subsequent decision.

**Competitive landscape reference:** What do the three best versions of
this type of interface do? Not what do they look like — what do they do?
How do they structure the primary user task? What navigation pattern?
What information hierarchy? The best-in-class example for the task type
is primary tier reference, not inspiration.

**Context of use reference:** Where and how is this interface used?
Mobile-first means something different for a banking app (high intent,
careful attention, frequent interruption) than for a social feed (low
intent, casual attention, continuous scroll). The same "mobile-first"
constraint produces different design decisions depending on the context
of use.

**Anti-reference:** What has failed in this product category? What does
the user hate about existing solutions? Negative reference — what this
product must not do — is as important as positive reference.

### Discipline-Specific Questions

- What is the one thing the user must be able to do on this page without any confusion?
- What does the user do immediately before arriving here and immediately after leaving?
- What emotional state is the user in when they arrive? (motivated/frustrated/uncertain/informed)
- What is the single most common failure point in this product category from the user's perspective?

---

## Layer 2 — Scale & Proportion (Information Hierarchy)

### What to Find

**Viewport distribution data:** What screen sizes cover 90%+ of the target
audience? This is not a design assumption — it is a measurable fact for
any established audience and an inferable estimate for new products (use
category benchmarks). The viewport distribution determines breakpoint
priorities and content density decisions.

**Information hierarchy reference:** How much content belongs above the
fold at the primary viewport? What is the primary action — is it visible
without scrolling? What is secondary? What requires navigation?
The information hierarchy is a proportion decision, not a visual design
decision. It should be established at wireframe stage from reference,
not discovered during mockup.

**Content density reference:** What is the appropriate information density
for this interface type and user task? A data dashboard has different
density norms than a marketing landing page. Find the best examples
of the correct density for this specific type — not the category average.

### Discipline-Specific Questions

- What viewport is the design primary for? (What does the audience actually use?)
- What is the content-to-chrome ratio at the primary viewport?
- What content is above fold at mobile primary viewport in the most common use case?
- What is the reading distance and minimum text size for the primary use context?

---

## Layer 3 — Production Stage Reference

### Web Development Production Stages

| Stage | What You're Building | Reference Needed |
|---|---|---|
| Discovery | Problem definition, scope | User task research, competitive analysis |
| Wireframe | Information architecture, layout structure | Structural patterns, navigation models, layout references |
| Visual Design | Visual language, component design | Design system references, style rules, typography |
| Prototype | Interaction behavior, animation | Interaction pattern libraries, animation references |
| Implementation | Code structure, browser behavior | Framework documentation, browser compatibility, accessibility |
| QA / Launch | Cross-device/browser validation | Device testing matrix, accessibility audit tools |

### Stage-Appropriate Reference Practice

**At wireframe stage:** Gather structural and layout reference only.
Do not gather visual style reference at this stage — it will contaminate
structural decisions. The wireframe should answer: does this layout work
for the task? Not: does this look right?

**At visual design stage:** Gather style rule reference and design system
reference. Apply the rules you extracted from the competitive landscape.
Do not gather implementation reference at this stage.

**At implementation stage:** Gather framework-specific reference and
browser behavior reference. The question is: does this actually work
the way I designed it, in the browsers and devices the user has?

---

## Layer 4 — Governing Rules

### What to Extract

**Typography parameters:** Size scale (not just "big/medium/small" —
actual rem values or type scale ratios), weight range used, line height
range, tracking adjustments at display sizes. Written numbers, not feelings.

**Color system parameters:** Primary, secondary, and semantic colors
with exact values. Background hierarchy (surface, elevated surface, overlay).
Semantic colors (success, warning, error, info) with contrast ratios
documented against their expected backgrounds.

**Spacing system:** Base unit and scale. Grid columns and gutters at
each breakpoint. Component internal padding standards.

**Interactive state parameters:** Hover, focus, active, disabled states
for every interactive element type. Focus states are a common omission —
extract reference for how the best products in this category handle focus
visibility.

**The written rules format for web dev:**

```
Typography:
  Body: 16px/1.5 line-height, system-ui, regular weight
  Heading 1: 2.5rem, -0.02em tracking, 600 weight
  Small: 14px, 1.4 line-height
  Never: font-size below 14px, line-height below 1.3

Color:
  Background: #F8F9FA
  Surface: #FFFFFF
  Primary: #2563EB (contrast 4.5:1 on background)
  Error: #DC2626 (contrast 4.5:1 on background)
  Never: placeholder text below 4.5:1 contrast

Spacing:
  Base unit: 4px
  Component padding: 12–24px (3–6 base units)
  Section spacing: 48–96px (12–24 base units)
  Never: arbitrary values not on the scale
```

---

## Layer 5 — Contextual Conditions

### Browser and Device Rendering

**Browser rendering reference:** CSS features behave differently across
browsers. What the design assumes must be validated against what the
target browser range actually renders. CSS grid, custom properties,
container queries, color-mix(), and many other modern CSS features
have varying support levels that affect whether the design is even
achievable in the target environment.

**Display rendering reference:** sRGB color profiles, HDR display behavior,
system dark mode, browser default font rendering (subpixel AA vs. grayscale AA)
all affect how the visual design actually appears to the user. Reference
gathered on one display configuration may look wrong on another.

**Ambient conditions:** A website used primarily on mobile in transit
(bright ambient, one-handed, distracted) needs different contrast and
tap target size than one used at a desktop in an office. The conditions
of use are Layer 5 reference.

### Performance Context

**Core Web Vitals targets:** LCP, CLS, and INP targets are contextual
constraints, not post-launch concerns. They constrain technical decisions
at the implementation stage. Know the targets before implementation begins.

**Bandwidth assumptions:** What is the connection quality of the target
audience? A fintech product for corporate users assumes enterprise WiFi.
A civic service product assumes residential broadband with a percentage
of mobile data users. The bandwidth assumption constrains image sizing,
font loading strategy, and JavaScript bundle size.

---

## Layer 6 — Framework and Browser Behavior

### What to Find

**Framework constraints:** What does the chosen framework do that cannot
be overridden without significant cost? React's rendering model, Next.js
routing behavior, SvelteKit's hydration approach — each has behaviors
that constrain what is easily buildable. Know these before designing
interactions that fight the framework.

**Component library constraints:** If a component library is used,
what does it do out of the box and what requires override? Overriding
a component library's defaults is always more expensive than designing
to its defaults. Reference the library's component behavior before
designing against it.

**Browser quirks at target range:** What specific behaviors does the
target browser range exhibit that differ from the specification or from
the developer's primary browser? iOS Safari has different scroll behavior,
different date input behavior, and different flexbox edge case behavior
than Chrome. If iOS Safari is in the support matrix, it needs to be in
the reference matrix.

---

## Layer 7 — Precision Detail

### What to Find

**Micro-interaction reference:** How do the best products in this category
handle hover states, loading states, success states, and error states?
What animation timing and easing functions are appropriate for this interface
register? (Playful apps use spring physics. Financial products use linear
or ease-out. The register of the animation communicates personality.)

**Copy precision reference:** What voice and tone do the best products
in this category use for button labels, error messages, empty states,
and loading messages? The copy is as much a Layer 7 precision decision
as the pixel-level visual design.

**Accessibility precision:** What does a correct focus ring look like
for this design system? What do screen reader announcements sound like
for the interactive patterns used? What do keyboard navigation flows
feel like? These are testable against standards — gather the standards
as reference before implementation.

---

## The Web Development Reference Brief

```
PROJECT: [site/app name]
TYPE: [landing page / web app / e-commerce / marketing / SaaS / other]
PRIMARY AUDIENCE: [who is using this]
DATE: [brief version date]

LAYER 1 — FUNCTION & CONTEXT
Primary user task (one sentence):
User context of use:
Top 3 competitive references:
What this product must NOT do (anti-reference):

LAYER 2 — SCALE & PROPORTION
Primary viewport:
Viewport distribution (top 3):
Primary breakpoints: mobile  tablet  desktop
Above-fold content at mobile:
Information hierarchy (what is primary / secondary / tertiary):

LAYER 3 — CURRENT STAGE
[ ] Discovery  [ ] Wireframe  [ ] Visual Design  [ ] Prototype  [ ] Implementation
Stage reference gathered:
Stage-specific gaps:

LAYER 4 — GOVERNING RULES
Type scale (document values):
Color system (document hex + contrast ratios):
Spacing base unit:
What this interface NEVER does:

LAYER 5 — CONTEXTUAL CONDITIONS
Target browser range:
Target device range:
Primary ambient condition (mobile-in-transit / desktop-office / other):
CWV targets: LCP  CLS  INP
Bandwidth assumption:

LAYER 6 — FRAMEWORK & BEHAVIOR
Framework:
Component library (if any):
Known browser quirks in target range:
Framework constraints that affect design:

LAYER 7 — PRECISION DETAIL (complete at implementation stage)
Micro-interaction references:
Focus state design:
Empty state designs:
Error state designs:

GAPS:
Critical:
High:
Low:

BRIEF VERSION: [v1.0 / v2.0 / vFinal]
```

---

## When to Re-Run Reference Work

- After user testing reveals the primary task assumption was wrong
- When the framework or component library changes
- When the target browser range expands (new support requirement)
- When performance targets are missed and architectural decisions need revisiting
- When the scope expands beyond the original brief's assumptions

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
