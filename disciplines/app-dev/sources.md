# App Development — Reference Sources

Best sources for Reference Engineering in app development, by Pyramid layer.

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Function & Context

**App Store / Google Play Reviews** — FREE
Primary-tier user task and pain point reference. Read the 3-star reviews
of comparable apps — they articulate what users came for, what worked,
and what didn't. 5-star reviews tell you what to keep. 1-star reviews
tell you what to avoid. 3-star reviews tell you what users actually
needed and didn't get.

**App Annie / data.ai / Sensor Tower** — PAID (limited free)
App store analytics: rankings, review trends, download estimates,
update frequency of competitors. Layer 1 competitive context reference.

**Reddit communities for the app category** — FREE
`r/productivity`, `r/iphone`, `r/androidapps`, category-specific subreddits.
Users discuss what apps they use, why they switched, and what they wish
existed. Raw primary-tier Layer 1 reference.

**Mobbin** — FREE / PAID
Real app screenshots organized by flow (onboarding, checkout, settings,
permissions). Layer 1 reference for how comparable apps handle the
primary task flow. Filter by platform and app category.

---

## Layer 2 — Scale & Proportion

**Apple Device Screen Sizes** — FREE
developer.apple.com/design/human-interface-guidelines/layout — official
dimensions for all current and recent Apple devices. Primary-tier.

**Android Screen Compatibility** — FREE
developer.android.com/guide/practices/screens_support — official guidance
on screen size categories and density buckets. Primary-tier.

**Screen Size Distribution (StatCounter)** — FREE
gs.statcounter.com — real-world screen resolution distribution by platform
and region. Use for confirming the minimum size that covers 90%+ of the
target audience.

---

## Layer 3 — Stage Reference

**Mobbin** — FREE / PAID
See Layer 1. Also the best source for app UI pattern reference organized
by screen type. Wireframe stage: find structure. Visual design stage:
find component treatment.

**ScreenLane / Scrnshts** — FREE
App screenshot archives organized by app and screen type. Good for
finding real examples of specific screens (onboarding, paywall,
empty states, settings).

**Google Play Store / Apple App Store top charts** — FREE
The top apps in any category are real, current examples of what users
respond to. Download and use them as Layer 3 reference — note the
navigation, the information density, the onboarding approach.

---

## Layer 4 — Governing Rules

**Apple Human Interface Guidelines** — FREE
developer.apple.com/design/human-interface-guidelines — the definitive
source for iOS and macOS design requirements. Read in full for any Apple
platform app. Primary-tier, non-optional.

**Material Design 3** — FREE
m3.material.io — the definitive source for Android design requirements
and recommendations. Primary-tier for Android apps. Also widely used
as a general design system reference.

**Microsoft Fluent Design** — FREE
fluent2.microsoft.design — Windows and cross-platform design guidance.
Primary-tier for Windows apps built with WinUI or Fluent components.

**WPF / WinForms HIG resources** — FREE
Microsoft documentation for Windows Presentation Foundation and Windows
Forms. Less prescriptive than Apple or Material but documents expected
behaviors for system integration.

---

## Layer 5 — Contextual Conditions

**Apple OS Adoption** — FREE
developer.apple.com/support/app-store — Apple publishes official iOS
and iPadOS version distribution. Primary-tier for setting iOS minimum
OS version. Updated regularly.

**Android Version Distribution** — FREE
developer.android.com/about/dashboards — Google publishes Android
version distribution for Play Store-enabled devices. Primary-tier
for Android OS minimum setting.

**Firebase Crashlytics / App Store Connect Analytics** — FREE (with your app)
Once the app is live, these are primary-tier sources for actual device
and OS version distribution in your specific user base. More accurate
than general market data for established apps.

**BrowserStack App Live / AWS Device Farm** — PAID
Real device cloud testing for mobile apps. Primary-tier Layer 5
reference for behavior on devices not available locally. Essential
for Android given device fragmentation.

**Instruments (Xcode) / Android Profiler** — FREE
Platform-native profiling tools. Primary-tier for Layer 5 performance
reference on the development device. Must be supplemented with testing
on minimum-spec hardware.

---

## Layer 6 — Framework & OS Behavior

**Apple Developer Documentation** — FREE
developer.apple.com/documentation — official UIKit, SwiftUI, and
AppKit documentation. Primary-tier for all iOS/macOS implementation
reference. Updated with each OS release. Prefer this over tutorials
and Stack Overflow for authoritative behavior documentation.

**Android Developers Documentation** — FREE
developer.android.com/docs — official Android and Jetpack documentation.
Primary-tier for Android implementation. Includes migration guides
when APIs change.

**Electron Documentation** — FREE
electronjs.org/docs — official Electron framework documentation.
Primary-tier for Electron app behavior including OS integration,
auto-update (electron-updater), and native menu handling.

**React Native Documentation** — FREE
reactnative.dev/docs — official React Native documentation. Note that
React Native has significant platform divergence between iOS and Android
implementations. The documentation documents both where they diverge.

**Stack Overflow (with date filter)** — FREE
Use Stack Overflow with the date filter set to the last 12 months.
Older answers may document behavior that has changed in OS or framework
updates. Always verify against official documentation before treating
as authoritative.

---

## Layer 7 — Precision Detail

**Apple Motion Guidelines** — FREE
developer.apple.com/design/human-interface-guidelines/motion — official
animation and transition specifications. Primary-tier for iOS/macOS
animation timing and easing.

**Material Motion** — FREE
m3.material.io/styles/motion — official Material Design motion specifications.
Primary-tier for Android animation timing. Includes specific duration
and easing values for each motion type.

**iOS Accessibility Programming Guide** — FREE
developer.apple.com/accessibility — VoiceOver implementation guide.
Primary-tier for Layer 7 accessibility precision on iOS.

**Android Accessibility** — FREE
developer.android.com/guide/topics/ui/accessibility — TalkBack and
accessibility service implementation guide. Primary-tier for Android.

**Accessibility Insights** — FREE (Microsoft)
accessibilityinsights.io — accessibility testing tool for Windows,
Android, and Web. Use to audit keyboard and screen reader accessibility
during implementation.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
