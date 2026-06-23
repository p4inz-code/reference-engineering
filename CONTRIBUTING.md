# Contributing to Reference Engineering

Thank you for contributing. This library is built on the principle that
Reference Engineering is a discipline that belongs to every practitioner who
needs it — and the community makes it better.

---

## Before You Contribute

Read `MANIFESTO.md` and `DISCIPLINE_TEMPLATE.md` first.

The manifesto tells you what this project is. The template tells you exactly
how to structure any new discipline section. Contributions that don't follow
the template will be asked to revise before merging.

---

## What We Accept

### New discipline sections
A complete discipline folder under `disciplines/` following `DISCIPLINE_TEMPLATE.md` exactly:
- `README.md` — overview, who it's for
- `REFERENCE_GUIDE.md` — full methodology for this discipline
- `mistakes.md` — 5–10 discipline-specific mistakes, scannable card format
- `checklist.md` — printable pre-production checklist
- `sources.md` — best reference sources for this discipline

See the roadmap in `README.md` for disciplines currently needed.

### Improvements to existing discipline sections
Corrections, additions, better sources, clearer language, updated tooling references.

### Improvements to core/ documents
Corrections and clarifications to the universal framework documents.
**Do not propose changes to MANIFESTO.md** — that document is a permanent
historical record, not a living document.

### New AI skill packs
Skills for specific AI agents (Claude, Cursor, Codex, Gemini) implementing
Reference Engineering for a specific discipline. These go under `ai-skills/`
with a link to the external repo.

---

## What We Do Not Accept

- PRs that remove or rewrite attribution to the framework's origin
- Discipline sections that redefine "Reference Engineering" to mean something other than what is defined in `core/WHAT_IS_REFERENCE_ENGINEERING.md`
- AI-generated discipline sections submitted without domain expertise review — the quality bar is practitioner-level knowledge
- Changes to `MANIFESTO.md`, `TRADEMARK_NOTE.md`, `CITATION.md`, or the attribution paragraph in `LICENSE`

---

## Contributor Agreement

By submitting a pull request to this repository, you agree that:

1. Your contribution is licensed under the MIT License (same as this repository)
2. The term "Reference Engineering," the Seven Principles, the Reference Pyramid, and the overall framework retain attribution to Atharva Patil (Northbyte Studios) as defined in `MANIFESTO.md` and `TRADEMARK_NOTE.md`
3. Your contribution will be credited in `CHANGELOG.md` and the relevant discipline section

You retain authorship credit for any discipline section you create or
substantially author. Your name goes in the README.md of that discipline folder.

---

## How to Submit

1. Fork the repository
2. Create a branch: `feat/disciplines/your-discipline-name`
3. Build your discipline folder following `DISCIPLINE_TEMPLATE.md` exactly
4. Open a PR with:
   - Your discipline folder complete (all 5 files)
   - A one-paragraph description of your domain expertise for this discipline
   - Any sources you added to `sources.md` with verification that they are current and accessible

---

## Quality Bar

This is not a link dump or a collection of "useful tips." Every discipline
section should read like it was written by a working professional in that field
who has made the mistakes documented in `mistakes.md` and learned from them.

If you are not a practitioner in the discipline you are contributing, pair with
one. The community Discord (discord.gg/XFF5nV53ZJ) can help with pairing.

---

## Questions

Open an issue with the label `question` or join the Northbyte Studios Discord
at discord.gg/XFF5nV53ZJ.

---

*Northbyte Studios — Atharva Patil — 2026*
