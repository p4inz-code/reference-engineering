# Character Design — Outcome & Decisions

**Brief version:** v2 (post-blockout)
**Decision log:** All decisions traced to reference. Undocumented assumptions flagged.

---

## Proportion Decisions

**D01 — Head count: 7.1 heads**
Between Horizon (7.0) and God of War (7.5). Lands at the readable
hero proportion without crossing into superhero excess.
Reference: Comparable game proportion analysis (T2 aggregate)
Confidence: SUPPORTED — three independent T2 sources bracket this value

**D02 — Shoulder width: +22% from anatomical baseline**
Center of the 20–25% exaggeration range. Creates heroic read without
requiring topology compromises at shoulder deformation zones.
Reference: Pulp illustration proportion analysis (T1), rigging constraint (T1)
Confidence: CONFIRMED — T1 + T1 agreement, production-tested at blockout

**D03 — Hand size: +18% from anatomical baseline**
Larger hands read better at third-person camera distance and in action
animation. Pulp illustration reference consistently shows enlarged hands.
Reference: Pulp illustration analysis (T1), camera distance test (T1)
Confidence: CONFIRMED

**D04 — Hat brim: 12cm overhang (reduced from initial 15cm in v1)**
[V2 update] 15cm brim clipped camera at climbing animation. Reduced to 12cm.
Silhouette still reads clearly — hat is still the primary silhouette element.
Reference: In-engine camera clip test (T1)
Confidence: CONFIRMED — production-tested

---

## Silhouette Decisions

**D05 — Four primary silhouette elements locked**
1. Wide-brim hat (top shape)
2. Shoulder satchel on left side (asymmetric body break)
3. Athletic shoulder-to-waist taper (archetype proportion)
4. Right-hand prop (whip handle / torch / pistol depending on scene)
All four read at third-person camera distance in primary gameplay poses.
Reference: Pulp magazine cover analysis (T1), Indiana Jones silhouette study (T1)
Confidence: CONFIRMED

**D06 — Silhouette validated at three primary gameplay poses**
Running: all four elements read ✅
Combat stance: all four elements read ✅
Climbing: hat brim reads, satchel reads, prop in holster (not hand) ✅
Reference: In-engine pose test (T1)
Confidence: CONFIRMED — production-tested

---

## Shape Language Decisions

**D07 — Primary mass: modified rectangle**
Capable, grounded, heroic without aggressive. Hard edges at structural
elements (boots, belt, hat brim). Soft edges at costume/cloth elements.
Never angular at the face — accessible, not intimidating.
Reference: Shape language analysis from comparable game characters (T2)
Confidence: SUPPORTED

**D08 — Costume folds: function-logic only**
Folds occur at stress points (elbow bend, knee break, hip flex, collar
tension). No decorative wrinkles. Where the cloth would be under tension,
it is smooth. Where it releases, it folds.
Reference: Real garment photography, 1930s field clothing (T1)
Confidence: CONFIRMED

---

## Material & Surface Decisions

**D09 — Anatomy detail level: simplified muscle groups**
Deltoid, bicep, trapezius — present and readable. Individual muscle fibers
not visible. Surface has plane changes, not anatomical exactness.
Reference: Comparable stylized character surfacing (T2 aggregate)
Confidence: SUPPORTED

**D10 — Skin: SSS zones defined**
Strong SSS: ear, nose tip, lips
Moderate SSS: cheeks, brow
Minimal SSS: jaw, neck, forehead
Pores: present at nose, cheeks, forehead. Absent at jaw and neck.
Reference: Naughty Dog GDC skin presentation (T2), Megascans face scan (T1)
Confidence: SUPPORTED (T2) + CONFIRMED for texture frequency (T1)

**D11 — Costume wear zones: five primary areas**
Hat brim edge + sweat band, jacket elbows + collar + cuffs,
boot toe cap + heel edge, satchel flap edge + clasp, belt at buckle.
Wear everywhere else is minimal — too much wear reads as neglect,
not history. These five zones tell the story.
Reference: 1930s expedition photography (T1), vintage field clothing (T1)
Confidence: CONFIRMED

**D12 — Color architecture: warm neutral base, one accent**
Base: warm khaki (jacket, trousers) — #8B7355 approximate
Leather: darker warm brown (boots, satchel, belt) — #5C3D2E approximate
Metal: desaturated brass/bronze (hardware) — #8A7340 approximate
One cool accent: shirt fabric — #4A6670 (muted blue-green, reads as
contrast against warm costume without competing)
No pure colors. All muted. Character reads as "worn and real."
Reference: Pulp illustration color analysis (T1), comparable game color (T2)
Confidence: SUPPORTED

---

## Camera Zone Detail Investment Decisions

**D13 — Hero detail zones: face, hands, boot front, jacket front**
These are visible at primary camera distance in primary gameplay poses.
Maximum texel density investment here.

**D14 — Standard detail zones: hat, satchel, jacket sides**
Visible but not prominent at primary camera distance.
Standard texel density.

**D15 — Reduced detail zones: jacket back, trouser back, boot back**
Rarely visible at third-person camera in primary gameplay poses.
Reduced texel density. No hero detail.

Reference: UE5 third-person camera distance test (T1)
Confidence: CONFIRMED — production-tested

---

## [V2] Decisions Added Post-Blockout

**D16 — Jacket lapels: separate geometry with cloth physics**
Blockout revealed lapel intersection with chin at run animation.
Separate geometry allows cloth simulation to clear the chin naturally.
Reference: Blockout animation test (T1)
Confidence: CONFIRMED

**D17 — Satchel strap: 3mm offset from jacket surface**
Intersection artifact at full shoulder deformation. 3mm gap prevents
visual artifact while remaining invisible at camera distance.
Reference: Blockout deformation test (T1)
Confidence: CONFIRMED

---

## The "NEVER" List (Written Into Production Document)

1. Never hyperrealistic muscle anatomy — simplified muscle groups only
2. Never symmetrical costume — asymmetry (satchel, worn areas) is required
3. Never new-looking equipment — all costume elements have documented wear
4. Never neutral/balanced proportions — all exaggerations documented and intentional
5. Never cartoon-clean surfaces — stylized realism requires surface complexity
6. Never decorative wrinkles — folds follow function logic only
7. Never angular face geometry — accessible, not aggressive
8. Never color differentiation without value differentiation — all elements
   must read in high-contrast lighting by value, not only by color

---

## Undocumented Assumptions (Flagged)

**A01: Hair system not specified**
No decision made on Groom vs. cards vs. mesh hair. Hair system affects
topology requirements at the scalp and hat interaction zone.
Risk: MEDIUM — if Groom is used, hat physics interaction needs spec.
Action: Resolve before mid-production.

**A02: Facial animation rig not specified**
Face topology decisions were made for visual quality, not facial animation.
If this character requires lip sync or facial expressions (cutscenes),
the face topology may need adjustment.
Risk: LOW for gameplay, HIGH for cutscenes.
Action: Confirm with animation team before face sculpt is locked.

---

*Example: Reference Engineering library — github.com/p4inz-code/reference-engineering*
