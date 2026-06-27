# UI/UX Design — Reference Sources

Best sources for Reference Engineering in UI/UX design, by Pyramid layer.

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — User Task and Mental Model

**App Store / Google Play reviews of comparable products** — FREE
Primary-tier user task and failure mode reference. The 2–3 star reviews
tell you what users came for, what worked, and what didn't. More useful
than user research reports for competitors — it's direct user voice.

**Hotjar / FullStory / Microsoft Clarity** — FREE / PAID
Session recording and heatmap tools. If you have access to data from
an existing product, these are primary-tier Layer 1 reference for
understanding how real users actually navigate.

**Reddit / community forums** — FREE
Search `[product category] reddit` for user discussions about comparable
products. Users articulate their mental models ("I expected it to work
like X"), their frustrations, and what they actually use the product for.

**Jobs to Be Done interviews** — PRIMARY METHOD
Structured user interviews focused on the job the user hires the product
to do. The JTBD framework is a reference methodology for Layer 1 research.
Resources: Bob Moesta's writing, JTBD interviews on YouTube.

---

## Layer 2 — Information Hierarchy

**Baymard Institute** — PAID (significant free content)
baymard.com — the most comprehensive research database for e-commerce
and web UI patterns. Research reports cite specific failure rates and
user behavior data. Primary-tier for e-commerce Layer 2 reference.
Their free articles contain significant actionable content.

**Nielsen Norman Group** — PAID (significant free content)
nngroup.com — user research and UX guidelines from the field's leading
research organization. Reports cite user study data. Free articles cover
foundational patterns. Primary-tier for pattern validation.

**Laws of UX** — FREE
lawsofux.com — documented cognitive psychology principles that govern
UI behavior (Hick's Law, Fitts's Law, Miller's Law). Primary-tier for
understanding why specific information hierarchy decisions work.

---

## Layer 3 — Stage Reference

**Mobbin** — FREE / PAID
mobbin.com — organized UI screenshot library, filterable by platform,
app category, and screen type (onboarding, checkout, settings, empty states).
The best organized source for stage-appropriate UI reference.
Use at wireframe stage for layout patterns, visual design stage for
component treatment.

**Screenlane** — FREE
screenlane.com — web and mobile UI organized by screen type and interaction.
Good for wireframe stage reference.

**Pttrns** — FREE / PAID
pttrns.com — mobile UI pattern library. Organized by pattern type.
Good for interaction pattern research at prototype stage.

**UI Patterns** — FREE
ui-patterns.com — documented UI design patterns with explanation of
when to use each. Good for IA and wireframe stage reference.

---

## Layer 4 — Governing Rules

**Refactoring UI** (book) — PAID
Adam Wathan and Steve Schoger. The definitive resource for extracting
visual rules from design. Covers spacing systems, type scales, color
systems. Every recommendation is specific with exact values. Primary Layer 4 reference.

**Apple Human Interface Guidelines** — FREE
developer.apple.com/design — required reading for any iOS or macOS product.
Primary-tier, non-optional for Apple platforms. Also a strong general
reference for component behavior and platform conventions.

**Material Design 3** — FREE
m3.material.io — required reading for Android products. Also widely used
as a general design system reference. Specific values for component sizing,
spacing, and color are documented.

**Every.design / Lookup.design** — FREE
Design system examples from real products. Compare Shopify Polaris,
GitHub Primer, Atlassian, IBM Carbon side-by-side. Strong for extracting
written rules from production design systems.

**Design Systems Repo** — FREE
designsystems.com — collection of public design systems with documentation.
Primary-tier reference for understanding how production design systems
document their rules.

---

## Layer 5 — Contextual Conditions

**WebAIM Contrast Checker** — FREE
webaim.org/resources/contrastchecker — the standard tool for WCAG
contrast ratio verification. Primary-tier for accessibility compliance.

**WCAG 2.1 Guidelines** — FREE
w3.org/TR/WCAG21 — the official accessibility standard documentation.
Primary-tier for understanding requirements, not just checking compliance.

**Colour Contrast Analyser (TPGi)** — FREE
tpgi.com/color-contrast-checker — desktop tool for checking contrast
in designs and on screen. Useful for checking contrast of rendered
interfaces, not just hex values.

**StatCounter** — FREE
gs.statcounter.com — device and display statistics by region. Primary-tier
for understanding the actual device range of the target audience.

**BrowserStack** — PAID (free tier limited)
Real device and browser testing. Primary-tier for validating design
decisions under real display conditions across the target device range.

---

## Layer 6 — Component and Interaction Behavior

**Radix UI / shadcn/ui / Headless UI documentation** — FREE
Headless component library documentation. Documents default accessibility
behavior, focus management, keyboard interaction. Primary-tier for
understanding what component libraries provide before designing against them.

**Framer Motion documentation** — FREE
framer.com/motion — animation library documentation including easing
function reference and performance guidance. Layer 6 reference for
animation capability and constraints.

**Can I Use** — FREE
caniuse.com — CSS and JS feature support across browsers. Layer 6 reference
for what is buildable in the target browser range.

---

## Layer 7 — Precision Detail

**Easings.net** — FREE
Visual reference for animation easing functions. Primary-tier for choosing
the correct easing for each interaction type.

**Material Motion** — FREE
m3.material.io/styles/motion — specific timing and easing values for
UI interactions. Primary-tier animation timing reference.

**UX Writing Hub** — FREE
uxwritinghub.com — UX copy patterns, error message templates, empty
state copy examples. Layer 7 reference for copy precision.

**Nielsen Norman Group: Error Message Guidelines** — FREE (article)
nngroup.com — research-backed guidelines for error message copy.
Primary-tier for error state copy reference.

**Accessible Name and Description Computation** — FREE
w3.org — technical reference for how screen readers compute accessible
names. Primary-tier for Layer 7 accessibility precision.

**VoiceOver / TalkBack** — FREE (platform built-in)
The actual screen readers used by target users. Primary-tier Layer 7
reference for accessibility — there is no substitute for testing with
the actual assistive technology.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
