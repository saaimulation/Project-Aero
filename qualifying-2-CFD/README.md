# 🏎️ Qualifying 2

"ST0 ends Q1 at the 17th position, let's see if the upgrades allow for some better racing"  

Welcome back! Q2!! With feedback and some advice from an F1 engineer!!!

---

## Feedback

After sharing ST0 publicly, I received detailed technical feedback from an aerodynamicist currently working at Alpine F1 Team. Out of respect, I will not name them. The review focused on regulation compliance, aerodynamic intent, surface quality and CFD readiness.

### Overall assessment
The concept was considered strong for a second-year undergraduate project and technically CFD-able. However, I was advised not to proceed with CFD at this stage, as the current geometry would not provide a meaningful baseline due to aerodynamic inefficiencies and surface discontinuities.

### Regulations and concept
The wing does not currently comply with the FIA 2026 regulations, as it was configured as a four-element design. A three-element front wing was recommended, with legality checked early using regulation volumes rather than retrospectively.

Creating regulation volumes was strongly encouraged as a starting point for the design process, both to ensure legality and to define aerodynamic intent from the outset. This would also help resolve issues such as excessive span and undersized endplates.

### Profiles and spanwise loading
The airfoil sections were identified as too thin for realistic aerodynamic loads, even if suitable for 3D printing. The spanwise loading was heavily biased towards the centreline, eased at mid-span, and increased again close to the endplate.

This distribution was likely generating opposing vortical structures that remove energy from the flow rather than contributing to a clear downstream objective. I was encouraged to think more deliberately about where the flow should go, how it interacts with the tyre wake, and how it feeds the floor.

### Surface quality and CAD approach
Several mirrored and intersecting surfaces lacked tangential continuity, creating points of geometric discontinuity. I was advised to ensure at least G1 continuity across all surfaces, noting that F1 surfaces are typically designed to G2 or G3.

It was recommended to rely more on controlled lofts rather than sweeps, using three to four well-defined sections to maintain surface control and reduce unintended curvature.

### Endplates and footplates
The endplates were highlighted as the weakest area of the design and in need of a significant rework. Discontinuities between the main body and footplates would likely cause local flow stagnation and send poor-quality flow downstream into the floor.

Both inboard and outboard footplates were considered too thin, which also contributed to CFD geometry issues. Some regions showed unexpected local thickness, likely due to filleting or surface construction errors.

### Nose and main body
The nose was described as overly flat and undersized relative to the loading it was producing. A slightly larger and more volumetric nose was suggested to improve flow management and continuity into the wing elements.

### CFD guidance
Although the geometry could technically be meshed, the advice was to delay CFD until the design was refined. The priority should be improving surface continuity, thickness distribution and aerodynamic intent before using CFD to validate a cleaner and more efficient baseline.

Despite these issues, the feedback concluded that the work was inefficient but very good for my level, and that the amount of iteration and ambition shown was well ahead of a typical second-year undergraduate project.

