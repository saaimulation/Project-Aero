# 🏎️ Qualifying 2

"ST0 ends Q1 at the 17th position, let's see if the upgrades allow for some better racing"  

Welcome back! Q2!! With feedback and some advice from an F1 engineer!!!

---

## Feedback 🛠️

After sharing ST0 publicly, I received detailed technical feedback from an aerodynamicist currently working at Alpine F1 Team (name withheld). The review focused on regulation compliance, aerodynamic intent, CAD surface quality and CFD readiness.

### Overall assessment 📊
• The concept is strong for a second-year undergraduate project and technically suitable for CFD.  
• However, I was advised not to proceed with CFD yet, as the current geometry would not provide a meaningful aerodynamic baseline.  
• Refinement of the design should come before any simulation work.

### Regulations and concept 📐
• The wing is not currently FIA 2026 legal due to being configured as a four-element design.  
• A three-element front wing was recommended.  
• Regulation volumes should be created early in the design process to define legality and aero intent from the start.  
• Using regulation volumes would also help resolve issues such as excessive span and undersized endplates.

### Profiles and spanwise loading 🌬️
• The airfoil sections were identified as too thin for realistic aerodynamic loading.  
• Spanwise loading is heavily biased towards the centreline, reduces at mid-span, then increases again near the endplate.  
• This likely creates opposing vortical structures that remove energy from the flow rather than serving a clear downstream purpose.  
• I was encouraged to think more deliberately about where the flow is intended to go, how it interacts with the tyre wake, and how it feeds the floor.

### Surface quality and CAD approach 🧩
• Several mirrored and intersecting surfaces lack tangential continuity, creating geometric discontinuities.  
• A minimum of G1 continuity should be maintained across all surfaces.  
• In professional F1 environments, G2 or G3 continuity is typically targeted, though G1 is acceptable for this project.  
• Using lofts rather than sweeps was recommended, with three to four controlled sections to maintain surface quality and reduce unnecessary curvature.

### Endplates and footplates 🚧
• The endplates were highlighted as the weakest area of the design and require significant rework.  
• Discontinuities between the main body and footplates are likely to cause local flow stagnation and contaminate downstream flow into the floor.  
• Both inboard and outboard footplates are too thin, contributing to CFD geometry issues.  
• Some regions show unexpected local thickness, likely due to filleting or surface construction errors.

### Nose and main body 🧱
• The nose was described as overly flat and undersized relative to the aerodynamic loading it generates.  
• A slightly larger and more volumetric nose was suggested to improve flow management and continuity into the wing elements.

### CFD guidance 💻
• Although the geometry could technically be meshed, proceeding with CFD now would not be productive.  
• The priority should be improving surface continuity, thickness distribution and aerodynamic intent.  
• CFD should be used later to validate a cleaner and more efficient baseline.

---

## TL;DR 🧠🏎️

• Feedback came from an Alpine F1 aerodynamicist (name withheld out of respect).  
• The wing is CFD-able but not worth simulating yet due to inefficiency and geometry issues.  
• Major improvements needed in regulation compliance, surface continuity and aero intent.  
• Endplates and thickness distribution are the main weaknesses.  
• Concept is strong for my level and worth refining before CFD.

Despite the inefficiencies, the feedback concluded that the work is very strong for my level and demonstrates a high degree of ambition and iteration, well beyond a typical second-year undergraduate project.

## What’s Next – ST1 Roadmap 🧭🏎️

The next iteration (ST1) will focus on refining the concept into a regulation-led, CFD-ready baseline.

• Rebuild the front wing around FIA 2026 regulation volumes to ensure legality from the outset.  
• Reduce the configuration to a three-element wing and redefine element stacking and slot gaps.  
• Increase airfoil thickness to support realistic aerodynamic loading and improve flow robustness.  
• Rework spanwise loading distribution to remove opposing vortical structures and define clearer downstream intent.  
• Redesign endplates and footplates to improve continuity, reduce stagnation, and deliver cleaner flow to the floor.  
• Improve surface quality across all components, targeting full G1 continuity with smoother loft-driven geometry.  
• Adjust nose geometry to improve volumetric continuity and flow management into the wing elements.  
• Clean and simplify CAD topology to remove unintended thickness changes and prepare for meshing.  

Once these changes are implemented, ST1 will be used as the first meaningful CFD baseline, focusing on pressure distribution, flow attachment, and qualitative validation before further optimisation.


