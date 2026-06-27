# Character Design — Reference Engineering Process

**Brief versions covered:** v1 (pre-production) and v2 (post-blockout)
This document shows both passes. V2 additions are marked **[V2]**.

---

## Layer 1 — Function & Context

### Historical Reality: 1930s Archaeological Fieldwork
*Answers: "What does '30s archaeologist-adventurer' actually mean?"*

Real 1930s field archaeologists (Howard Carter era, 1920s–30s):
- Work clothing, not adventure clothing. Practical khakis, work boots, wide-brim hats for sun protection.
- Equipment: brushes, notebooks, surveying tools — not weapons or climbing gear.
- Physique: academic, not athletic. The real archaeologists were scholars, not action heroes.

This is **not** what the brief wants. The brief wants the pulp fiction version.
Important: knowing what the reality was helps define exactly how far the
fiction departs from it — and that departure is design information.

Hierarchy tier: **Primary** (historical record)
Design implication: the character's costume acknowledges real archaeology
at the detail level (functional pockets, practical materials, worn leather)
while departing from it at the silhouette level (more athletic build, more
dramatic costume elements).

### Pulp Fiction Version: 1930s Adventure Magazines and Novel Covers
*Answers: "What is the pulp fiction version of this archetype?"*

Analysis of 1930s pulp adventure magazine covers (The Shadow, Doc Savage,
Adventure Magazine):
- Extremely athletic proportions — approaching 8 heads in illustration style
- Dramatic, active poses — never standing upright in a neutral position
- Clothing designed to look rugged while reading clearly as heroic
- Always holding something — the "prop in hand" is part of the silhouette
- Strong value contrast between figure and background — character silhouette reads instantly

Design implication: this is the primary visual source for the archetype,
not the real history. The proportions, costume drama, and silhouette clarity
all trace to pulp illustration, not real archaeology.
Hierarchy tier: **Primary** (direct source material for the archetype)

### Gameplay Function: Third-Person Action RPG
*Answers: "What does the body need to do?"*

Third-person action RPG movement set (standard):
- Idle: weight shifted, slightly relaxed — not stiff
- Run: full upper body movement, arms pumping
- Combat: wide stance, weapon-ready pose
- Climbing: full range shoulder and hip deformation
- Interaction: hand reach, crouch

Implication: the character cannot have extreme proportions that break at
shoulder deformation (very wide shoulders fail at climbing). The proportion
decision must be validated against the animation set.
Hierarchy tier: **Primary** (UE5 animation rigging requirements)

---

## Layer 2 — Scale & Proportion

### Head Count Decision
*Answers: "What head count for 'slightly exaggerated stylized realism'?"*

Reference analysis across comparable games in the stylized realism category:
- Horizon Zero Dawn (Guerrilla, 2017): 7.0 heads — realistic, minimal exaggeration
- God of War (Santa Monica, 2018): 7.5 heads — slightly taller, more heroic
- Uncharted 4 (Naughty Dog, 2016): 7.2 heads — realistic hero
- Genshin Impact (HoYoverse, 2020): 6.8 heads — anime-adjacent stylization

Target zone for "slightly exaggerated stylized realism" with action RPG
readability: **7.0–7.2 heads.** More than 7.2 begins to read as superhero
rather than adventurer. Less than 7.0 reads as realistic, not stylized.

Hierarchy tier: **Secondary** (comparable games, same camera distance and style target)

### Proportion Exaggeration Rules
*Answers: "What proportion exaggerations are appropriate?"*

Analysis of pulp illustration proportions vs real human proportion:
- Shoulders: 20–25% wider than real (creates heroic read without superhero excess)
- Hands: 15–20% larger than real (better readability in action at distance)
- Legs: standard or 5% longer (height comes from torso length in this style)
- Head: standard or 3–5% smaller (relative to shoulders — creates heroic proportion)
- Waist: standard or slightly narrower (emphasizes shoulder width by contrast)

Hierarchy tier: **Secondary** (pulp illustration analysis) + **Tertiary** (character design principle: readable proportion exaggeration at distance)

---

## Layer 3 — Production Stage Reference (Silhouette)

### Primary Silhouette Shapes
*Answers: "What 3–4 shapes make this character instantly recognizable?"*

The archaeologist-adventurer silhouette must read in these elements at
third-person camera distance:

1. **Wide-brim hat** — the single most important silhouette element.
   Instantly reads as "adventurer" and creates a strong top shape.
   Without it: character could be anyone.
2. **Shoulder bag / satchel** — breaks the body silhouette on one side,
   adds asymmetry, reads as "carrying something important."
3. **Athletic upper body → practical lower body** — the proportion transition
   from capable shoulders to functional field clothing creates the archetype read.
4. **Tool/weapon in dominant hand** — pulp illustration rule: the prop
   in hand is part of the silhouette. Whether whip, gun, or torch, it must
   read at distance.

Reference: Pulp magazine cover analysis (T1), Indiana Jones franchise silhouette study (T1)
Hierarchy tier: **Primary** — direct archetype source material

### Silhouette at Primary Gameplay Poses
*Answers: "Does the silhouette work in gameplay poses, not just T-pose?"*

Test poses analyzed against silhouette rules:
- **Running:** Hat silhouette still reads. Satchel bounces — animation note.
  Shoulder bag must be rigged to move or it reads as floating.
- **Combat stance:** Wide stance. Dominant hand forward. Hat tilted.
  Silhouette is strong — more interesting than standing neutral.
- **Climbing:** Arms above head — hat brim partially obscures face.
  Acceptable: face is not the hero element in this archetype.

**[V2] Post-blockout finding:** Hat brim at climbing animation was wider
than expected — clipped camera. Hat brim width reduced by 15% in v2.
Reference: in-engine camera test (T1) — added in v2.

---

## Layer 4 — Governing Rules

### Shape Language
*Answers: "What is the shape language?"*

Analysis across pulp adventure illustration and comparable game characters:

**Primary shape: modified rectangle**
The adventurer archetype uses a rectangular primary mass (capable, grounded,
dependable) with organic softening at costume edges (human, not robotic).
Pure circles: too friendly/cartoon. Pure triangles: too aggressive/villain.
Modified rectangle with curved edges: heroic but approachable.

**Secondary shapes:**
- Hat: wide horizontal rectangle (dominance, competence)
- Satchel: soft rectangle (practical, not threatening)
- Boots/gloves: slight taper toward extremities (drawn, active)

**Shape language rules:**
1. Hard edges at structural elements (boots, belt, hat brim)
2. Soft edges at costume/cloth elements (shirt, jacket)
3. Never angular at the face — this archetype is accessible, not intimidating
4. Costume folds follow function logic — where stress would actually occur

Hierarchy tier: **Secondary** (character design analysis, comparable games)

### Style Rules: "Stylized Realism" at This Level
*Answers: "What specific visual rules define this style?"*

From comparable game analysis:
1. Anatomy: simplified muscle groups — present but not hyper-defined.
   You know where the deltoid is; you don't see every fiber.
2. Surface detail: present at hero areas (face, hands, boots), minimal at
   background areas (back of jacket, underside of arms).
3. Edge behavior: beveled, not chamfered. Soft transitions between planes.
   No knife-edge creases except at intentional style accents (belt hardware).
4. Skin: pores suggested, not simulated. SSS visible at ear and nose.
5. Clothing: folds at stress points, not decorative wrinkles everywhere.

**What this character NEVER looks like:**
- Hyperrealistic muscle anatomy (wrong style — too realistic)
- Flat-shaded or cartoon-clean surfaces (wrong style — too stylized)
- Symmetrical costume with no wear or character (too generic)
- Neutral/balanced proportions (no exaggeration = wrong archetype)
- Overly clean or new-looking equipment (this character has history)

Hierarchy tier: **Secondary** (comparable game style analysis)

### **[V2] Additional Rules from Blockout**
Post-blockout findings added to rule set:
- Hat brim: maximum 15cm overhang before camera clip at climbing animation
- Satchel flap: must be modeled as separate piece for cloth physics
- Boot detail: visible at all primary camera distances — invest in this area

---

## Layer 5 — Contextual Conditions

### UE5 Third-Person Camera Reference
*Answers: "What are the actual camera conditions?"*

UE5 default third-person: character approximately 300cm from camera,
camera at 160cm height, 60–75° FOV.
At this distance and FOV: face detail is visible but not dominant. Hands
and boots visible at 30–50% of face resolution. Back of character: low
camera focus — reduce detail investment here.

Hero detail investment by camera zone:
- Face, hands, boots, front of jacket: HIGH
- Side of character, hat: MEDIUM
- Back of character: LOW (player rarely sees this in standard third-person)

Hierarchy tier: **Primary** (UE5 documentation + engine test)

### Lighting: Mixed Outdoor / Interior Adventure
*Answers: "What lighting conditions does character appear in?"*

Outdoor: harsh sun, strong shadow. Character must read clearly in
high-contrast lighting — edges must be clean enough to separate from
background in varied conditions.
Interior (dungeon/ruin): low-key, dramatic. Character must read at
low albedo values.
Rule: no costume elements that rely on color differentiation alone to read —
all elements must also have value differentiation.

Hierarchy tier: **Secondary** (comparable game lighting analysis) + **Primary** (UE5 Lumen test)

---

## Layer 6 — Behavior & Construction (Deformation)

### Shoulder Deformation Reference
*Answers: "What topology does the shoulder need?"*

The shoulder is the hardest deformation zone for this character because:
- The wide heroic shoulder proportion pushes the anatomy toward the point
  where standard shoulder deformation fails
- Climbing animation requires full overhead arm extension
- The jacket adds a cloth layer over the deformation

Real-world shoulder anatomy at full arm extension: the deltoid flattens,
the trapezius engages, the clavicle rotates. The jacket over this must
either simulate this (cloth physics) or be modeled to not fight the deformation.

Reference: UE5 skeleton shoulder deformation documentation (T1),
comparable character rigging teardowns from GDC (T2)
Hierarchy tier: **Primary** + **Secondary**

### **[V2] Costume Deformation — Post-Blockout Findings**
Added in v2 after blockout revealed:
- Jacket lapels require separate geometry for cloth physics or they poke
  through the character's chin at run animation
- Satchel strap intersection with jacket shoulder: intersection artifact
  at full deformation — strap geometry needs offset from jacket surface by 2–3mm

---

## Layer 7 — Precision Detail [V2 Only]

### Face and Skin Reference
*Added at v2 (blockout complete, hero detail stage beginning)*

Skin reference for stylized realism:
- Pore distribution: present at nose, cheeks, forehead — absent or minimal
  at jawline and neck (readability at distance)
- SSS zones: strong at ear, moderate at nose and lips, minimal elsewhere
- Age reading: mid-30s — early lines at eye corners and forehead, not deep

Reference: Naughty Dog GDC presentations on stylized skin (T2),
Megascans face scan data for texture frequency guidance (T1)

### Costume Wear Reference
*Answers: "What wear and history does this costume have?"*

Primary wear zones (where costume takes real-world stress):
- Hat: brim edge, sweat band stain, dimpled crown
- Jacket: elbow reinforcement worn through, cuff fraying, collar darkened
- Boots: toe cap scuffed, heel edge worn, lacing grommets stressed
- Satchel: flap edge worn, clasp area scratched, bottom corners rubbed

Reference: Vintage field clothing photography, 1920s–1930s expedition records (T1)
Hierarchy tier: **Primary**

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
