# UI Redesign — Outcome & Decisions

**Brief version:** 1.1
**Stage:** Wireframe-ready
**Decision log:** Every decision below traces to a specific rule from `03_analysis.md`

---

## Layout Decisions

**D01 — Information hierarchy: KPI row + chart + detail**
Adopted from extracted rule 2. No deviation — standard is well-established
across the category and aligns with Layer 1 user task findings.
*Reference: Grafana (secondary), Datadog (secondary), confirmed by Layer 1 user task analysis*

**D02 — Above-fold content: 4 KPI cards**
3 primary data points (rule 1) + 1 alert indicator.
KPIs: Portfolio value, Daily P&L, Largest mover, Anomaly count.
These directly answer the two Layer 1 questions: "is anything moving unusually"
(anomaly count) and "is my exposure correct" (portfolio value, P&L, largest mover).
*Reference: Layer 1 user interview synthesis (primary)*

**D03 — Navigation: Left sidebar, collapsible**
Adopted from extracted rule — sidebar with icon + label, collapses to icon-only.
Sidebar items: Overview, Portfolio, Alerts, Reports, Settings.
*Reference: Stripe Dashboard (secondary)*

**D04 — Drill-down: Inline expansion**
Table row click → row expands inline with detail panel.
Comparison is preserved because both rows remain visible.
Slide-in panel rejected (Robinhood pattern) — breaks comparison workflow.
*Reference: Morningstar Portfolio (primary)*

**D05 — Session resume**
Application opens to last active screen. No forced home dashboard on entry.
Home dashboard accessible via Overview nav item.
*Reference: Bloomberg Terminal observation (primary)*

---

## Typography Decisions

**D06 — Typeface pairing**
Data values: IBM Plex Mono (monospace, free, excellent at small sizes)
Labels and body: Inter (proportional, industry-standard for SaaS)
Two typefaces, no deviation from rule.
*Reference: Category analysis style rules (primary)*

**D07 — Minimum sizes**
Data values: 12px minimum
Labels: 14px minimum
Headers: 16px
Section labels: 11px uppercase (exception: labels are contextual, not data)
*Reference: Viewing distance analysis (tertiary — validate with accessibility audit)*

---

## Color Decisions

**D08 — Base palette (light mode)**
Background: #F8F9FA (warm gray, not white — reduces eye strain at desk)
Surface: #FFFFFF (card/widget backgrounds)
Border: #E2E8F0 (light, precise grid feel)
Text primary: #1A202C (near-black, high contrast)
Text secondary: #718096

**D09 — Data colors (non-negotiable)**
Positive/gain: #22543D / #38A169 (dark/light green pair)
Negative/loss: #742A2A / #E53E3E (dark/light red pair)
Alert: #744210 / #DD6B20 (dark/light amber pair)
Informational: #2A4365 / #3182CE (dark/light blue pair)
*Reference: Bloomberg convention (primary — industry standard)*

**D10 — Accent color**
#3182CE (blue). Exclusive to interactive primary actions.
Not used for data representation — blue is reserved for informational data.
Interactive blue is distinguished from data blue by saturation and context.

---

## Visual Style Decisions

**D11 — Data containers: rectangular**
Border-radius: 4px maximum on container cards (structural, not decorative).
Data cells within containers: 0px radius.
*Reference: Style rule — no rounded corners on data containers*

**D12 — Charts: line primary, bar secondary**
P&L over time: line chart
Allocation breakdown: horizontal bar (not pie)
Comparison: grouped bar
All charts: grid lines always visible (1px, #E2E8F0)
No 3D. No gradients.
*Reference: Category analysis style rules (primary)*

**D13 — Iconography**
Feather Icons set (MIT license, clean, functional, no decoration).
Size: 16px in sidebar, 14px in inline contexts.
No decorative use.
*Reference: Style rule — functional icons only*

---

## Decisions Deferred to Brief v2 (Mockup Stage)

| Decision | Reason deferred | When to resolve |
|---|---|---|
| Micro-interaction specs | Layer 7 — not needed for wireframes | Mockup stage |
| Loading state designs | Layer 7 — not needed for wireframes | Mockup stage |
| Dark mode color palette | Gap 04 not resolved — needs client input | After client confirmation |
| Mobile breakpoints | Gap 06 not resolved — needs client input | After client confirmation |

---

## Decisions NOT Made (and Why)

| Not decided | Why |
|---|---|
| Specific KPI data fields | Gap 01 unresolved — needs product data model |
| Grid density at 4K | Gap 02 unresolved — needs client analytics |
| Component library | Gap 03 unresolved — needs engineering input |

These are not style decisions. They are not made here. They are flagged
as open and tracked until resolved.

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
