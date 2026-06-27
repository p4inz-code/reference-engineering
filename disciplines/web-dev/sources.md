# Web Development — Reference Sources

Best sources for Reference Engineering in web development, by Pyramid layer.

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Function & Context

**Maze / Hotjar / FullStory** — PAID (free tiers)
User research and session recording tools. Primary-tier source for user
task reference when you have access to existing product data.

**G2 / Product Hunt reviews** — FREE
Competitor product reviews written by real users. Excellent for identifying
what users actually come for, what they love, and what frustrates them.
Primary Layer 1 source for competitive analysis — reviews tell you what
the product does for users, not what the marketing page claims.

**Reddit / community forums** — FREE
Search `[product category] reddit` for community discussions. Users discuss
what they actually need, what competitors fail at, and what they wish
existed. Raw but primary-tier user task intelligence.

**StatCounter / SimilarWeb** — FREE / PAID
Traffic source, device distribution, and geographic data for competitor
websites. Layer 1 context of use data.

---

## Layer 2 — Scale & Proportion

**StatCounter GlobalStats** — FREE
Real-world browser, OS, and screen resolution statistics by region and
category. Primary-tier viewport distribution reference. Filter by device
type and region for accurate audience-specific data.

**Screensiz.es** — FREE
Device viewport dimensions organized by device. Quick reference for
standard device sizes when designing breakpoints.

**Chrome DevTools Device Library** — FREE (built into Chrome)
Standard device viewports for simulation. Note: simulation is not
a substitute for real device testing for Layer 5 calibration.

---

## Layer 3 — Stage Reference

**Mobbin** — FREE / PAID
The best organized library of real app and web UI screenshots, organized
by pattern (onboarding, checkout, empty states, etc.) and by platform.
Wireframe and visual design stage reference. Searchable by pattern and
by company.

**Screenlane** — FREE
Web and mobile UI inspiration organized by screen type. Good for
wireframe stage reference — finding structural patterns for specific
interface types.

**Pttrns** — FREE / PAID
Mobile UI pattern library. Good for interaction pattern reference at
prototype stage.

**Codepen** — FREE
Live code examples for interaction patterns, animations, and CSS techniques.
Layer 3 reference for implementation stage — shows how patterns are actually
built, not just what they look like.

---

## Layer 4 — Governing Rules

**Refactoring UI** (book) — PAID
The best resource for extracting visual rules from design decisions.
Covers spacing systems, typography scales, color systems, and shadow
systems with specific, measurable parameters. Primary reference for
building a design system from scratch.

**Material Design 3 / Apple HIG / Fluent Design** — FREE
Platform design systems from Google, Apple, and Microsoft. Primary-tier
reference for platform conventions. Even if not building for a specific
platform, these document why certain patterns exist — useful for
understanding what Layer 4 rules are trying to achieve.

**Every.design / Lookup.design** — FREE
Design system examples from real products (Shopify Polaris, GitHub
Primer, Atlassian, etc.). Compare how different products approach the
same design system decisions. Strong Layer 4 extraction source.

**Contrast Checker (WebAIM)** — FREE
webaim.org/resources/contrastchecker — primary-tier accessibility
reference. Confirm WCAG contrast ratios for every color pairing before
finalizing the color system.

---

## Layer 5 — Contextual Conditions

**Can I Use (caniuse.com)** — FREE
The authoritative source for CSS, HTML, and JavaScript feature support
across browsers. Primary-tier Layer 5 reference for browser behavior.
Check every non-trivial CSS or JS feature against the target browser range
before designing it into the product.

**MDN Web Docs** — FREE
Mozilla Developer Network documentation. Primary-tier reference for
how web platform features actually behave, including browser compatibility
notes. More detailed than Can I Use for behavior differences.

**BrowserStack** — PAID (free tier limited)
Real device and browser testing in the cloud. Primary-tier Layer 5
reference for how the product actually renders on devices not available
locally. Essential for Safari/iOS testing without a Mac.

**WebPageTest** — FREE
Real-world performance testing from multiple geographic locations and
connection types. Primary-tier Layer 5 reference for Core Web Vitals
under real conditions.

**Lighthouse** — FREE (built into Chrome DevTools)
Performance, accessibility, SEO, and best practices audit. Use during
implementation as Layer 5 ongoing reference — run it before every
significant feature ship.

---

## Layer 6 — Framework & Browser Behavior

**Framework Official Documentation** — FREE
Always primary-tier. React docs, Next.js docs, Svelte docs, Vue docs.
Read the framework's own documentation for the feature being implemented
before looking at tutorials or Stack Overflow. Tutorials may be outdated.
Documentation reflects current behavior.

**MDN Compatibility Tables** — FREE
Within MDN documentation, every CSS property and JS API has a compatibility
table. Use these for Layer 6 browser behavior reference, not just Can I Use
(which shows support but not behavior differences).

**Safari / WebKit Bug Tracker** — FREE
bugs.webkit.org — the source of truth for known Safari bugs and their
status. If something isn't working in Safari, check here before spending
time debugging something that is a known bug with a known workaround.

**iOS Safari Quirks (various resources)** — FREE
Search `iOS Safari [feature] bug` for documented quirks. Community
resources on GitHub (e.g., "ios-safari-viewport-units-fix") document
known issues and standard workarounds. This is the most consistently
underresearched browser in web development.

---

## Layer 7 — Precision Detail

**Easings.net** — FREE
Visual reference for animation easing functions. See what each easing
curve looks like in motion before using it. Primary-tier reference for
deciding which easing is appropriate for which type of interaction.

**Material Motion** — FREE
Google's motion design guidelines with documented timing and easing
recommendations by interaction type. Layer 7 reference for animation
system decisions.

**Axe DevTools / WAVE** — FREE
Browser extensions for accessibility testing. Primary-tier reference
for Layer 7 accessibility precision. Run on every component before
marking it complete.

**Copy / UX Writing Resources:**
- UX Writing Hub — FREE — UX copy patterns and examples
- Microsoft Writing Style Guide — FREE — tone and voice reference
- Shopify Polaris Content Guidelines — FREE — specific copy patterns for
  e-commerce contexts

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
