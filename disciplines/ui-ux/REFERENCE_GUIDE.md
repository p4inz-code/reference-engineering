# UI/UX Design — Reference Engineering Guide

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Function & Context

### What to Find

**User task reference:** What job does the user hire this interface to do?
Not what the product does — what the user accomplishes. A calendar app
helps users avoid missed commitments and manage time. The task is "I need
to know what I'm doing and when" — not "I need to create events." The
distinction governs what information needs to be visible by default.

**Mental model reference:** What does the user already know when they
arrive? What prior experiences shaped their expectations? A user who
comes from Gmail has a specific mental model for email. A user who
comes from Notion has a specific mental model for documents. The mental
model reference determines what conventions to honor and what conventions
are safe to depart from.

**Failure mode reference:** What are the three most common user errors
in comparable products? App store reviews, support ticket themes, and
user testing reports from comparable products are primary-tier sources
for understanding where users fail — before any wireframe is drawn.

**Emotional context reference:** What emotional state is the user in
when they arrive? A user filing an insurance claim is stressed and
wants efficiency and clarity. A user browsing a music discovery app
is relaxed and exploratory. The emotional context governs tone, pacing,
and information density.

### The Task Analysis Format

```
PRIMARY TASK: [one sentence — what the user accomplishes]
PRE-TASK STATE: [where the user comes from, what they know]
POST-TASK STATE: [what has changed for the user after success]
COMMON FAILURE: [what prevents task completion in comparable products]
EMOTIONAL REGISTER: [stressed/relaxed/focused/exploratory/other]
SUCCESS CRITERION: [how the user knows they completed the task]
```

---

## Layer 2 — Scale & Proportion (Information Hierarchy)

### What to Find

**Information hierarchy reference:** What information must be visible
immediately? What requires interaction to surface? What is never needed
by 90% of users (candidate for removal)? Reference comparable products
and document their information hierarchy explicitly — not by looking at
screenshots, but by noting what each UI element communicates and whether
it is primary, secondary, or tertiary.

**Content density reference:** What is the information density appropriate
for this product type and user task? A data dashboard has different density
norms than a onboarding screen. A settings page has different density
than a feed. Find the best examples of the correct density for each
screen type in comparable products.

**Minimum viable interaction:** How few steps does it take to complete
the primary task in the best comparable product? This is the benchmark.
If your design requires more steps for the same task, each additional
step requires justification.

---

## Layer 3 — Stage Reference

### UI/UX Production Stages

| Stage | What You're Building | Reference Needed |
|---|---|---|
| Research | Problem definition, user needs | User research, competitor analysis, failure mode documentation |
| Information Architecture | Structure, navigation, content organization | IA patterns, navigation models, card sort results |
| Wireframe | Layout, hierarchy, interaction flows | Layout patterns, wireframe conventions, flow reference |
| Visual Design | Design system, component design | Platform HIG, design system reference, visual style |
| Prototype | Interaction behavior, transitions | Interaction pattern libraries, animation reference |
| User Testing | Validation | Testing protocol reference, task completion benchmarks |
| Delivery | Final specs | Accessibility standards, design token documentation |

### Stage-Appropriate Reference Practice

**At research stage:** Primary reference is user data — real users, real
problems, real failures. No wireframes. No visual references. The research
stage answers: is the problem real, and does our solution address it?

**At IA stage:** Reference navigation models and content organization
patterns from comparable products. The question is structural — does
this organization make the right information findable?

**At wireframe stage:** Reference layout and pattern libraries. The question
is functional — does this layout allow the user to complete the task?
No color, no visual design. Wireframes should be evaluable on function alone.

**At visual design stage:** Design system and style reference become active.
Platform HIG compliance is checked here. The question shifts to: does
this look right, and does it follow the rules?

---

## Layer 4 — Governing Rules

### Interaction Pattern Analysis

The primary Layer 4 practice for UI/UX is interaction pattern analysis —
extracting the specific behavioral rules of comparable products, not just
their visual appearance.

**Interaction Pattern Analysis Format:**

```
PRODUCT: [name]
PATTERN: [specific interaction being analyzed]
DATE ANALYZED: [date]

WHAT TRIGGERS IT: [user action]
WHAT HAPPENS: [system response — specific, not general]
TIMING: [duration in ms or frames]
FEEDBACK: [visual / haptic / audio — specific]
EDGE CASES: [what happens when it fails, is interrupted, or repeats]

EXTRACTED RULES:
1. [Rule as a design constraint]
2. [Rule as a design constraint]

WHAT THIS PRODUCT NEVER DOES:
- [Negative constraint]

TRANSFERABLE: [what applies to our product]
NOT TRANSFERABLE: [what is specific to this product's context]
```

### Design System Rules (Written Parameters)

The written rules for a UI/UX design system must be specific enough that
two designers produce consistent results by following them — not by
looking at the same Figma file.

```
TYPOGRAPHY:
  Heading 1: 32px / 1.25 line-height / -0.01em tracking / 700 weight
  Body: 16px / 1.6 line-height / 0em tracking / 400 weight
  Caption: 12px / 1.4 line-height / 0.02em tracking / 400 weight
  Minimum size: 12px (never smaller)
  Maximum weight: 700 (never bold above this)

SPACING:
  Base unit: 4px
  Component padding: 12px (3 base) to 24px (6 base)
  Section spacing: 48px (12 base) to 96px (24 base)
  Never: values not on the 4px scale

COLOR:
  Background: #F8F9FA (not white — reduces eye strain)
  Primary action: #2563EB (contrast 4.5:1 on background)
  Destructive: #DC2626 (contrast 4.5:1 on background)
  Success: #16A34A (contrast 4.5:1 on background)
  Text primary: #111827 (contrast 13.2:1 on background)
  Text secondary: #6B7280 (contrast 4.5:1 on background — minimum)

BORDER RADIUS:
  Small components (buttons, tags): 6px
  Cards and containers: 12px
  Full-width surfaces: 0px
  Never: mixing radius values within the same component

WHAT THIS DESIGN SYSTEM NEVER DOES:
  - Font size below 12px
  - Contrast ratio below 4.5:1 for any text
  - Animation above 400ms for UI transitions
  - More than 3 type sizes on a single screen
  - Decorative borders (borders only where they aid separation)
```

---

## Layer 5 — Contextual Conditions

### Platform and Device Reference

**Device range:** What devices does the target user actually use?
Not what devices exist — what devices this product's target audience uses.
Analytics or category benchmarks provide primary-tier data.

**Display conditions:** High-brightness mobile in sunlight is a different
display context than a calibrated design monitor in a dim studio.
The design must function in the actual display conditions of the users.

**Input precision:** Touch has lower precision than mouse. A button
that works at 16×16px for mouse users is unusable for touch users
at the same size. Platform guidelines specify minimum touch target
sizes (44×44pt iOS, 48×48dp Android) — these are Layer 5 constraints.

### Accessibility as Layer 5

Accessibility standards are contextual conditions — they define the
range of users who need to be able to use the product. WCAG 2.1 AA
is the minimum standard for most products. WCAG 2.1 AAA is the target
for publicly-funded or healthcare-adjacent products.

Accessibility constraints that function as design rules:
- Minimum contrast ratio: 4.5:1 for normal text, 3:1 for large text
- Minimum touch target: 44×44px (not the visual element — the hit area)
- Focus indicator: visible, minimum 3px outline, meets contrast ratio
- Animation: must be disableable (prefers-reduced-motion)
- Text: must scale to 200% without breaking layout

---

## Layer 6 — Behavior & Construction

### Component Library Behavior Reference

If a component library is used (Radix, Headless UI, shadcn/ui, Material UI),
document what it does by default before designing against it.
Default behaviors that are hard to override are constraints on design.

**Key behaviors to document:**
- Dropdown: does it use a portal? Does it handle overflow? Does it trap focus?
- Modal: what is the close behavior? Escape key? Backdrop click?
- Form validation: when does it trigger? (on blur, on submit, on change?)
- Toast/notification: what is the default duration? Position? Stack behavior?

### Animation Framework Constraints

What animation capabilities does the chosen framework support? Web:
CSS transitions and animations have hardware acceleration constraints.
React Native: Animated API has bridge overhead. Flutter: all animations
on the GPU — very capable. The animation capability constrains what
Layer 7 micro-interactions are feasible.

---

## Layer 7 — Precision Detail

### Micro-Interaction Reference

**Transition timing:** UI transition durations by type:
- Instant feedback (button press, checkbox): 100ms or less
- State changes (expanding accordion, tab switch): 150–250ms
- Screen transitions (page navigation): 250–350ms
- Complex animations: 350–500ms
- Never: UI transitions above 500ms (feels slow to users)

**Easing reference:** Correct easing by interaction type:
- Elements entering: ease-out (fast start, slow end — arrives naturally)
- Elements leaving: ease-in (slow start, fast end — departs crisply)
- Elements moving: ease-in-out (smooth throughout)
- Physics-based (bouncy UI): spring curve (React Spring, Framer Motion)

**Copy precision:** Every string in the interface is a Layer 7 decision.
Reference the copy conventions of comparable products:
- Button labels: verb + noun ("Save changes" not "Submit")
- Error messages: explain what happened + what to do next
- Empty states: explain why it's empty + how to fix it
- Loading states: tell the user what is loading and how long it will take

### Focus State Design

Focus states are the most commonly missed Layer 7 element.
Every interactive element needs a visible focus state. Reference:
- WCAG requires focus indicator to be at minimum 3px, contrasting color
- Platform default focus (browser blue outline) is acceptable if it meets contrast
- Custom focus states must meet or exceed the WCAG minimum
- Test with keyboard-only navigation — all focus states must be visible

---

## The UI/UX Reference Brief

```
PROJECT: [product name]
TYPE: [mobile app / web app / SaaS / consumer / enterprise]
PLATFORM: [iOS / Android / Web / cross-platform]
DATE: [brief version date]

LAYER 1 — USER TASK
Primary task (one sentence):
User mental model entering:
Top 3 comparable product failure modes:
Emotional register on arrival:
Success criterion:

LAYER 2 — INFORMATION HIERARCHY
Information priority: primary / secondary / tertiary (list per screen)
Minimum viable interaction (step count):
Content density target (reference: [comparable product]):

LAYER 3 — CURRENT STAGE
[ ] Research  [ ] IA  [ ] Wireframe  [ ] Visual Design  [ ] Prototype  [ ] Testing
Stage-specific reference gathered:

LAYER 4 — GOVERNING RULES
Typography (document exact values):
Color (document hex + contrast ratios):
Spacing base unit:
Border radius system:
Interaction pattern rules (document per pattern):
What this design NEVER does:

LAYER 5 — CONTEXTUAL CONDITIONS
Target device range:
Minimum contrast standard: WCAG AA / AAA
Minimum touch target: [px]
Motion preference: must support prefers-reduced-motion: [ ]
Font scaling: layout stable at 200% text scale: [ ]

LAYER 6 — BEHAVIOR & CONSTRUCTION
Component library (if any):
Known default behaviors that constrain design:
Animation framework:

LAYER 7 — PRECISION DETAIL
Transition timing targets (by type):
Focus state design: [ ]
Empty states designed: [ ]
Error states designed: [ ]
Loading states designed: [ ]
Copy review: all strings reviewed against voice/tone: [ ]

GAPS:
Critical:
High:

BRIEF VERSION: [v1.0 / v2.0 / vFinal]
```

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
