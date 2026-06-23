# Reference Engineering — Glossary

All terms used in this library, defined precisely.

---

## Core Terms

**Reference Engineering**
The systematic practice of identifying, gathering, analyzing, and organizing
reference material before and during production — with the explicit goal of
answering specific technical and creative questions, not merely collecting
visual inspiration. Term coined by Atharva Patil (Northbyte Studios, 2026).

**Reference Brief**
A structured document that defines the reference requirements for a specific
production project. Includes the production questions that need answering,
the reference gathered to answer them, and the gap analysis showing what
is still missing. A reference brief is versioned — it is updated at each
major production milestone, not written once.

**Reference Board**
The visual collection of reference images organized to support a production.
A reference board is the output of reference gathering, not the practice of
Reference Engineering itself. Reference Engineering is the methodology that
makes a reference board useful rather than decorative.

**Reference Pyramid**
The seven-layer framework that defines what types of reference every production
needs, ordered from foundational (Layer 1: Function & Context) to specific
(Layer 7: Hero Detail). A reference board is structurally complete when it
has evidence of reference gathered at every relevant layer.

**Production Question**
A specific, answerable question that production needs to resolve in order to
proceed. Reference Engineering treats production questions as the primary unit
of work — reference is gathered to answer questions, not to fill a board.
Example: "What is the real-world diameter of this pipe fitting?" rather than
"find some pipe reference."

**Gap Analysis**
The systematic identification of production questions that are not yet answered
by the current reference board. Gap analysis is as important as reference
gathering — the gaps that remain are the risks to production.

**Reference Audit**
A structured review of an existing reference board against a defined checklist,
with the goal of identifying gaps, removing decoration, and ensuring
stage-appropriate coverage. Run at each major production milestone.

---

## Pyramid Layer Terms

**Layer 1 — Function & Context**
The foundational reference layer. What the thing does, where it exists,
who interacts with it, and how it behaves in use (not just at rest).

**Layer 2 — Scale & Proportion**
Real-world dimensions and proportion systems. Comparative scale reference
showing the thing next to known-size objects. Orthographic reference when available.

**Layer 3 — Production Stage Reference**
Reference appropriate to the current stage of production. Silhouette stage
needs orthographic and side-view reference. Detail stage needs close-up
surface reference. Stage-appropriate reference is different from general reference.

**Layer 4 — Style Rules**
The extractable visual parameters of the style being worked in. Written rules
(not feelings) derived from a minimum of three reference sources. Includes
shape language, detail density, surface quality, edge treatment, and any
discipline-specific parameters.

**Layer 5 — Lighting Context**
Reference showing how the subject reads under the actual lighting conditions
of the production. Not studio lighting reference for an outdoor scene.
Not film lighting reference for real-time game output.

**Layer 6 — Material & Surface**
Reference for how the material is constructed and how it physically behaves —
under deformation, aging, wear, stress. Goes beyond surface appearance to
material properties.

**Layer 7 — Hero Detail**
Close-range micro-detail reference. Texture frequency, surface treatment,
wear patterns at proximity. The highest layer of the pyramid — only gathered
after all six layers below are addressed.

---

## Reference Hierarchy Terms

**Primary Reference**
Direct documentation of the exact thing being made. Real-world photographs,
technical drawings, or footage of the specific subject. Highest credibility,
lowest availability for fictional subjects.

**Secondary Reference**
Close analogs — things that share significant properties with the subject
but are not identical. A sci-fi weapon's secondary reference might include
real-world firearms with similar functional roles. High credibility for
extractable principles, requires explicit translation.

**Tertiary Reference**
Extracted principles from distant analogs. The rules of how things in a
category behave, applied to a subject that doesn't fit neatly in that
category. Lower credibility for specifics, high value for establishing
behavioral logic where primary and secondary reference don't exist.

---

## Failure Mode Terms

The ten named failure modes are defined in `REFERENCE_MISTAKES.md`.
Short-form definitions:

**Decoration Board** — Large board, zero analysis. Reference that answers nothing.

**Peak Without Foundation** — Hero detail reference gathered before proportion
and silhouette reference is established.

**Style Drift** — Gradual departure from reference style caused by making
micro-decisions from images rather than written rules.

**Stage Mismatch** — Reference appropriate to a different production stage
than the current one being used to make current-stage decisions.

**The Missing Analog** — Production stall caused by treating reference as only
direct documentation of the exact thing, rather than engineering answers
from available indirect reference.

**Single-Source Bias** — Over-reliance on one reference source, producing
work that reads as derivative of that source.

**Contextless Collection** — Reference gathered without annotation.
Board that cannot be navigated during production.

**Frozen Brief** — Reference brief written once and never revisited at
production milestones.

**Quantity Over Specificity** — Large board, low usability. Reference board
that cannot be navigated quickly during production.

**Discipline Mismatch** — Reference gathered from a different production
medium than the output medium, with no explicit translation of what transfers.

---

## Discipline Terms

**Discipline Section**
A folder in `disciplines/` containing the Reference Engineering methodology
adapted for a specific creative or technical field. Each discipline section
contains exactly five files: README.md, REFERENCE_GUIDE.md, mistakes.md,
checklist.md, sources.md.

**AI Skill Pack**
A collection of structured prompts or skill files that implement Reference
Engineering methodology for a specific AI agent (Claude, Cursor, Codex, etc.)
and discipline. Listed under `ai-skills/`. The 3d-ref-skills pack
(github.com/p4inz-code/3d-ref-skills) is the first published example.

**Discipline Template**
The standard structure that all discipline sections must follow.
See `DISCIPLINE_TEMPLATE.md`.

---

## Attribution Terms

**Prior Art**
Public documentation that establishes the existence of an idea, method, or
term before any later claim. The git commit history and timestamped documents
in this repository constitute prior art for the term "Reference Engineering"
as applied to systematic pre-production methodology.

**Framework Attribution**
Credit to the origin of the Reference Engineering framework. See `CITATION.md`
for the recommended attribution format. Attribution is encouraged, not legally
required under MIT.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
