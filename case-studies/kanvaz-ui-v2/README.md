# Case Study: Kanvaz UI v2.0

**Project type:** Desktop application UI (Electron, Windows)
**Discipline:** App Development / UI Design
**Analyst:** Atharva Patil — Northbyte Studios (first-person)
**Date of project:** 2025–2026
**Date of analysis:** 2026-06-22
**Access level:** First-person — I built this

---

## What Kanvaz Is

Kanvaz is a free, offline, infinite canvas reference board desktop application
for Windows. It is positioned as a PureRef alternative optimized for VFX and
3D pre-production workflows. It is MIT licensed, distributed as a portable EXE,
and built on Electron.

The current version is v2.0.1. This case study analyzes the UI decisions made
during the v2.0 development cycle and applies the Reference Engineering
framework retroactively.

---

## Why This Project

Kanvaz is an unusual case study subject: it is a tool *for* reference work,
built without systematic reference work governing its own UI design.
The irony is intentional and useful — it demonstrates that Reference
Engineering is not automatically practiced by people who understand its value.
Knowing that reference matters and practicing Reference Engineering are different things.

This case study also demonstrates Reference Engineering applied to app
development — a discipline where "reference" means competitor analysis,
interaction pattern libraries, platform conventions, and user behavior
documentation rather than visual or physical reference.

---

## What This Case Study Shows

1. How the absence of Layer 1 (Function & Context) reference produces
   UI decisions that satisfy the designer's mental model of the user
   rather than the actual user's workflow
2. How the absence of Layer 4 (Governing Rules) reference produces
   visual inconsistency that accumulates across a codebase without
   a single visible breaking point
3. How the absence of Layer 5 (Contextual Conditions) reference produces
   UI calibrated to the developer's display rather than the user's display
4. What a retroactive RE brief for this project would have looked like —
   and which specific decisions would have been different

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
