# reference-engineering

> **The systematic process of collecting, organizing, analyzing, connecting, retrieving, and applying references to improve the quality of decisions made during production.**

<!-- BANNER PLACEHOLDER — Session 3 -->

**Reference Engineering** is a discipline focused on references as its primary object.

Not knowledge. Not research. Not documentation. Not inspiration.

**References** — the specific collected materials that practitioners use to inform decisions before and during production. Reference Engineering is the discipline of working with those materials systematically.

---

## Why This Exists

Most practitioners collect references. Very few engineer them.

The difference is not effort — it is methodology. A reference collector asks: *"What should I save?"* A reference engineer asks: *"What decisions does this project require, and what reference will inform each one?"*

This repository is the canonical free library for Reference Engineering across every discipline that has a production phase. It defines the methodology, proves it with examples, and provides the tools to practice it.

Reference Engineering was developed by [Atharva Patil](https://github.com/p4inz-code) (Northbyte Studios, Navi Mumbai, India) in 2026. See [`MANIFESTO.md`](./MANIFESTO.md) for the origin and [`CITATION.md`](./CITATION.md) to cite this work.

---

## The Ten Principles

1. References are assets
2. Context is more valuable than quantity
3. Organization precedes automation
4. Retrieval is as important as collection
5. Relationships matter more than storage
6. Knowledge compounds
7. Systems outperform memory
8. Reference Engineering is optional
9. The discipline is tool-agnostic
10. The discipline is domain-agnostic

---

## The Reference Pyramid

Seven layers. Build bottom-up. The upper layers are only useful once the lower layers are established.

```
                         ▲
                        /|\
                       / | \
                      /  7  \     PRECISION DETAIL
                     /-------\    Close-range, fine-grain, craft-level
                    /    6    \   BEHAVIOR & CONSTRUCTION
                   /           \  How it is made, how it acts under conditions
                  /-------------\
                 /       5       \ CONTEXTUAL CONDITIONS
                /                 \ How it reads in its actual environment
               /-----------------\
              /         4         \ GOVERNING RULES
             /                     \ Extracted parameters — written, not vibes
            /-----------------------\
           /            3            \ STAGE-APPROPRIATE REFERENCE
          /                           \ Right reference for the current phase
         /-----------------------------\
        /               2               \ SCALE & PROPORTION
       /                                 \ Real dimensions, relational anchors
      /-----------------------------------\
     /                  1                  \ FUNCTION & CONTEXT
    /                                       \ What it does, where it lives
   /-------------------------------------------\
```

Most reference collections have too much at the top and nothing at the foundation. The gaps at the bottom hurt more than the abundance at the top helps.

Full model: [`core/REFERENCE_PYRAMID.md`](./core/REFERENCE_PYRAMID.md)

---

## What's in This Library

### Theory Layer
The canonical theoretical foundation. Cite [`theory/REFERENCE_ENGINEERING_THEORY.md`](./theory/REFERENCE_ENGINEERING_THEORY.md) when referencing this discipline.

| Document | Contents |
|---|---|
| [`theory/REFERENCE_ENGINEERING_THEORY.md`](./theory/REFERENCE_ENGINEERING_THEORY.md) | Complete unified theory — definition, principles, all models |
| [`theory/REFERENCE_HIERARCHY.md`](./theory/REFERENCE_HIERARCHY.md) | Credibility model — Primary, Secondary, Tertiary tiers |
| [`theory/REFERENCE_LIFECYCLE.md`](./theory/REFERENCE_LIFECYCLE.md) | How reference briefs age, version, and compound |
| [`theory/REFERENCE_RELATIONSHIPS.md`](./theory/REFERENCE_RELATIONSHIPS.md) | How references relate to each other — the relationship model |
| [`theory/REFERENCE_DECISION_MAKING.md`](./theory/REFERENCE_DECISION_MAKING.md) | How reference quality maps to decision quality |
| [`theory/REFERENCE_MEMORY.md`](./theory/REFERENCE_MEMORY.md) | Compounding, personal libraries, institutional memory |

### Core Layer
Operational documents — use these during production.

| Document | Contents |
|---|---|
| [`core/WHAT_IS_REFERENCE_ENGINEERING.md`](./core/WHAT_IS_REFERENCE_ENGINEERING.md) | Definition, boundary, six operations, navigation |
| [`core/REFERENCE_PYRAMID.md`](./core/REFERENCE_PYRAMID.md) | Seven-layer structural model with domain cross-reference |
| [`core/REFERENCE_SYSTEM.md`](./core/REFERENCE_SYSTEM.md) | How the framework connects across disciplines |
| [`core/REFERENCE_MISTAKES.md`](./core/REFERENCE_MISTAKES.md) | Ten named failure modes with fixes and production costs |
| [`core/REFERENCE_CHECKLIST.md`](./core/REFERENCE_CHECKLIST.md) | Universal printable pre-production checklist |
| [`core/SOURCES.md`](./core/SOURCES.md) | Reference sources organized by Pyramid layer |
| [`core/GLOSSARY.md`](./core/GLOSSARY.md) | All framework terms defined precisely |

### Examples
Worked demonstrations of the complete Reference Engineering workflow across five disciplines.

| Example | Discipline | Key Skill Demonstrated |
|---|---|---|
| [`examples/ui-redesign/`](./examples/ui-redesign/) | UI/UX | Extracting written rules from competitor analysis |
| [`examples/game-environment/`](./examples/game-environment/) | Game Art / 3D | Full seven-layer coverage, primary reference sourcing |
| [`examples/brand-identity/`](./examples/brand-identity/) | Brand Design | Converting subjective briefs into measurable parameters |
| [`examples/character-design/`](./examples/character-design/) | Character Art | Full lifecycle — brief v1 → v2, all seven layers |
| [`examples/architecture/`](./examples/architecture/) | Architecture | Multi-domain reference management |

Read [`examples/character-design/`](./examples/character-design/) for the most complete lifecycle demonstration.

### Case Studies
Retroactive analysis of real projects through the Reference Engineering lens.

| Case Study | Project | Key Finding |
|---|---|---|
| [`case-studies/kanvaz-ui-v2/`](./case-studies/kanvaz-ui-v2/) | Kanvaz desktop app | Technical failures are often reference failures in disguise |

Format for new case studies: [`case-studies/FORMAT.md`](./case-studies/FORMAT.md)

### Disciplines *(coming v1.0.0)*
Field-specific adaptations of the framework.

| Discipline | Status |
|---|---|
| `disciplines/3d-art/` | ✅ v1.0.0 |
| `disciplines/web-dev/` | ✅ v1.0.0 |
| `disciplines/app-dev/` | ✅ v1.0.0 |
| `disciplines/vfx/` | ✅ v1.1.0 |
| `disciplines/game-dev/` | ✅ v1.1.0 |
| `disciplines/ui-ux/` | ✅ v1.1.0 |

---

## Start Here

New to Reference Engineering:

1. [`core/WHAT_IS_REFERENCE_ENGINEERING.md`](./core/WHAT_IS_REFERENCE_ENGINEERING.md) — what it is, what it is not, and why the boundary matters
2. [`MANIFESTO.md`](./MANIFESTO.md) — the philosophy and origin
3. [`core/REFERENCE_PYRAMID.md`](./core/REFERENCE_PYRAMID.md) — the seven layers
4. One example from [`examples/`](./examples/) closest to your discipline
5. [`core/REFERENCE_CHECKLIST.md`](./core/REFERENCE_CHECKLIST.md) — run this before your next project

For the complete theory: [`theory/REFERENCE_ENGINEERING_THEORY.md`](./theory/REFERENCE_ENGINEERING_THEORY.md)

---

## What Reference Engineering Is Not

Reference Engineering is distinct from adjacent disciplines:

| Discipline | Manages | Goal |
|---|---|---|
| **Reference Engineering** | References | Better decisions through better reference practice |
| Knowledge Management | Knowledge assets | Organizational learning |
| Research Methodology | Investigation processes | Discovery of new information |
| Documentation | Recorded information | Reliable future access |
| Moodboarding | Aesthetic communication | Shared creative direction |

Reference Engineering intersects with all of these. It is not replaced by any of them.

---

## For 3D Artists — Start Now

The first AI skill pack implementing Reference Engineering is available today:

**3d-ref-skills v3.1.0** — 9 skills covering the full 3D pre-production reference workflow

→ [github.com/p4inz-code/3d-ref-skills](https://github.com/p4inz-code/3d-ref-skills)

Compatible with Claude Code, Cursor, Codex, Gemini.

---

## Origin

I am an animation student and indie developer in Navi Mumbai, India. In 2026, while building systematic reference workflows for 3D production and game development, I found that the methodology underneath what I was doing had no name, no documentation, and no canonical resource. Every discipline had the same reference problem. None of them had a shared language for it.

This repository is the attempt to provide that language.

— Atharva Patil, Northbyte Studios

Cite this work: [`CITATION.md`](./CITATION.md)
Prior art record: [`TRADEMARK_NOTE.md`](./TRADEMARK_NOTE.md)

---

## Contributing

See [`CONTRIBUTING.md`](./CONTRIBUTING.md) and [`DISCIPLINE_TEMPLATE.md`](./DISCIPLINE_TEMPLATE.md).

Community: [discord.gg/XFF5nV53ZJ](https://discord.gg/XFF5nV53ZJ)

---

## License

MIT — see [`LICENSE`](./LICENSE)

*Reference Engineering — coined by Atharva Patil, Northbyte Studios, 2026*
