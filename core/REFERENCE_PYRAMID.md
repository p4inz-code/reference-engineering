# The Reference Pyramid

The Reference Pyramid defines the seven layers of reference that every
production needs — regardless of discipline. Most reference boards collapse
because they have too much at the peak and nothing at the foundation.

The pyramid is read bottom-up: you cannot build the top layers without
the foundation being solid.

---

```
                        ▲
                       /|\
                      / | \
                     /  7  \        HERO DETAIL
                    /-------\       Texture, micro-surface, fine craft
                   /    6    \      MATERIAL & SURFACE
                  /           \     How it's made, how it behaves
                 /-------------\
                /       5       \   LIGHTING CONTEXT
               /                 \  How it reads under real-world conditions
              /-----------------\
             /         4         \ STYLE RULES
            /                     \Extracted parameters, not vibes
           /-----------------------\
          /            3            \PRODUCTION STAGE
         /                           \Silhouette / blockout / UV / hero
        /-----------------------------\
       /               2               \SCALE & PROPORTION
      /                                 \Real dimensions, comparative anchors
     /-----------------------------------\
    /                  1                  \FUNCTION & CONTEXT
   /                                       \What it does, where it lives, who uses it
  /-------------------------------------------\

```

---

## Layer 1 — Function & Context

**What it is:** The foundational layer. What does this thing *do*? Where does
it exist? Who interacts with it, and how?

**Why it's first:** Every visual decision downstream is constrained by
function. A weapon that looks beautiful but can't be rigged for an animation
rig is a reference engineering failure. A building material that looks correct
but doesn't tile is a texture engineering failure. You cannot gather useful
reference for something you don't understand the function of.

**What to find:**
- Real-world examples of the thing in use (not just at rest)
- Context shots: the thing in its environment
- Interaction reference: how it is held, operated, worn, entered, inhabited
- Failure states: what it looks like when worn, broken, or old

**Skip-layer consequence:** Production questions about function arrive
mid-production, causing rework. ("Wait — does this door handle open inward
or outward? The animation rigging needs to know.")

---

## Layer 2 — Scale & Proportion

**What it is:** Real-world dimensions and proportion systems. What is the
actual size of this thing relative to the things around it?

**Why it matters:** Scale is the most commonly underspecified reference layer.
A prop that is slightly the wrong scale looks wrong in every shot without
the viewer being able to articulate why.

**What to find:**
- Technical specs or blueprints when available
- Comparative shots: the thing next to a known-size object (human figure, door, car)
- Orthographic reference when available
- Proportion systems: head-count for characters, module size for architecture

**Skip-layer consequence:** Scale errors that require full rework discovered
at the integration stage. The asset doesn't fit in the scene correctly.

---

## Layer 3 — Production Stage

**What it is:** Reference specific to the current production stage.
Silhouette reference, blockout reference, UV reference, and hero detail
reference are four different things. Gather the one you need *now*.

**The stages:**
- **Silhouette stage:** Side/front/back/top orthographic. Strong readable shape.
- **Blockout stage:** Major mass proportions. No detail.
- **Mid-model stage:** Panel lines, secondary forms, topology questions.
- **UV/Texture prep stage:** Tiling seam reference, surface variation reference.
- **Hero detail stage:** Micro detail, wear patterns, high-frequency texture.

**What to find:** Reference that answers the specific question of your
current stage, not the next one.

**Skip-layer consequence:** Working from hero detail reference at the
silhouette stage. The overall read is wrong even if every detail is correct.

---

## Layer 4 — Style Rules

**What it is:** The extractable parameters of the visual style you are working
in. Not a feeling — a set of written rules derived from the reference.

**What to extract:**
- Shape language (hard-edged vs organic, angular vs rounded)
- Detail density (where is there detail, where is there rest)
- Surface quality (matte/shiny/rough/smooth spectrum)
- Color/value architecture (local color vs ambient, saturation range)
- Edge treatment (bevel width, chamfer behavior, hard vs soft transitions)
- Proportion exaggeration (if any)

**What to do with it:** Write it down. "The style uses hard angular bevels,
never rounds. Detail density is 80% negative space, 20% clustered greebling.
Surface reads as matte except chrome accents." That is style engineering.

**Skip-layer consequence:** Work that feels off-style even when every
individual element is technically correct. "It looks right but doesn't
feel right" is always a Style Rules failure.

---

## Layer 5 — Lighting Context

**What it is:** How the thing reads under specific real-world lighting
conditions — the conditions it will actually live in during production.

**Why it matters:** A material that looks correct in a studio reference photo
may completely misread in the outdoor daylight conditions of your scene.
Reference gathered without lighting context produces surfaces calibrated
to the wrong conditions.

**What to find:**
- Reference photographed under lighting conditions similar to your production
- Multiple lighting conditions if the asset appears in multiple environments
- Value read at distance (does the silhouette still read clearly?)
- Specular behavior under real-world conditions

**Skip-layer consequence:** Textures and materials that require full revision
at the lighting and rendering stage because they were calibrated to the
wrong light.

---

## Layer 6 — Material & Surface

**What it is:** How the material is constructed, what it is made of,
and how it physically behaves.

**Why physical behavior matters:** The way metal dents is different from
the way ceramic cracks is different from the way fabric drapes. Reference
that shows the static appearance of a material without showing its behavior
is incomplete for any production involving deformation, damage, or animation.

**What to find:**
- Construction reference: how is it made, assembled, joined
- Behavior reference: how does it deform, age, wear, break
- PBR reference (for 3D): albedo range, roughness range, metallic value
- Layer reference: what is underneath when the surface wears through

**Skip-layer consequence:** Technically correct materials that read as fake
because they don't behave the way the real material behaves under stress,
wear, or lighting.

---

## Layer 7 — Hero Detail

**What it is:** The top-layer fine detail reference. Micro-surface, texture
frequency, craftwork, wear patterns at close range.

**Why it's at the top:** Hero detail is only useful when all six layers below
it are already answered. Gathering hero detail reference before you know the
function, scale, style rules, and material behavior of the thing is
a waste of time — and a very common mistake.

**What to find:**
- Close-up photography of real-world equivalents
- Micro-surface texture reference (pore size, grain direction, scratch pattern)
- Wear and aging reference specific to this material
- Craft reference: stitching, welds, fasteners, surface treatments

**Skip-layer consequence:** Beautifully detailed work that fails at the
read-distance because the foundation layers were wrong. Detail does not
fix proportion or function or style.

---

## How to Use the Pyramid

**Start at Layer 1, build up.** Do not start with hero detail reference.

**Check for gaps.** Most reference boards have Layer 7 (hero detail) covered
and Layers 1–3 missing. The gaps hurt more than the presence helps.

**Stage your gathering.** You do not need Layer 7 reference at the start of
production. Gather by stage, not all at once.

**The discipline-specific guides** in `disciplines/` tell you what specific
reference to look for at each layer for that field.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
