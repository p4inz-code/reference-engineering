# App Development — Reference Engineering Mistakes

Eight failure modes specific to app development reference practice.

---

## MISTAKE 01 — Platform Convention Blindness

> *"Users will figure out our custom navigation."*

**Symptom:** Users rate the app low for "confusing" or "hard to use" despite
the UI being internally consistent. Support tickets about basic navigation.
Users can't find features that are clearly present. App store reviews mention
the app "doesn't feel right" or "feels weird" without specifying why.

**Cause:** Layer 4 (Governing Rules) reference was absent for platform HIG
requirements. Navigation, gesture, and interaction conventions were designed
from first principles rather than from platform standards. Users have strong
implicit expectations from every other app on their device. An app that
violates those expectations creates friction proportional to how far it departs.

**Fix:** Before any wireframe is drawn, read the full HIG for the target
platform for the specific app category. Not a summary — the actual documentation.
Document every HIG requirement that applies to this app. Design to the
requirement, not around it.

**Production cost:** Navigation redesign after user research reveals
convention violations. If the navigation architecture is wrong, this is
a major refactor. Time lost: 1–3 weeks depending on app complexity.

---

## MISTAKE 02 — The Wrong OS Version Target

> *"We'll just require the latest OS."*

**Symptom:** App has a small addressable market because the OS minimum
requirement excludes a significant portion of the target audience.
Alternatively: app targets a wide OS range but uses APIs only available
on newer OS versions, producing crashes on older devices.

**Cause:** Layer 5 (Contextual Conditions) reference — specifically OS
version distribution for the target market — was not gathered. The OS
version requirement was set from convenience (what the developer uses)
or from ambition (only supporting the newest features) rather than from
market data.

**Fix:** Before setting the OS minimum, look up the OS version distribution
for the target market and app category. For iOS: Apple publishes adoption
statistics. For Android: Android Studio shows Play Store distribution data.
The minimum should cover 85–90%+ of the target market unless there is
explicit justification for a higher minimum.

**Production cost:** Rewriting features to support a broader OS range
after the market research is done post-launch. In some cases, the API
choice made for the initial OS target cannot be backported and requires
a complete feature reimplementation.

---

## MISTAKE 03 — Permission Timing Failure

> *"We ask for all permissions on first launch to get it over with."*

**Symptom:** High permission denial rates. Users decline permissions they
would have accepted if asked at the right moment. Once denied, the user
must go to Settings to re-grant — which most users never do. Features
that require denied permissions are silently non-functional.

**Cause:** Layer 1 (Function & Context) and Layer 6 (Behavior & Construction)
reference on permission UX patterns was absent. Permission timing is a
well-researched problem with documented best practices that were not consulted.

**Fix:** For each permission the app requires:
1. Document the user action that makes the permission obviously necessary
2. Request the permission immediately before that action (just-in-time)
3. Provide a clear explanation of why the permission is needed before the
   system dialog appears
4. Design the graceful degradation for when permission is denied

Reference: platform documentation on permission best practices, UX research
on permission timing (multiple published studies show just-in-time requests
are granted at significantly higher rates than upfront requests).

**Production cost:** User adoption gap from users who denied permissions
and never re-granted them. Effectively: lost features for a significant
percentage of users. Fix requires a permission re-request flow and a
re-education campaign — neither is cheap.

---

## MISTAKE 04 — State Management Assumptions

> *"If the app crashes, the user just reopens it."*

**Symptom:** User reviews mention losing work, lost progress, or the app
"forgetting" what they were doing. Users who experience state loss rarely
give the app a second chance.

**Cause:** Layer 6 (Behavior & Construction) reference for app lifecycle
and state persistence was absent. The app was designed for the happy path
(normal open, use, close) without reference to what happens at app suspend,
background-to-foreground transition, low-memory termination, or crash.

**Fix:** Document the app's behavior at every lifecycle state before
implementation begins — not as a post-implementation test, but as a
design specification derived from platform lifecycle documentation.
For every piece of user state: is it persisted? When? What is the
behavior if persistence fails?

**Production cost:** Fundamental architecture revision if state management
was not designed into the data layer from the start. User trust loss
from data loss events — this is one of the highest-impact failure modes
for user retention.

---

## MISTAKE 05 — Dark Mode as Afterthought

> *"We'll add dark mode support later."*

**Symptom:** On devices with system dark mode enabled, the app has white
backgrounds where the OS has dark, black overlays over dark components,
or crashes when the system theme changes while the app is running.

**Cause:** Layer 5 (Contextual Conditions) reference — system theme
handling — was not included in the initial brief. Dark mode was treated
as a feature to add rather than a platform requirement to comply with.
On iOS (since iOS 13), macOS, and Windows 10+, dark mode is a system-level
feature that apps are expected to handle.

**Fix:** System theme handling is a Layer 5 constraint that must be in
the brief before any color decision is made. Design the color system with
both light and dark variants. Use semantic color tokens that resolve to
the correct value for the current system theme. Test with system dark
mode enabled from the first prototype.

**Production cost:** Full color system revision after dark mode is
implemented as an afterthought produces hardcoded color values throughout
the codebase that must each be converted to semantic tokens. Time lost:
3–7 days for a mature app.

---

## MISTAKE 06 — Performance Tested Only on Development Device

> *"It's fast on my phone."*

**Symptom:** App performs well on the developer's device and poorly on
the devices used by the target market. Slow scrolling, delayed response
to input, slow startup — on devices two or three generations older than
the development device.

**Cause:** Layer 5 (Contextual Conditions) reference on hardware minimum
specification was absent. The development device is almost always more
powerful than the minimum supported device. Testing only on the development
device calibrates performance budget to the wrong hardware.

**Fix:** Before implementation begins, confirm the minimum supported
hardware specification. Acquire or access (via cloud testing) the minimum
supported device for performance testing. Run performance profiling
on the minimum device, not only on the development device. Set performance
budgets (startup time, scroll frame rate, input response) against the
minimum device's capabilities.

**Production cost:** Performance optimization retrofit on a shipped app
is difficult and often incomplete. Performance problems discovered post-launch
require architectural changes that are hard to make safely in a live product.

---

## MISTAKE 07 — Offline Behavior Undefined

> *"It's a connected app — users will always have internet."*

**Symptom:** App crashes or shows blank screens when connectivity is lost.
Users in areas with intermittent connectivity (commutes, travel, rural areas)
have non-functional experiences. App does not queue user actions for sync
when connectivity returns.

**Cause:** Layer 6 (Behavior & Construction) reference for offline behavior
was not gathered. The connectivity assumption was not validated against
the target audience's actual connectivity patterns.

**Fix:** Document the offline behavior before implementation. For every
network operation: what is the behavior when it fails? (Show error, retry,
queue for later, use cached data?) A connected app that handles connectivity
loss gracefully is a much better product than one that assumes a connection
will always exist.

Reference: research the target audience's connectivity patterns. B2B users
in offices have different connectivity than consumers on mobile networks.
Platform documentation on offline and network state handling is primary-tier.

**Production cost:** Retrofit offline handling into a connected-first
architecture. Depending on how deeply network calls are embedded in the
architecture, this can require a significant architectural refactor.

---

## MISTAKE 08 — App Store Submission Surprise

> *"We didn't know you couldn't do that."*

**Symptom:** App rejected from the App Store or Google Play for a reason
that was entirely preventable with prior research. Common rejection reasons:
privacy policy missing, required privacy disclosure missing, use of private
APIs, payments not using platform's payment system, content policy violation.

**Cause:** App store guidelines are Layer 4 (Governing Rules) reference
that was not gathered at the start of the project. Store requirements are
treated as a submission checklist rather than as design constraints that
affect architecture and feature decisions.

**Fix:** Read the full App Store Review Guidelines (Apple) or Developer
Policy Center (Google) before the feature set is finalized. Several common
features (external payment links, subscription management, content from
the web) have platform-specific requirements that must be designed into
the architecture from the start. An app that uses external payments must
be architectured differently than one that uses in-app purchases.

**Production cost:** App rejection requires fixing the violation, re-submitting,
and waiting for review again — a minimum of 1–3 days per rejection cycle.
If the violation requires an architectural change (payment system), the
cost can be weeks.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
