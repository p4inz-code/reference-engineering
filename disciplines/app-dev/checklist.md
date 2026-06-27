# App Development — Reference Engineering Checklist

Run before writing code. Run again at each production stage.
Mark: ✓ Complete / ~ Partial / ✗ Missing / N/A Not applicable

---

## PRE-PRODUCTION

### Layer 1 — Function & Context
- [ ] Primary user task written in one sentence
- [ ] Session frequency and duration documented
- [ ] Top 3 comparable apps identified and analyzed
- [ ] App store reviews of comparable apps reviewed (Layer 1 primary reference)
- [ ] What causes users to delete comparable apps — documented

### Layer 2 — Scale & Proportion
- [ ] Minimum supported screen size confirmed
- [ ] Maximum supported screen size confirmed
- [ ] Primary viewport at minimum size — does primary content fit?
- [ ] Primary action reachable at minimum size without scrolling?
- [ ] Density-independent units confirmed for design

### Layer 4 — Governing Rules
- [ ] Target platform HIG read (not summarized — read)
- [ ] HIG requirements applicable to this app type listed
- [ ] Navigation pattern chosen and documented (reference: platform HIG)
- [ ] Interaction gestures documented (reference: platform standards)
- [ ] App-specific visual rules documented with numbers
- [ ] "What this app NEVER does" list written

### Layer 5 — Contextual Conditions
- [ ] OS version minimum confirmed against market distribution data
- [ ] Hardware minimum spec confirmed
- [ ] Permission requirements listed (every permission the app will request)
- [ ] Permission timing strategy documented (just-in-time, not upfront)
- [ ] System theme handling defined: light / dark / both / system-follow
- [ ] Offline behavior defined for every network-dependent feature
- [ ] Connectivity failure state defined

---

## ARCHITECTURE STAGE

- [ ] Navigation structure validated against comparable apps
- [ ] App lifecycle states documented (launch / active / background / suspend / terminate)
- [ ] State persistence defined: what is persisted, when, and how?
- [ ] State persistence failure modes documented
- [ ] Data model accounts for offline state
- [ ] Update mechanism defined and documented

---

## VISUAL DESIGN STAGE

- [ ] Platform HIG color usage requirements confirmed
- [ ] Semantic color tokens created (not hardcoded values)
- [ ] Dark mode color tokens defined alongside light mode
- [ ] Typography uses platform Dynamic Type (or equivalent) for accessibility
- [ ] Touch targets minimum 44×44pt (iOS) or 48×48dp (Android)
- [ ] Tap target spacing minimum 8pt to prevent accidental taps
- [ ] Focus and selection states designed for all interactive elements
- [ ] Loading states designed for all asynchronous operations
- [ ] Error states designed for all failure modes
- [ ] Empty states designed for all lists and content areas

---

## IMPLEMENTATION STAGE

- [ ] All platform APIs used checked for minimum OS version requirement
- [ ] Fallback behavior implemented for APIs not available on minimum OS
- [ ] App lifecycle transitions tested (background → foreground restores correct state)
- [ ] Low-memory termination tested (state is correctly restored on relaunch)
- [ ] System theme change tested while app is running
- [ ] Permission denial tested — app functions correctly in degraded state
- [ ] Offline state tested — app handles connectivity loss gracefully
- [ ] Framework used per documentation — no patterns from outdated tutorials

---

## QA / PRE-SUBMISSION

- [ ] Tested on minimum supported device (not only development device)
- [ ] Tested on minimum supported OS version
- [ ] Dark mode tested
- [ ] Accessibility tested with platform screen reader (VoiceOver / TalkBack / Narrator)
- [ ] All permissions tested: grant, deny, and revoke mid-session
- [ ] All error states triggered and verified
- [ ] App Store / Play Store guidelines reviewed — all requirements met
- [ ] Privacy policy URL confirmed
- [ ] Required platform disclosures included
- [ ] App store screenshots at required sizes prepared

---

## COMMON GAPS IN APP DEVELOPMENT BY PLATFORM

| Platform | Most Commonly Missing |
|---|---|
| iOS | Dark mode (Layer 5), Dynamic Type (Layer 4), swipe-back gesture (Layer 4) |
| Android | Material You dynamic color (Layer 4), back gesture handling (Layer 6) |
| Windows (.NET/WPF) | System theme handling (Layer 5), DPI scaling (Layer 2) |
| Electron | OS-appropriate menus (Layer 4), system theme (Layer 5), auto-update (Layer 6) |
| React Native | Platform-specific behavior divergence (Layer 6), performance on Android (Layer 5) |
| Flutter | Platform convention compliance (Layer 4), accessibility (Layer 7) |

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
