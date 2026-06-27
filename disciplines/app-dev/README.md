# Reference Engineering — App Development

> Systematic pre-production reference methodology for developers building desktop, mobile, and cross-platform applications.

**Discipline:** App Development
**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Who This Is For

Developers building desktop applications (Electron, .NET, native), mobile
applications (iOS, Android, React Native, Flutter), and cross-platform apps.
Solo developers and small teams where pre-production reference work is typically
informal or absent. The methodology accounts for the specific challenges of
app development: platform conventions that must be respected, OS-level
behavior that cannot be overridden, and the long production cycles where
reference gaps discovered late are extremely expensive.

---

## What Reference Engineering Solves in App Development

App development has a specific reference problem that web development does
not: platform conventions are not optional aesthetic choices. An iOS app
that doesn't follow Human Interface Guidelines creates friction that users
attribute to the app being "broken" even when the functionality is correct.
A Windows app that ignores system theme handling produces visible bugs
on machines with dark mode enabled. Reference Engineering in app development
is the discipline of knowing what the platform requires before building,
not discovering it after submission.

The second specific problem: in app development, the distance between
"working on my machine" and "working on the user's machine" is larger
than in web development. OS version differences, hardware differences,
and permission model differences all create contextual conditions that
must be referenced before implementation, not discovered in user reports.

---

## The Pre-Production Questions App Development Must Answer

- [ ] What is the primary user task? What does the user open this app to accomplish?
- [ ] What platform(s) and OS version range is supported?
- [ ] What are the platform's Human Interface Guidelines requirements for this type of app?
- [ ] What hardware variance exists in the target audience? (RAM, storage, GPU, screen resolution range)
- [ ] What permissions does the app require, and how do users respond to permission requests?
- [ ] What is the data persistence model? (local, cloud, hybrid — and what are the failure modes?)
- [ ] What comparable apps in this category do users already have mental models for?
- [ ] What does "update" mean for this app? (auto-update, manual, store-managed — each has UX implications)

---

## Pyramid Layer Map for App Development

| Pyramid Layer | What It Means in App Development |
|---|---|
| Layer 1 — Function & Context | Primary user task, session context (how long, how often, what triggers it), competitive app landscape |
| Layer 2 — Scale & Proportion | Screen size range, DPI range, window size constraints, content hierarchy at minimum supported resolution |
| Layer 3 — Stage Reference | Architecture/wireframe reference; visual design reference; implementation reference per platform |
| Layer 4 — Governing Rules | Platform HIG compliance, design system rules, interaction model parameters |
| Layer 5 — Contextual Conditions | OS version range, hardware minimum spec, permission model, system theme handling |
| Layer 6 — Behavior & Construction | Framework behavior, OS API behavior, data persistence behavior, update mechanism behavior |
| Layer 7 — Precision Detail | Platform-specific animations, transition behavior, native component customization limits |

---

## Contents

| File | What's in it |
|---|---|
| [`REFERENCE_GUIDE.md`](./REFERENCE_GUIDE.md) | Full methodology — all seven layers, all production stages, brief template |
| [`mistakes.md`](./mistakes.md) | 8 discipline-specific failure modes with fixes |
| [`checklist.md`](./checklist.md) | Printable pre-production checklist, stage-organized |
| [`sources.md`](./sources.md) | Best reference sources for app development |

---

## Related

- **Case study:** [`case-studies/kanvaz-ui-v2/`](../../case-studies/kanvaz-ui-v2/) — first-person case study on Kanvaz desktop app (Electron)
- **Example:** [`examples/ui-redesign/`](../../examples/ui-redesign/) — UI/UX reference methodology applicable to app UI

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
