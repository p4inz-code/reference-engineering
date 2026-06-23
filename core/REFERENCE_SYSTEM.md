# The Reference Engineering System

How the framework fits together — across disciplines, across production stages,
and across the tools available to you.

---

## The Three Levels

Reference Engineering operates at three levels simultaneously:

```
LEVEL 3 — DISCIPLINE LAYER
  Field-specific methodology, questions, sources, and failure modes
  (see disciplines/ folder)
         ↕
LEVEL 2 — UNIVERSAL FRAMEWORK
  Seven Principles, Reference Pyramid, Core Loop
  (this document and core/ folder)
         ↕
LEVEL 1 — BRIEF LAYER
  Actual reference gathered and organized for your specific project
  (your production documents)
```

The Universal Framework (Level 2) is the same for every discipline.
The Discipline Layer (Level 3) adapts it to the specific questions
that field asks. The Brief Layer (Level 1) is where you actually work.

---

## Which Document Is for What?

| Question | Document |
|---|---|
| What is Reference Engineering? | `core/WHAT_IS_REFERENCE_ENGINEERING.md` |
| What is the philosophy and origin? | `MANIFESTO.md` |
| What are the seven layers I need? | `core/REFERENCE_PYRAMID.md` |
| What mistakes do practitioners make? | `core/REFERENCE_MISTAKES.md` |
| What do I run before a project starts? | `core/REFERENCE_CHECKLIST.md` |
| What sources are available? | `core/SOURCES.md` |
| What does every term mean? | `core/GLOSSARY.md` |
| How do I apply this to 3D art? | `disciplines/3d-art/REFERENCE_GUIDE.md` |
| How do I apply this to web dev? | `disciplines/web-dev/REFERENCE_GUIDE.md` |
| How do I apply this to [any field]? | `disciplines/[field]/REFERENCE_GUIDE.md` |
| How do I use an AI agent? | `ai-skills/README.md` |
| How do I add a discipline? | `DISCIPLINE_TEMPLATE.md` |

---

## The Brief Lifecycle

A reference brief is not written once. It is maintained through production.

```
PRE-PRODUCTION
  ↓ Write brief  (Layer 1–4 of pyramid)
  ↓ Fill board
  ↓ Audit gaps
  ↓ GO

BLOCKOUT / EARLY PRODUCTION
  ↓ Re-audit brief (Layer 3 check — are you using stage-appropriate reference?)
  ↓ Add any gaps revealed by blockout
  ↓ CONTINUE

MID-PRODUCTION
  ↓ Layer 5–6 audit (lighting context and material behavior)
  ↓ Add detail-stage reference now (Layer 7)
  ↓ CONTINUE

LATE PRODUCTION / HANDOFF
  ↓ Final brief audit
  ↓ Document what you would gather differently next time
  ↓ DONE
```

Most practitioners run this loop once (at the start) or not at all.
Reference Engineering runs it at every major milestone.

---

## Cross-Discipline Transfer

The seven principles and the pyramid layers have equivalents in every field.
The discipline-specific guides in `disciplines/` make this explicit, but here
is the core mapping:

| Universal Layer | 3D Art | Web Development | Security Research |
|---|---|---|---|
| Function & Context | What is the prop? What does it do? | What is the user trying to accomplish? | What is the attack surface? |
| Scale & Proportion | Real dimensions, polygon budget | Viewport sizes, content hierarchy | Scope boundaries, asset inventory |
| Production Stage | Silhouette / blockout / UV / hero | Wireframe / mockup / component / build | Recon / enumerate / exploit / report |
| Style Rules | Shape language, detail density | Design system, brand rules | Threat model framework |
| Lighting Context | Scene lighting conditions | Browser / device rendering conditions | Environment constraints, defenses |
| Material & Surface | PBR channels, material behavior | Framework behavior, browser quirks | Tool behavior, detection risk |
| Hero Detail | Micro-texture, wear patterns | Micro-interaction, copy polish | Exploit detail, PoC precision |

The questions change. The structure does not.

---

## When to Re-Run Reference Work

Reference Engineering is triggered not just at the start of a project but
whenever production reveals that existing reference is insufficient.

**Re-run triggers:**
- The blockout reveals a proportion problem that reference didn't anticipate
- A client brief changes direction mid-project
- You reach a production stage you have no reference for
- A technical constraint changes what is possible (new rendering pipeline,
  new target platform, new scope)
- Someone on the team asks a production question you can't answer from the existing brief

The cost of re-running a reference brief is 30–60 minutes.
The cost of discovering an unanswered production question mid-build is
measured in days.

---

## The Compounding Effect

Reference Engineering compounds across a career in a way that unsystematic
reference collection does not.

**Year 1:** You have a brief template. Your pre-production is structured.
You make fewer mid-production pivots.

**Year 2:** You have a personal source library. You know where to find
specific reference types quickly. Your brief completion time is half of year 1.

**Year 3:** You have documented your failure modes. You pattern-match against
them automatically. Your briefs prevent problems you haven't even encountered
in this project because you've seen them before.

**Year 5:** Your brief template is tuned to your specific type of work.
Your source library is excellent. Your failure mode recognition is fast enough
to catch problems in other people's work. You can teach the methodology.

Systematic reference practice is an investment that pays compounding returns.
Unsystematic collection starts over every project.

---

## The AI Layer

AI skill packs (under `ai-skills/`) are tools that implement Reference
Engineering methodology inside AI agent systems. They are not a replacement
for the methodology — they are a faster interface to it.

The 3d-ref-skills pack (`github.com/p4inz-code/3d-ref-skills`) is the
first published implementation. It contains 9 skills covering the full
Reference Engineering workflow for 3D art.

Additional skill packs are planned. See `ai-skills/README.md`.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
