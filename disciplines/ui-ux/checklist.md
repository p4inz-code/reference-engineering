# UI/UX Design — Reference Engineering Checklist

Run at each design stage. Each stage has its own reference requirements.
Mark: ✓ Complete / ~ Partial / ✗ Missing / N/A Not applicable

---

## RESEARCH STAGE

### Layer 1 — User Task and Mental Model
- [ ] Primary user task defined in one sentence (outcome, not feature)
- [ ] User mental model documented (what comparable products shape expectations)
- [ ] Top 3 failure modes in comparable products documented
- [ ] Emotional register on arrival documented
- [ ] Success criterion defined (how user knows task is complete)

### Layer 2 — Minimum Viable Interaction
- [ ] Step count to complete primary task in best comparable product counted
- [ ] Step count target set for this product
- [ ] Information hierarchy drafted: primary / secondary / tertiary

---

## INFORMATION ARCHITECTURE STAGE

- [ ] Navigation model chosen and referenced against comparable products
- [ ] Content organization validated against user mental model
- [ ] All primary tasks reachable in ≤3 navigation steps
- [ ] IA tested with card sort or equivalent (if budget allows)
- [ ] No design system or visual reference introduced at this stage

---

## WIREFRAME STAGE

- [ ] Wireframes evaluable on function alone (no visual distraction)
- [ ] Primary task completion path clear without explanation
- [ ] Information hierarchy visible in wireframe layout
- [ ] All states represented: loaded / loading / empty / error
- [ ] Interaction flows documented for all non-obvious interactions

---

## VISUAL DESIGN STAGE

### Layer 4 — Design System Rules
- [ ] Typography scale documented with exact values (px, rem, line-height, weight)
- [ ] Color system documented with hex values and WCAG contrast ratios
- [ ] Spacing base unit defined
- [ ] Border radius system defined
- [ ] Interactive state rules: hover, focus, active, disabled — all components
- [ ] "What this design NEVER does" list written
- [ ] Rules validated against minimum 3 comparable products

### Layer 5 — Accessibility Standards
- [ ] All text contrast ratios: minimum 4.5:1 (normal), 3:1 (large)
- [ ] Focus states designed for all interactive elements
- [ ] Touch targets: minimum 44×44px hit area
- [ ] Animation: prefers-reduced-motion behavior defined
- [ ] Text scaling: layout stable at 200% text size

### Platform Conventions
- [ ] Platform HIG requirements checked for target platform
- [ ] Convention departures documented with rationale
- [ ] Onboarding investment planned for each convention departure

---

## PROTOTYPE STAGE

- [ ] Interaction timing documented per interaction type (ms)
- [ ] Easing curves specified per interaction type
- [ ] All states prototyped (not just happy path)
- [ ] Prototype tested with keyboard navigation
- [ ] Prototype tested with screen reader (VoiceOver / TalkBack)

---

## USER TESTING STAGE

- [ ] Task completion rate measured against comparable product benchmarks
- [ ] Time-on-task measured for primary task
- [ ] Error rate documented
- [ ] Convention departures specifically tested — do users discover them?
- [ ] Brief updated with user testing findings before implementation handoff

---

## DELIVERY / IMPLEMENTATION HANDOFF

### Layer 7 — Precision Detail
- [ ] All states specified: empty, loading, error, success, partial
- [ ] All edge cases documented: zero items, maximum items, long text
- [ ] Copy reviewed: all strings follow voice/tone guidelines
- [ ] Animation specs complete: duration, easing, trigger, direction
- [ ] Focus order documented for all screens
- [ ] Design tokens documented (not hardcoded values)

### Implementation Validation
- [ ] Contrast ratios verified in implementation (not just in Figma)
- [ ] Keyboard navigation tested in implementation
- [ ] Screen reader tested in implementation
- [ ] Component compliance verified against design system

---

## COMMON GAPS BY PRODUCT TYPE

| Product Type | Most Commonly Missing |
|---|---|
| Consumer mobile app | Layer 1 (task vs. feature focus), Layer 7 (empty states) |
| SaaS / B2B web app | Layer 5 (accessibility), Layer 4 (design system enforcement) |
| Enterprise tool | Layer 1 (expert user mental model), Layer 2 (data density standards) |
| E-commerce | Layer 1 (purchase intent task), Layer 7 (error state for payment) |
| Onboarding flow | Layer 1 (mental model on arrival), Layer 7 (copy precision) |
| Settings / preferences | Layer 2 (information hierarchy), Layer 7 (empty and confirmation states) |

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
