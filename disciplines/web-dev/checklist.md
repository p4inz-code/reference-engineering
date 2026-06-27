# Web Development — Reference Engineering Checklist

Run before writing code. Run again at each production stage.
Mark: ✓ Complete / ~ Partial / ✗ Missing / N/A Not applicable

---

## DISCOVERY / PRE-DESIGN

### Layer 1 — Function & Context
- [ ] Primary user task written in one sentence (not what the page does — what the user accomplishes)
- [ ] User context of use defined (device, environment, emotional state, intent)
- [ ] Top 3 competitive references analyzed for structure, not just appearance
- [ ] Anti-reference documented — what this product must NOT do

### Layer 2 — Information Hierarchy
- [ ] Target viewport distribution documented (analytics or category benchmark)
- [ ] Primary breakpoints confirmed
- [ ] Above-fold content defined at primary mobile viewport
- [ ] Information hierarchy established: primary / secondary / tertiary

---

## WIREFRAME STAGE

- [ ] Structural reference gathered (layout patterns, navigation models)
- [ ] No visual style reference introduced at this stage
- [ ] Wireframe answers: does this layout serve the user task?
- [ ] Navigation model validated against competitive reference
- [ ] Content hierarchy visible in wireframe without styling

---

## VISUAL DESIGN STAGE

### Layer 4 — Governing Rules
- [ ] Typography scale documented with exact values (rem sizes, line heights, weights)
- [ ] Color system documented with hex values and contrast ratios
- [ ] Spacing base unit defined and documented
- [ ] Interactive states designed: hover, focus, active, disabled
- [ ] Focus states explicitly designed (not "default browser" as the answer)
- [ ] Written rules exist before first component is built
- [ ] Rules sourced from minimum 3 competitive references
- [ ] "What this interface NEVER does" list written

### Layer 5 — Contextual Conditions
- [ ] WCAG contrast ratios confirmed for all text/background combinations
- [ ] Touch target minimum size confirmed (44×44px minimum)
- [ ] Typography readable at minimum at primary mobile viewport + viewing distance
- [ ] Dark mode considered (required or optional — decision documented)

---

## IMPLEMENTATION STAGE

### Layer 6 — Framework & Browser Behavior
- [ ] Framework defaults documented for each component type used
- [ ] Component library override cost assessed before designing against defaults
- [ ] Target browser range confirmed
- [ ] Known quirks for each browser in target range documented
- [ ] CSS features used checked against Can I Use for target range
- [ ] Safari tested on real device or verified emulator (not just Chrome devtools)
- [ ] iOS Safari tested for any input, scroll, or touch interaction

### Layer 5 — Performance Context
- [ ] CWV targets documented: LCP  CLS  INP
- [ ] Image size budget established from LCP target
- [ ] JavaScript bundle budget established from INP target
- [ ] Font loading strategy defined
- [ ] Third-party script impact assessed

### Accessibility
- [ ] All interactive elements keyboard-navigable
- [ ] Focus order logical and documented
- [ ] Images have appropriate alt text
- [ ] Form inputs have explicit labels
- [ ] Error messages programmatically associated with inputs
- [ ] Dynamic content changes announced to screen readers

---

## PRE-LAUNCH / QA

- [ ] Tested at actual viewport range (not just at breakpoints)
- [ ] Tested on minimum 2 real devices (or verified BrowserStack equivalent)
- [ ] Lighthouse score run and documented
- [ ] CWV targets met or gap documented with plan
- [ ] Accessibility audit run (axe DevTools minimum)
- [ ] Brief vFinal written with lessons for next project

---

## COMMON GAPS IN WEB DEVELOPMENT

| Project Type | Most Commonly Missing |
|---|---|
| Marketing landing page | Layer 1 (conversion task), Layer 5 (mobile device calibration) |
| SaaS / web app | Layer 6 (framework constraints), Layer 4 (design system rules) |
| E-commerce | Layer 5 (performance / CWV), Layer 1 (purchase intent task) |
| Portfolio / personal site | Layer 2 (viewport range), Layer 4 (consistent rules) |
| Internal tools | Layer 5 (accessibility), Layer 1 (actual user workflow) |
| API documentation | Layer 2 (code block density), Layer 7 (copy precision) |

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
