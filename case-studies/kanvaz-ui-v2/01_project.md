# Kanvaz UI v2.0 — Project Record

## What Was Built

Kanvaz v2.0: a complete UI rebuild of the Kanvaz desktop application
(Electron, Windows). The v2.0 release replaced the v1.x UI with a new
visual design system, updated the canvas interaction model, and added
several new features (autosave attempt, multi-board support, improved
image import).

Timeline: approximately 3 months of intermittent development alongside
other active projects (Nexus, Dead Corps, coursework).
Team: solo developer — all design and development by Atharva Patil.
Distribution: portable EXE, GitHub releases page, free, MIT licensed.
Current version: v2.0.1 (patch after v2.0 shipped with known bugs).

---

## The Brief

**Stated brief (internal):** Rebuild the UI to be "cleaner and more
professional" than v1.x. Add the features users had requested in Discord.
Fix the performance issues from v1.x's canvas implementation.

**What the brief did not specify:**
- Who the specific target user is (beyond "VFX and 3D artists")
- What those users' primary workflow actually is
- What "cleaner and more professional" means in parameters
- What competitive products are the reference point
- What display conditions the target user is typically working in

The absence of these specifications in the brief is the root cause of
most of the reference failures documented in this case study.

---

## The Outcome

**What shipped:** Kanvaz v2.0 shipped. The core canvas functionality works.
The visual design is more coherent than v1.x. The application is usable
and has active users.

**Known shipped bugs (v2.0.0):**
- Autosave does not work reliably (the most-requested feature, shipped broken)
- Multi-board switching has edge cases that cause state loss
- Image import from clipboard intermittently fails on some Windows configurations

**v2.0.1 patch:** Fixed the most critical autosave failure mode. Clipboard
import still intermittent. Multi-board state loss in low-priority queue.

---

## What Worked

**Canvas performance:** The v2.0 canvas implementation is significantly
faster than v1.x at large board sizes. This was the highest-priority
technical goal and was achieved.

**Visual coherence:** The v2.0 UI is visually more consistent than v1.x.
The component system is more systematic. The dark theme is better executed.

**Core functionality reliability:** The basic workflow (add images, arrange,
annotate, save/load) is stable in v2.0.1.

---

## What Failed or Was Harder Than It Should Have Been

**Autosave implementation:** The autosave feature was the most-requested
community feature. It was prioritized for v2.0. It shipped broken.
Root cause: the autosave interaction model was designed without reference
to how other canvas applications handle autosave conflicts and failure states.
The failure mode (autosave overwriting user's manual save with an
auto-saved intermediate state) was a known failure pattern in this
application category that reference would have revealed.

**Toolbar layout contested in revision:** The primary toolbar layout went
through four revisions during development. Each revision responded to
"this doesn't feel right" rather than to a documented standard.
No written style rule governed toolbar behavior. Revisions ended when
development time pressure forced a decision, not when a reference-backed
answer was found.

**Dark theme calibration off on high-brightness displays:** The dark theme
was calibrated on a single monitor (the development machine). Several users
reported that on high-brightness displays or in bright ambient conditions,
the dark theme elements have insufficient contrast. The UI was calibrated
to one display condition — mine — without reference to the range of display
conditions the application would be used in.

**"PureRef replacement" positioning not validated:** The application is
positioned as a PureRef alternative for VFX/3D artists. PureRef's workflow
was never systematically analyzed. The features Kanvaz added or changed
were not validated against PureRef's specific workflow advantages.
One version 2 user noted that Kanvaz's board file format is not compatible
with PureRef — a migration friction point that direct competitor analysis
would have flagged.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
