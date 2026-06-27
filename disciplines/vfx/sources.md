# VFX — Reference Sources

Best sources for Reference Engineering in VFX, by Pyramid layer.

**Contributed by:** Atharva Patil — Northbyte Studios
**Last updated:** 2026-06-22

---

## Layer 1 — Phenomenon Identity

**YouTube — Slow Motion Channels** — FREE
The Slow Mo Guys (700fps–100,000fps real phenomena). Warwick University
slow motion. US Army Research Laboratory footage. Search the specific
phenomenon — "gasoline fire slow motion", "explosion slow motion",
"water impact slow motion". Primary-tier Layer 1 and Layer 3 reference.

**NIST Fire Research** — FREE
nist.gov/fire — National Institute of Standards and Technology fire
research footage. Real fire under controlled conditions at documented
scales. Primary-tier for fire type identification and behavior reference.

**NOAA / National Weather Service** — FREE
weather.gov and NOAA archives — weather phenomena footage (lightning,
tornado, waterspout, fog, cloud formations). Primary-tier for weather VFX.

**US Geological Survey (USGS)** — FREE
usgs.gov — volcanic, flood, earthquake, and geological phenomena footage.
Primary-tier for natural disaster VFX.

---

## Layer 2 — Timing and Scale

**Frame counting in slow-motion footage** — PRIMARY METHOD
Use a video editor or player with frame-by-frame playback. Count frames
from onset to peak and from peak to dissipation. Convert to 24fps
equivalent by dividing by the slow-motion frame rate multiplier.
This is the most accurate timing reference method available.

**Published VFX Breakdowns (for scale context)** — FREE
VFX breakdowns from film productions (YouTube, Art of VFX website)
document the scale of specific effects. Use for scale context only —
not for behavior reference. Secondary tier for scale.

---

## Layer 3 — Phase Reference

**The Slow Mo Guys** — FREE
youtube.com/theslowmoguys — covers fire, water, explosions, impacts,
electricity, and more at extreme frame rates. Best single source for
onset and dissipation phase reference — normal speed footage compresses
these phases; slow motion reveals them.

**Pond5 / Artgrid / Storyblocks** — PAID
Stock footage archives. Search by phenomenon and filter for slow-motion.
Better organized than YouTube for professional research. Some free tiers.

**Archive.org** — FREE
Public domain footage archive. Historical footage of phenomena. Useful
for large-scale events (nuclear tests, major fires, floods) with less
safety and legal overhead than finding primary documentation.

---

## Layer 4 — Governing Rules

**Blackbody Radiation Color Chart** — FREE
Search "blackbody radiation color temperature chart." Primary-tier
reference for fire and combustion color. The color of fire is determined
by temperature, not by fuel type alone. The chart converts temperature
(Kelvin) to visible color — use it to document the color progression
of a fire effect from cool (orange) to hot (white-blue).

**Published Houdini/Niagara/EmberGen Tutorials with parameter documentation**
Good tutorials document the relationship between real physical behavior
and simulation parameters. Use these as Secondary-tier Layer 4 reference —
they show how physical behavior translates to sim parameters.

**SideFX Houdini Documentation** — FREE
sidefx.com/docs — Houdini's pyro and fluid solver documentation explains
the physical meaning of each parameter. Primary-tier for understanding
the connection between real behavior and sim controls.

---

## Layer 5 — Contextual Conditions

**The Art of VFX** — FREE
artofvfx.com — VFX breakdowns including composite environment discussion.
Shows how VFX artists solved the integration problem for specific shots.
Secondary-tier for composite context reference.

**RocketStock / Motion Array** — FREE / PAID
Stock background plates and HDRI environments. Use as proxy composite
environment when the actual background plate is not yet available.

**Polyhaven HDRIs** — FREE (CC0)
Real-world lighting environments for testing VFX integration. Match the
HDRI conditions to the conditions of the background plate for more
accurate development preview.

---

## Layer 6 — Physical Behavior

**"An Introduction to Fluid Dynamics" (Batchelor)** — PAID (book)
The primary academic reference for fluid dynamics. Layer 6 primary-tier
for any fluid, smoke, or fire simulation. Not a tutorial — a physics
resource for understanding why fluids behave as they do.

**Physics of Fire (various academic sources)** — FREE
Search "fire combustion physics" on Google Scholar. Academic papers on
combustion chemistry, flame structure, and smoke formation. Primary-tier
for understanding fire behavior at the physics level.

**SideFX Houdini Learning Paths** — FREE
sidefx.com/learn — official Houdini learning resources including pyro
fundamentals. Bridges physical behavior and simulation parameters.

**Niagara Documentation (UE5)** — FREE
docs.unrealengine.com — Niagara system documentation. Primary-tier for
real-time VFX implementation reference. Includes performance optimization
guidance relevant to Layer 5 budget constraints.

**EmberGen Documentation** — FREE
jangafx.com/software/embergen — EmberGen's documentation includes
parameter explanations connected to physical behavior.

---

## Layer 7 — Precision Detail

**The Slow Mo Guys (extreme slow motion)** — FREE
At the highest frame rates (100,000fps), individual droplets, ember
particles, and micro-structures within effects become visible. Primary-tier
Layer 7 reference for secondary element behavior.

**Houdini Procedural VFX Community Resources** — FREE
SideFX forums, Rebelway community, Applied Houdini tutorials. Secondary-tier
for secondary element simulation techniques.

**VFX Supervisor Masterclasses (BAFTA, ACM SIGGRAPH)** — FREE / PAID
Published talks from VFX supervisors on large-scale productions. SIGGRAPH
proceedings include technical papers on specific VFX techniques.
Secondary-tier for understanding how production effects achieved
specific detail behaviors.

---

*Part of the Reference Engineering library — github.com/p4inz-code/reference-engineering*
*Framework by Atharva Patil — Northbyte Studios — 2026*
