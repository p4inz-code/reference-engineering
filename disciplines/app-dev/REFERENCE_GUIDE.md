# App Development — Reference Engineering Guide

Full methodology for gathering, analyzing, and organizing reference across
the complete app development production arc.

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Function & Context

### What to Find

**User task reference:** What does the user open this app to accomplish?
Not what features the app has — what job the user is hiring the app to do.
This distinction matters because apps are judged not by their features
but by how well they accomplish the user's primary task. An app with
twenty features that makes the primary task harder has failed Layer 1.

**Session context reference:** How long is a typical session? How often
does the user open the app? What triggers a session start? A todo app
opened forty times a day in 30-second bursts has different UX requirements
than a video editor opened twice a week for three-hour sessions. The
session pattern is Layer 1 reference that governs navigation design,
onboarding approach, and state management strategy.

**Comparable app reference:** What apps does the target user already have
on their device that solve adjacent or related problems? The user's mental
model of how apps should work is built from their existing apps. Departing
from those models creates friction that must be justified by a specific
advantage. Reference the conventions the user already knows.

**App store review reference:** Reviews of comparable apps in the same
category on the same platform are primary-tier Layer 1 reference. They
tell you what users come for, what frustrates them, and what competing
apps fail to do — all from the users themselves.

### Discipline-Specific Questions

- What is the user's primary task in one sentence?
- How does the user's day look before and after this app session?
- What app do users currently use to accomplish this task? Why isn't it good enough?
- What would cause a user to delete this app within the first week?

---

## Layer 2 — Scale & Proportion

### What to Find

**Screen size and DPI range:** The minimum and maximum screen sizes in
the target device range. The minimum is the constraint — everything must
work there. On mobile: smallest supported device. On desktop: minimum
window size. On Windows: 1366×768 is still the modal screen resolution
in many markets.

**Content hierarchy at minimum size:** Does the primary content fit above
fold at the minimum screen size? Does the primary action remain accessible?
The minimum size is where the hierarchy is tested most harshly.

**Typography minimum sizes:** Platform HIG guidelines specify minimum
text sizes. Apple recommends no smaller than 11pt. Android recommends
no smaller than 12sp. These are Layer 2 constraints on the content
density decisions.

**Density-independent units:** Apps must be designed in density-independent
units (dp on Android, pt on iOS, px at 96dpi on Windows) to remain
consistent across DPI ranges. Reference the conversion at the target
DPI range before designing.

---

## Layer 3 — Production Stage Reference

### App Development Production Stages

| Stage | What You're Building | Reference Needed |
|---|---|---|
| Architecture | Data model, navigation structure, state management | Navigation pattern reference, state management patterns |
| Wireframe | Screen layouts, interaction flows | UI pattern reference for this app category, HIG patterns |
| Visual Design | Component design, design system | Platform HIG, design system reference, comparable apps |
| Implementation | Feature builds, platform integration | Platform API documentation, framework docs |
| QA / Testing | Cross-device, cross-OS validation | Device test matrix, OS version compatibility |
| Store Submission | App store compliance | Store guidelines, screenshot specifications |

### Stage-Appropriate Reference Practice

**At architecture stage:** Gather navigation pattern reference for this
app category. How do comparable apps structure their navigation — tab bar,
drawer, hierarchical, modal? The navigation pattern is an architecture
decision that is expensive to change after implementation begins.

**At visual design stage:** Platform HIG is primary-tier reference.
It is not a suggestion. Apple will reject apps that violate HIG
requirements. Google Play will surface warnings for Material Design
violations. Know what is required before designing against it.

**At implementation stage:** Platform API documentation is the primary
reference. Not tutorials — official documentation. APIs change between
OS versions and tutorials become outdated. The documentation is always
current.

---

## Layer 4 — Governing Rules

### Platform HIG as Layer 4 Reference

Platform Human Interface Guidelines are the most important Layer 4
reference in app development. They are not aesthetic guidelines —
they are behavioral standards that users expect apps on their platform
to follow. Violating them creates friction the user experiences as bugs.

**Apple Human Interface Guidelines (iOS/macOS):**
- Navigation: use platform navigation components (NavigationStack,
  TabView) rather than custom equivalents unless there is explicit reason
- Typography: use Dynamic Type for all text sizes — users with
  accessibility size settings expect apps to respond
- Controls: use standard UIKit/SwiftUI controls for standard tasks
- Gestures: swipe to go back is expected on iOS — implementing a custom
  back button without supporting the swipe gesture breaks a core convention

**Android Material Design 3:**
- Navigation: bottom navigation bar for 3–5 top-level destinations,
  navigation drawer for 6+
- Typography: use Material Type scale — sp units for text, dp for everything else
- Color: implement Material You dynamic color or document why not
- Components: use Material components rather than custom equivalents

**Windows / WPF / WinUI:**
- Title bar: apps that use the full title bar area must handle custom
  title bar correctly across all Windows themes
- Dark mode: system theme changes must be handled — apps that don't
  respond to system theme switch have a visible bug
- Accessibility: Windows Narrator is the primary screen reader — test
  against it specifically

### Written Rules Beyond Platform HIG

Beyond platform compliance, document the app-specific visual rules:
same format as web-dev Layer 4 — numbers, not feelings.

---

## Layer 5 — Contextual Conditions

### OS Version Range

The OS version range is Layer 5 reference that constrains what APIs
are available. An API introduced in iOS 17 is not available on iOS 15.
If 20% of your users are on iOS 15, an iOS 17-only API needs a fallback
or the feature cannot ship.

Before implementation of any feature, document:
- The API or framework feature being used
- The minimum OS version it requires
- The percentage of target users on that OS version or higher
- The fallback behavior for users below the minimum

### Hardware Minimum Specification

The minimum hardware spec is Layer 5 reference that constrains
performance budget. RAM minimum affects how much data can be held
in memory. GPU minimum affects what rendering is achievable.
Storage minimum affects caching strategy.

For mobile: the slowest supported device is the performance target.
If the app runs well on a high-end flagship and poorly on a mid-range
device from three years ago — and mid-range devices from three years ago
are in the target market — the performance is insufficient.

### Permission Model Reference

Every permission the app requests has a user experience cost.
Reference how users respond to permission requests in this app category:
- When is the right moment to request each permission? (not on first launch)
- What is the default denial rate for this permission type?
- What is the degraded-but-functional experience when a permission is denied?

All three questions require reference: app store reviews of comparable
apps discussing permissions, UX research on permission request timing,
platform documentation on permission best practices.

---

## Layer 6 — Framework and OS Behavior

### What to Find

**Framework lifecycle reference:** Every framework has a specific application
lifecycle: launch, active, background, suspend, terminate. The behavior
at each transition must be explicitly designed for. Apps that don't
handle backgrounding correctly lose user data. Apps that don't handle
termination correctly corrupt their state.

**Data persistence behavior:** How does the chosen persistence layer
behave when storage is full? When the write fails? When the app is
terminated mid-write? These are Layer 6 failure mode references.
Every persistence implementation should have documented behavior for
each failure mode — sourced from the persistence layer's documentation.

**Update mechanism behavior:** How does the app update? Auto-update via
store, manual update check, in-app update prompt? What happens to user
data during an update? What happens if the user has the app open during
an update? Document the behavior with reference from the platform's
update mechanism documentation before implementing.

**Inter-app behavior:** Does the app share data with other apps? Accept
shared content from other apps? Integrate with system services (calendar,
contacts, health)? Each integration point has platform-specific behavior
documentation that is primary-tier Layer 6 reference.

---

## Layer 7 — Precision Detail

### What to Find

**Platform animation reference:** Each platform has expected animation
timing and curves for specific interactions. iOS uses spring animations
for most UI transitions. Android uses predictive back gesture animations.
Windows uses system-defined animation curves. Using off-platform animation
timing creates subtle wrongness that users perceive as "something feels off."

**Native component customization limits:** How far can each platform's
native components be customized before they must be replaced with custom
implementations? Knowing the customization limit before designing prevents
designing to a level of customization the platform doesn't support.

**Keyboard and accessibility interaction:** On mobile: how does the keyboard
affect layout? Which interactions require keyboard avoidance? On desktop:
what is the full keyboard interaction model for each component? What do
screen reader users hear when they navigate to each element?

---

## The App Development Reference Brief

```
PROJECT: [app name]
PLATFORM: [iOS / Android / Windows / macOS / cross-platform]
TYPE: [utility / productivity / creative / communication / game / other]
OS VERSION RANGE: min  to  max
DATE: [brief version date]

LAYER 1 — FUNCTION & CONTEXT
Primary user task:
Session frequency and duration:
Comparable apps the user already has:
Top 3 app store review themes (positive):
Top 3 app store review themes (negative):

LAYER 2 — SCALE & PROPORTION
Minimum supported screen size:
Maximum supported screen size:
Content above fold at minimum:
Primary action accessible at minimum:

LAYER 3 — CURRENT STAGE
[ ] Architecture  [ ] Wireframe  [ ] Visual Design  [ ] Implementation  [ ] QA
Stage reference gathered:
Stage gaps:

LAYER 4 — GOVERNING RULES
Platform HIG compliance checklist completed: [ ]
App-specific visual rules (document numbers):
Interaction model: [gestures, navigation pattern, modal strategy]
What this app NEVER does:

LAYER 5 — CONTEXTUAL CONDITIONS
OS version range: min  to  max
Hardware minimum spec:
Permission requirements (list each):
System theme handling: light / dark / both / system-follow
Offline behavior defined:

LAYER 6 — FRAMEWORK & BEHAVIOR
Framework:
App lifecycle: launch / active / background / suspend / terminate — all handled: [ ]
Data persistence layer:
Persistence failure modes documented: [ ]
Update mechanism:

LAYER 7 — PRECISION DETAIL (at implementation stage)
Platform animation timing confirmed:
Keyboard interaction documented:
Screen reader flow tested: [ ]

GAPS:
Critical:
High:
Low:

BRIEF VERSION: [v1.0 / v2.0 / vFinal]
```

---

## When to Re-Run Reference Work

- When the OS version minimum changes
- When a new permission is required
- When a platform releases a major version with new HIG changes
- When the app is ported to a new platform
- When user reviews reveal a systematic expectation mismatch
- When the app category evolves and the competitive landscape changes

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
