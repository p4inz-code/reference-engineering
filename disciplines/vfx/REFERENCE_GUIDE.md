# VFX — Reference Engineering Guide

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## The Phase Principle

Every VFX effect has three phases. Reference must cover all three separately.
A reference board with only peak-state images produces sims that start
and end correctly but look wrong at onset and dissipation — which is
most of the screen time.

```
ONSET          →          PEAK          →          DISSIPATION
Small, fast,            Maximum density,         Thinning, cooling,
high energy             full color range         trailing edges
```

Before any other reference work, identify the three phases for the
specific effect and what visually defines each one.

---

## Layer 1 — Function & Context

### What to Find

**Phenomenon identity:** What is the real-world phenomenon? Not "fire" —
what type of fire? (Pool fire, jet fire, fireball, wildfire, candlelight —
all have different visual behavior.) Not "explosion" — what type?
(Deflagration, detonation, BLEVE, gas explosion, dust explosion —
different density, timing, and color.) Specificity at Layer 1 determines
the accuracy of all reference that follows.

**Narrative function:** Is this a hero effect (the focus of the shot,
reviewed frame-by-frame by the client) or a background effect (supporting
the composition, reviewed as a whole)? Hero effects require primary-tier
reference for every parameter. Background effects can use secondary or
tertiary reference for some parameters.

**Compositional context:** What is behind and around this effect in the
final composite? A fire in front of a white sky reads completely differently
from the same fire in front of a dark forest. The context defines what
color values, density levels, and edge behavior will actually read.

### Discipline-Specific Questions

- What is the specific real-world phenomenon, named precisely?
- What is the effect's function in the shot — is it the hero or supporting?
- What is the camera angle and distance relative to the effect?
- What is behind the effect in the composite?

---

## Layer 2 — Scale & Proportion (Timing and Density)

### What to Find

**Physical scale:** What is the real-world size of this effect? A human-scale
explosion (grenade, small IED) has different column height, spread rate,
and density than a vehicle-scale explosion or a building-scale explosion.
Scale directly affects turbulence frequency, velocity range, and timing.

**Timing from real footage:** Count frames in real footage. The onset-to-peak
timing, peak duration, and dissipation rate are measurable from footage
and should be documented as frame counts at the target frame rate.

```
[Example documentation format]
Phenomenon: small vehicle fuel fire (post-collision)
Footage source: NIST fire research footage, 2018
Frame rate: 240fps (slow motion) — converted to 24fps equivalents

Onset to peak: 12 frames (24fps equivalent: 0.5 seconds)
Peak duration: 60 frames (2.5 seconds)
Dissipation: 180 frames (7.5 seconds — long tail)
```

**Density curve:** At each phase, what is the visual density of the effect?
Density is not a feeling — it is a measurable property of the reference
footage. Use a color picker on the reference frame to approximate
the opacity of the effect at its densest point.

---

## Layer 3 — Stage Reference (Per Phase)

### Reference Per Phase

**Onset reference:** The effect at its most energetic per-unit-volume,
smallest overall. Find footage that shows the first 20% of the effect's
life. What color? What speed? What edge behavior?

**Peak reference:** The effect at maximum volume and visual complexity.
Find footage at the 30–60% mark of the effect's life. What is the
color at core vs. edge? What is the turbulence scale?

**Dissipation reference:** The effect thinning and cooling. Find footage
at the 60–100% mark. How does the edge break up? What color does the
residual material become? What is the trailing velocity?

### Real-World Motion Reference Sources (by phenomenon)

| Phenomenon | Best Footage Source |
|---|---|
| Fire (small) | NIST Fire Research, YouTube slow-motion channels |
| Explosion (practical) | Military research footage, demolition footage |
| Water / fluid | The Slow Mo Guys, oceanographic research footage |
| Smoke | Wind tunnel research, NOAA weather footage |
| Dust / particulate | Slow-motion industrial footage, avalanche footage |
| Lightning | Weather channel slow-motion, research storm footage |
| Magic / stylized | Indirect — extract shape and motion principles from natural phenomena |

---

## Layer 4 — Governing Rules

### What to Extract and Write Down

The Layer 4 output for VFX is a set of written simulation parameters
extracted from real-world reference footage. Not "it should look hot" —
specific numbers.

```
[VFX Parameter Sheet — example: vehicle fuel fire]

ONSET (frames 0–12):
  Core color: #FF6B00 → #FFAA00 (orange to yellow-orange)
  Edge color: #2B1A00 (very dark brown-orange)
  Density at core: ~0.85
  Velocity direction: predominantly upward, 15° bias toward fuel source
  Turbulence scale: small (high frequency, tight wisps)

PEAK (frames 12–72):
  Core color: #FFFF80 (near white-yellow)
  Edge color: #FF4400 (deep orange)
  Smoke column core: #303030 (dark gray)
  Smoke column edge: #606060 (lighter gray)
  Density at core: 0.95
  Column height: approximately 3× vehicle height
  Turbulence scale: medium (lower frequency, larger rolling structures)

DISSIPATION (frames 72–252):
  Color shift: orange → dark brown → gray
  Density fall-off: exponential (drops to 0.3 by frame 120, 0.1 by frame 180)
  Trailing smoke: low velocity, drifts with ambient wind direction
  Ember behavior: present at peak and early dissipation, extinguish by frame 100

WHAT THIS EFFECT NEVER DOES:
  - Pure white smoke at any phase (this is a fuel fire — smoke is dark)
  - Symmetrical column (turbulence produces asymmetric structures)
  - Instantaneous onset (always a brief flash before column forms)
  - Rapid dissipation (fuel fires have long dissipation tails)
```

---

## Layer 5 — Contextual Conditions

### Composite Environment

**Background plate conditions:** What lighting is in the background plate?
The VFX must integrate — which means its color temperature, exposure,
and edge behavior must match the background plate, not just be internally
correct. A correctly simulated fire composited over a poorly matched
background reads as incorrect VFX even when the simulation is right.

**Camera conditions:** What lens, exposure, and frame rate was the
background plate shot with? Motion blur behavior, lens flare, and
exposure response must match. A VFX element simulated for 24fps in
a 48fps plate is immediately visible.

**Lighting reference in the plate:** Does the VFX have a practical
equivalent in the plate? (A hero explosion that blows up a practical
pyrotechnic will have matching practical light in the plate.)
Or is the VFX entirely CG? If entirely CG, the lighting response
must be engineered rather than matched.

### Real-Time Context (Games)

For real-time VFX (Niagara, VFX Graph):

**Scene lighting:** How does the particle system interact with scene
lighting? Unlit particles ignore scene lighting (appropriate for some
effects). Lit particles respond to it (appropriate for others). Wrong
choice produces VFX that floats or disappears depending on scene conditions.

**Performance budget:** What is the maximum particle count, draw call
budget, and overdraw allowance for this effect at the target platform?
These constraints define what level of simulation complexity is achievable.

---

## Layer 6 — Behavior & Construction

### Physical Behavior Reference

Real-world physics are Layer 6 primary reference for VFX. Not other
VFX — real physics. The behavior that makes CG VFX convincing is not
artistic — it is physical. Correct turbulence frequency for a given
Reynolds number. Correct buoyancy for the temperature differential.
Correct drag coefficient for the particulate type.

**Key physical behaviors to reference:**

*Fire:*
- Combustion temperature determines color (blackbody radiation: blue > white > yellow > orange > red = decreasing temperature)
- Buoyancy drives vertical velocity — hotter fire rises faster
- Turbulence is driven by the Kelvin-Helmholtz instability at the fire's boundary with cooler air

*Smoke:*
- Density decreases with altitude due to cooling and mixing
- Wind shear creates horizontal structure in smoke columns
- Smoke rises until it reaches thermal equilibrium with surrounding air, then spreads laterally

*Water / fluid:*
- Turbulent flow creates characteristic Kolmogorov micro-structures
- Surface tension dominates at small scales, gravity at large scales
- Spray droplet size distribution follows a power law

*Explosions:*
- Initial shockwave is faster than sound — visible as a ring before the fireball
- Fireball achieves maximum radius before smoke column forms
- Negative pressure (underpressure) follows positive pressure — inward suction after outward blast

### Pipeline-Specific Reference

**Houdini:**
- Pyro solver parameters map to real physical properties: temperature, fuel, density
- Turbulence parameters (disturbance, dissipation) have real-world equivalents in Re numbers
- Gather reference for specific solver parameters, not just visual reference

**Niagara (UE5):**
- Real-time budget constraints dominate — reference must include budget benchmarks
  from comparable real-time effects
- Particle count vs. visual quality trade-off reference from published UE5 case studies

**EmberGen:**
- Gather reference for simulation presets that match the target phenomenon
- Real-time GPU sim — reference should include performance vs. quality benchmarks

---

## Layer 7 — Precision Detail

### What to Find

**Micro-structure within the effect:** The detail at the edge of a fireball
(individual finger-like extensions before they're consumed), the structure
of smoke tendrils, the shape of individual water droplets at the spray edge.

**Secondary elements:** Embers from a fire (count, size, velocity, trajectory,
lifetime). Debris from an explosion (type, scale, velocity range, tumble rate).
Secondary smoke from cooling residue.

**Looping behavior (if looping):** Real effects don't loop. If the effect
must loop (real-time ambient effects), the loop points must be invisible.
Reference the techniques used in comparable looping VFX — cycle offset,
crossfade, multiple instance stagger.

---

## The VFX Reference Brief

```
PROJECT: [effect name]
PHENOMENON: [specific real-world phenomenon, named precisely]
FUNCTION: [hero / supporting / ambient]
PIPELINE: [Houdini offline / Niagara real-time / EmberGen / AE / Nuke]
DATE: [brief version date]

LAYER 1 — FUNCTION & CONTEXT
Phenomenon (precise name):
Narrative function:
Camera distance and angle:
Compositional context (what's behind it):

LAYER 2 — SCALE & TIMING
Physical scale:
Onset duration (frames at target fps):
Peak duration (frames):
Dissipation duration (frames):
Real footage source used for timing:

LAYER 3 — PHASE REFERENCE
Onset reference source:
Peak reference source:
Dissipation reference source:

LAYER 4 — GOVERNING RULES (fill per phase)
ONSET: core color / edge color / density / velocity / turbulence scale
PEAK: core color / edge color / density / column dimensions / turbulence scale
DISSIPATION: color shift sequence / density curve / trailing behavior

What this effect NEVER does:

LAYER 5 — CONTEXTUAL CONDITIONS
Background plate lighting:
Camera: lens / exposure / frame rate
Real-time budget (if applicable): max particles / draw calls / overdraw

LAYER 6 — PHYSICAL BEHAVIOR
Key physical behaviors documented:
Pipeline-specific parameter targets:

LAYER 7 — PRECISION DETAIL
Secondary elements (embers, debris, spray):
Micro-structure at edges:
Looping strategy (if looping):

GAPS:
Critical:
High:

BRIEF VERSION: [v1.0 / v2.0 / vFinal]
```

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
