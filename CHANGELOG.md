# Changelog — reference-engineering

All notable changes to this repository are documented here.
Format: [Version] — [Date] — [Description]

---

## [Unreleased]

Planned for v1.0.0:
- disciplines/3d-art/ (import from 3d-ref-skills)
- disciplines/web-dev/
- disciplines/app-dev/
- README.md full landing page
- Banner image (1280×640px)
- REFERENCE_PYRAMID.svg (rendered diagram)
- ai-skills/README.md + 3d-art link

---

## [0.1.0] — 2026-06-22 — Foundation Layer

Initial commit. Legal layer and core framework documents.

### Added

**Legal Layer**
- `LICENSE` — MIT license with attribution paragraph documenting first use of "Reference Engineering"
- `MANIFESTO.md` — Philosophical foundation, timestamped, authored by Atharva Patil
- `CITATION.md` — APA, Chicago, plain English, tool format, and BibTeX citation formats
- `TRADEMARK_NOTE.md` — Prior art documentation establishing public timestamped record of first use
- `CONTRIBUTING.md` — Contributor agreement and submission guidelines

**Core Framework**
- `core/WHAT_IS_REFERENCE_ENGINEERING.md` — Definition, distinction from moodboarding, core loop, seven principles summary
- `core/REFERENCE_PYRAMID.md` — Seven-layer pyramid with full explanations and skip-layer consequences
- `core/REFERENCE_SYSTEM.md` — How the framework connects across disciplines and production stages
- `core/REFERENCE_MISTAKES.md` — Ten named failure modes with symptoms, causes, fixes, production costs
- `core/REFERENCE_CHECKLIST.md` — Universal printable pre-production checklist, all Pyramid layers
- `core/SOURCES.md` — Universal reference sources organized by Pyramid layer
- `core/GLOSSARY.md` — All framework terms defined precisely

**Infrastructure**
- `DISCIPLINE_TEMPLATE.md` — Exact structure for contributor discipline sections (5 files, full templates)
- `CHANGELOG.md` — This file

### Notes

This version establishes the canonical public record for Reference Engineering
as a named discipline, coined by Atharva Patil (Northbyte Studios, 2026).

Prior implementation: github.com/p4inz-code/3d-ref-skills v3.1.0 (shipped 2026-06-22).

---

*github.com/p4inz-code/reference-engineering*

## [0.2.0] — 2026-06-22 — Theory Expansion + Proof Layer

### Added

**Theory Layer** (`theory/`)
- `theory/REFERENCE_ENGINEERING_THEORY.md` — canonical single-citation document, moved from `core/` and fully rewritten with stronger disciplinary boundary, domain-agnostic framing, and complete model synthesis
- `theory/REFERENCE_HIERARCHY.md` — full credibility model with tier definitions, translation documentation format, missing primary protocol, and minimum source requirements
- `theory/REFERENCE_LIFECYCLE.md` — complete lifecycle model: stages, aging, brief versioning, frozen brief failure mode, personal libraries, institutional memory
- `theory/REFERENCE_RELATIONSHIPS.md` — relationship model: five relationship types (confirmation, constraint, gap, contradiction, temporal), mapping format, cross-project relationships
- `theory/REFERENCE_DECISION_MAKING.md` — decision model: reference-backed decisions vs undocumented assumptions, confidence levels, decision trace format, common decision failures traced to reference practice
- `theory/REFERENCE_MEMORY.md` — memory model: why systems outperform memory, compounding effect, personal libraries, institutional reference memory

**Examples Layer** (`examples/`)
- `examples/README.md` — examples vs case studies distinction
- `examples/ui-redesign/` — complete 4-file example: B2B fintech dashboard redesign (UI/UX discipline)
- `examples/game-environment/` — complete 4-file example: post-apocalyptic modular ruins kit (game art / 3D discipline), all seven Pyramid layers
- `examples/brand-identity/` — complete 4-file example: indie game studio brand identity (brand design discipline)
- `examples/character-design/` — complete 4-file example: archaeologist-adventurer hero character (character art discipline), full brief lifecycle v1→v2
- `examples/architecture/` — complete 4-file example: brutalist library renovation + extension (architecture discipline)

**Case Studies Layer** (`case-studies/`)
- `case-studies/FORMAT.md` — reusable case study format with full file templates
- `case-studies/kanvaz-ui-v2/` — complete 4-file first-person case study: Kanvaz desktop app UI v2.0, retroactive RE analysis

### Changed

**Reconciliation pass — definition and boundary**
- `MANIFESTO.md` — expanded to 10 principles (from 7), strong boundary language added ("references are the subject"), explicit NOT list (not KM, not research, not documentation, not moodboarding, not prompt engineering)
- `core/WHAT_IS_REFERENCE_ENGINEERING.md` — rewritten: definition updated, six operations added, explicit boundary table, NOT list, stripped redundant Seven Principles table (now points to MANIFESTO)
- `core/GLOSSARY.md` — Reference Hierarchy section expanded from 3 short definitions to full model with tier diagram, translation documentation, and missing primary guidance
- `core/REFERENCE_ENGINEERING_THEORY.md` — moved to `theory/REFERENCE_ENGINEERING_THEORY.md` and fully rewritten
- `README.md` — full landing page replacing skeleton: theory table, examples table, case studies table, full origin section, discipline status table

### Notes

The disciplinary boundary established in this version is explicit and enforced:
Reference Engineering manages references. Knowledge is an outcome.
References are the subject. This distinction will not change in future versions.

Theory currently exceeds proof. Proof layer (examples + case studies) is now
established. Discipline implementations begin at v1.0.0.


## [1.0.0] — 2026-06-22 — First Discipline Implementations

### Added

**disciplines/3d-art/** — complete 5-file discipline section
- README.md — overview, pyramid layer map, pre-production questions
- REFERENCE_GUIDE.md — full methodology, all 7 layers, PBR reference table, brief template
- mistakes.md — 8 failure modes: wrong scale anchor, pipeline mismatch, ghost detail, stylization without rules, frozen brief midpoint, single-axis silhouette, uniform aging, platform borrow
- checklist.md — stage-organized: pre-production, blockout, mid-model, UV, texturing, rigging, hero detail, pre-delivery
- sources.md — organized by Pyramid layer, includes Kanvaz and 3d-ref-skills

**disciplines/web-dev/** — complete 5-file discipline section
- README.md — overview, pyramid layer map, pre-production questions
- REFERENCE_GUIDE.md — full methodology, all 7 layers, CWV performance context, brief template
- mistakes.md — 8 failure modes: own device, feature assumption, rules without numbers, responsive assumption, framework fighting, invisible accessibility, performance at launch, single-browser
- checklist.md — stage-organized: discovery, wireframe, visual design, implementation, pre-launch
- sources.md — organized by Pyramid layer, browser behavior sources, performance tools

**disciplines/app-dev/** — complete 5-file discipline section
- README.md — overview, pyramid layer map, pre-production questions
- REFERENCE_GUIDE.md — full methodology, all 7 layers, platform HIG as Layer 4, lifecycle behavior, brief template
- mistakes.md — 8 failure modes: platform convention blindness, wrong OS target, permission timing, state management, dark mode afterthought, performance on dev device, offline undefined, app store surprise
- checklist.md — stage-organized: pre-production, architecture, visual design, implementation, QA/submission
- sources.md — organized by Pyramid layer, platform-specific sources (Apple, Android, Windows, Electron)


## [1.1.0] — 2026-06-22 — Discipline Expansion

### Added

**disciplines/vfx/** — complete 5-file discipline section
- Phase principle, three-phase brief structure, pipeline-specific guides (Houdini/Niagara/EmberGen), physical behavior reference, 7 failure modes, pre-sim checklist

**disciplines/game-dev/** — complete 5-file discipline section
- Core loop timing methodology, mechanic analysis format, game feel parameters (coyote time, jump buffer, hit pause), 7 failure modes, stage-organized checklist

**disciplines/game-art/** — complete 5-file discipline section
- Gameplay context principle, readability framework, LOD chain planning, color architecture as communication tool, 7 failure modes, in-engine validation emphasis

**disciplines/ui-ux/** — complete 5-file discipline section
- Task analysis format, interaction pattern analysis format, written design system parameters, accessibility as Layer 5, 7 failure modes, stage-organized checklist

### Repository Status at v1.1.0

Total disciplines complete: 7 (3d-art, web-dev, app-dev, vfx, game-dev, game-art, ui-ux)
Total files: 88
Theory layer: 6 documents
Examples: 5 complete worked examples
Case studies: 1 (Kanvaz UI v2.0)

