# UI Redesign — Reference Engineering Process

This document covers both the reference board (what was gathered and why) and the analysis (extracted rules, gap audit). Together they constitute the Reference Engineering process for this project.

**Brief version:** 1.0
**Stage:** Pre-production / wireframe stage
**Reference gathered:** 2026-06-22

Every item on this board answers a specific question from `01_brief.md`.
Items not answering a question from the brief are not on this board.

---

## Layer 1 — Function & Context Reference

### User Task Flow Reference

**Bloomberg Terminal — Session Entry Pattern**
*Answers: "What does a financial analyst do in the first 60 seconds?"*
Observation: Bloomberg opens to the last active screen, not a home dashboard.
Power users do not want a "start here" dashboard — they want to resume.
Implication: Our dashboard should support session resume, not force a
home-screen overview every entry.
Hierarchy tier: Primary (real product, real users in our target category)

**Refinitiv Eikon — Overview Screen Layout**
*Answers: "What does a portfolio manager need to see without scrolling?"*
Observation: Watchlist, key movers, and news are always above fold.
Specific data (P&L, allocation breakdown) is below fold but accessible in one scroll.
Implication: Three primary data types above fold maximum. Everything else is one scroll or one click.
Hierarchy tier: Primary

**User interview synthesis — [from stakeholder brief]**
*Answers: "What are the two decisions this dashboard makes easier?"*
— "Is anything in my portfolio moving unusually today?" (alert/anomaly detection)
— "Is my overall exposure where I intend it to be?" (portfolio balance check)
These are the two Layer 1 questions. Everything else is secondary.
Hierarchy tier: Primary

---

## Layer 2 — Scale & Proportion Reference

### Information Hierarchy Reference

**Grafana (data monitoring dashboard)**
*Answers: "What layout pattern handles summary metrics + detailed charts?"*
Observation: Top row = KPI summary cards (4–6 numbers). Middle section = primary chart.
Bottom section = detail tables. This pattern repeats across every major
data dashboard regardless of domain.
Extracted rule: KPI row → primary visualization → detail — this is the standard
reading order for data dashboards. Deviation requires strong justification.
Hierarchy tier: Secondary (monitoring, not fintech, but information architecture is analogous)

**Datadog — Widget density**
*Answers: "What is the secondary data density standard?"*
Observation: 4 primary widgets visible at 1440px. 8 secondary items in sidebar.
Maximum readable widget count at standard viewing distance: 6 primary data points.
Hierarchy tier: Secondary

**Viewport analysis — StatCounter data for B2B SaaS**
*Answers: "What viewport sizes cover 90% of target users?"*
B2B SaaS users: 1920×1080 (38%), 1440×900 (24%), 1280×800 (18%) = 80% of use.
Design primary for 1440px. Ensure nothing breaks below 1280px.
Hierarchy tier: Tertiary → upgrade to Primary if client can provide analytics

---

## Layer 3 — Production Stage Reference (Wireframe)

### Navigation Model Reference

**Stripe Dashboard — Navigation pattern**
*Answers: "What navigation model does the category leader use?"*
Pattern: Left sidebar with icon + label, collapsible to icon-only.
Primary content always full-width right of sidebar.
No top navigation bar competing with content.
Applicable: Yes — our users navigate between portfolio sections similarly to
how Stripe users navigate between financial reporting sections.
Hierarchy tier: Secondary

**Robinhood — Overview to drill-down**
*Answers: "How do top competitors handle overview → drill-down?"*
Pattern: Summary card with key metric visible. Click card → detail slide-in panel.
No page navigation. Context preserved.
Observation: Works well for single-asset drill-down. Fails for comparison views.
Our use case requires comparison — this pattern does NOT transfer.
Hierarchy tier: Primary (direct competitor category), but pattern does not apply.

**Morningstar Portfolio — Drill-down pattern**
*Answers: "How do top competitors handle overview → drill-down?" (alternative)*
Pattern: Table row → expanded detail inline. Comparison is native.
Applicable: Yes — better fit for our use case than Robinhood's slide-in.
Hierarchy tier: Primary

---

## Layer 4 — Style Rules Reference

### "Authoritative" Visual Language Reference

**Reference set: Bloomberg, Refinitiv, FactSet, Morningstar**
*Answers: "What visual parameters define 'authoritative' in this category?"*

Extracted rules from analysis of all four:
- Typography: monospace or semi-condensed for data values. Proportional for labels.
- Color: Neutral base (dark navy or warm gray). One accent. Green/red for positive/negative.
- Grid: Dense. High information-per-pixel ratio. No decorative white space.
- Charts: Line charts dominant. No 3D. No gradients on bars. Grid lines always visible.
- Iconography: Minimal. Functional only. No decorative icons.

What this style NEVER does:
- No rounded corners on data containers (squares = precision)
- No illustration or photography in the UI
- No gradients on data values
- No animation except data loading states
- No more than 2 typefaces

Hierarchy tier: Primary (direct category competitors — rules are consistent across all four)

**Reference set: Palantir AIP, Hex (data notebooks)**
*Answers: "Where does 'modern' end and 'flashy' begin in this category?"*

Observation: Palantir uses subtle grid overlays and small geometric UI elements.
Hex uses color-coded cell types. Both read as "modern" not "flashy."
The line: decoration that communicates information = modern.
Decoration that exists for aesthetics = flashy.
Hierarchy tier: Secondary (adjacent tools, not direct competitors)

---

## Layer 5 — Display Context Reference

### Display Condition Reference

**Office display environment — lighting study**
*Answers: "What is the primary ambient lighting condition?"*
B2B office environments: fluorescent overhead + screen. High ambient light.
Implication: Light mode is primary. Dark mode is secondary (for home use / preference).
Base design in light mode. Dark mode adaptation required.
Hierarchy tier: Tertiary → confirm with client user research

**Financial data color standards**
*Answers: "Are there display calibration standards financial users expect?"*
Industry conventions (Bloomberg-established, now universal):
— Green = positive / gain
— Red = negative / loss
These are not conventions — they are expectations. Deviation causes user error.
Yellow = alert/warning (also standard). Blue = neutral/informational.
This is non-negotiable. Reference tier: Primary convention.

---

## Items Considered and Excluded

| Item | Why excluded |
|---|---|
| Apple Finance app screenshots | Consumer product, different information density requirements |
| Pinterest "dashboard design" inspiration | Decorative reference, no extractable rules for this product category |
| Crypto trading platform UI | Wrong trust register — this category actively signals "excitement" which is opposite of our target |

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
# UI Redesign — Analysis & Gap Audit

**Brief version:** 1.0 → 1.1 (post-analysis)
**Stage:** Pre-production → wireframe-ready

---

## Extracted Rules

The following rules are derived from the reference board. These are the
written parameters that will govern every design decision downstream.
Anyone on the team should be able to make consistent decisions from
these rules without referring to the reference board.

### Information Architecture Rules

1. Maximum 3 primary data points above the fold at 1440px
2. KPI summary row → primary visualization → detail table. This reading
   order is the standard for data dashboards. Deviation requires written justification.
3. Navigation: left sidebar, icon + label, collapsible to icon-only
4. Drill-down pattern: inline expansion (not slide-in panel) to preserve
   comparison capability
5. Session resume: open to last active screen, not force-home on entry

### Typography Rules

1. Data values: monospace or semi-condensed typeface
2. Labels and body: proportional typeface
3. Maximum 2 typefaces across the entire product
4. Minimum readable size at 1440px standard viewing distance: 12px data, 14px label

### Color Rules

1. Base: neutral (dark navy or warm gray — decision pending client approval)
2. Accent: one color, used for primary interactive elements only
3. Positive/gain: green (not negotiable — industry convention)
4. Negative/loss: red (not negotiable — industry convention)
5. Alert/warning: yellow
6. Informational: blue
7. No gradients on data values or data containers

### Visual Style Rules

1. Data containers: rectangular, no rounded corners
2. No illustration or photography anywhere in the UI
3. No animation except loading states and data updates
4. Chart type hierarchy: line charts primary, bar charts secondary, no 3D, no pie
5. Grid lines always visible on charts (precision convention)
6. Iconography: functional only, no decorative icons

### What This Design Never Does

- Rounded corners on data containers
- Gradients on data values
- More than 2 typefaces
- Decorative white space (white space is earned by information density, not added for aesthetics)
- Pie charts
- 3D chart types
- Illustration or photography in the UI

---

## Gap Audit

Questions from the brief that remain unanswered after the reference board.

### Critical Gaps (must resolve before wireframes)

**GAP 01: Primary user task is partially unclear**
We know the two key questions users need to answer (anomaly detection,
exposure check). We do not know the specific data that answers each question
for this product's data model.
*Resolution needed from:* Product/engineering, to understand what data is available
*Blocking:* KPI row content and information hierarchy

**GAP 02: Viewport distribution not confirmed**
Industry benchmark data used (StatCounter B2B SaaS). Client analytics
may differ. If client's users skew to 4K displays, density assumptions change.
*Resolution needed from:* Client analytics data
*Blocking:* Grid density and widget sizing

### High Priority Gaps (resolve before mockup stage)

**GAP 03: Component library/framework not specified**
Cannot assess constraint layer (Layer 6) without knowing the framework.
*Resolution needed from:* Engineering
*Not blocking wireframes but blocking:* Mockup-stage decisions

**GAP 04: Light/dark mode priority not confirmed**
Used industry assumption (light mode primary for office B2B use).
Needs client confirmation.
*Resolution needed from:* Client
*Not blocking wireframes but blocking:* Color system decisions at mockup stage

### Low Priority Gaps (resolve before delivery)

**GAP 05: Empty states and error states undefined**
Deferred to Brief v2 (mockup stage). Not needed for wireframes.

**GAP 06: Mobile breakpoint requirements unknown**
B2B financial analysts likely desktop-primary. Confirm before investing in
responsive breakpoints.

---

## Reference Hierarchy Audit

| Decision | Tier used | Confidence | Validation needed? |
|---|---|---|---|
| Green/red for positive/negative | Primary (industry convention) | High | No |
| KPI row → chart → detail layout | Secondary (Grafana, Datadog) | High | Confirm with user testing |
| Left sidebar navigation | Secondary (Stripe) | Medium | Confirm with user research |
| Inline drill-down (not slide-in) | Primary (Morningstar) | High | No |
| Light mode primary | Tertiary (industry assumption) | Low | YES — get client data |
| Viewport 1440px primary | Tertiary (StatCounter benchmark) | Low | YES — get client analytics |

---

## Brief v1.1 Updates

Added after analysis:

- Rule: Drill-down is inline, not slide-in (based on comparison requirement)
- Rule: Session resume to last screen (based on Bloomberg observation)
- Gap flagged: Primary user task data model needs product clarification
- Deferred: Layer 7 questions to Brief v2 at mockup stage

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
