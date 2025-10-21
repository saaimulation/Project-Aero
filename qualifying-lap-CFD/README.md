# 🏎️ Qualifying Lap — CFD  

"And here we are, lights out on the next stage of Project: Aero! The CAD lap is in the books, ST0 has rolled out of the garage, and it’s heading straight into the CFD arena. No wind tunnel, no factory-scale computers. Just me, SimScale, and a very nervous laptop fan."  

This part of the project is all about finding out if my RB19-inspired, regulation-legal, student-version-of-NX front wing can actually generate downforce… or if I’ve just built a very stylish drag machine.  

### 🎯 Goals  

- Import the geometry into SimScale and generate a clean mesh.  
- Run airflow simulations at baseline F1 speeds (~50 m/s to start).  
- Visualise pressure, velocity, and streamlines to understand behaviour.  
- See if the slot gaps and flap angles really do their job, or if I’ve engineered the world’s most expensive desk fan.  

### 🛠️ Tools  

- **SimScale** (meshing + solver + post-processing in one platform)  

---

Think of this as Q1 in qualifying: the aim isn’t to smash records yet, but to get a solid lap on the board. Once the pipeline works, we’ll push harder in Q2 and Q3 which means higher speeds, setup tweaks, and hopefully a lot more downforce.  

### 🧠 What I Expect to See  

- A clear pressure differential across the wing (high pressure above, low pressure below), confirming it generates downforce rather than lift.  
- Streamlines remaining attached through the slot gaps, if they detach too early, the wing stalls and performance drops off a cliff.  
- Evidence of Y250 vortex structures forming near the central section, helping control airflow downstream.  
- The outer flaps biasing flow outward around the tyres (like the RB19), reducing wake turbulence and drag.  
- Boundary layers that stay thin and attached, if they thicken or separate too much, I’ll know my flap angles were too aggressive.  

If I see these features, I’ll know the design philosophy was on the right track. If not… well, back to the CAD garage for ST1.  

---

# SimScale notes

So we begin. Starting off by importing my STL file into the software.

### Import and scale

<div>
  <img src="media/cfd1.png" alt="Initial import" width="49%">
  <img src="media/cfd3.png" alt="Scale check" width="49%">
</div>

Scaled the model by a factor of **0.001** to convert m → mm.

<div>
  <img src="media/cfdscaled.png" alt="After scaling" width="49%">
</div>

### Setup

Created an external flow volume and set up an incompressible simulation.

<div>
  <img src="media/cfd2.png" alt="External flow region" width="49%">
  <img src="media/cfdsetting.png" alt="Simulation settings" width="49%">
</div>

### What went wrong

Then came the errors. Many of them.

<div>
  <img src="media/cfderror.png" alt="Error 1" width="49%">
  <img src="media/cfderror2.png" alt="Error 2" width="49%">
</div>
<div>
  <img src="media/cfderror3.png" alt="Error 3" width="49%">
  <img src="media/cfderror5.png" alt="Error 5" width="49%">
</div>

Tried everything I could think of: tutorials, docs and forums. Tweaked the model, repaired faces, changed the flow region, removed tiny slots.  
Still no success.  After four days it was clear the blocker was geometry integrity, not the physics setup.

### Resources I used while debugging

- SimScale forum thread on [assigning materials to original geometry vs flow region](https://www.simscale.com/forum/t/my-original-geometry-and-flow-region-assigning-materials/99541/3)
- Official tutorial: [Formula Student car — Edit a copy](https://www.simscale.com/docs/tutorials/formula-student-car/#edit-a-copy)
- Knowledge base: [Intersections in the model](https://www.simscale.com/knowledge-base/intersections-in-model)
- Forum discussion: [Flat facet error](https://www.simscale.com/forum/t/flat-facet-error-and/90315)
- Video guide: [External aerodynamics in SimScale](https://www.youtube.com/watch?v=WsPy_TJotv4)

---

### Taking a step back

I decided to think about my options, since I was using a lot of time trying to debug this issue.   
Realising that it was an issue with my CAD, which I did not want to believe because it felt like I was going backwards.   
Regardless, I decided to look into it, and perfected my geometry for CFD testing.   

Here is how it went.  

### Fixing the geometry



## 🌟Star-CCM

I realised that there was a good route to take, which was to switch to Star-CCM.   

Let me explain:
1. I recently got a license from my university to use Star-CCM+
2. My role as an Aerodynamics Engineer for my Formula Student team only uses Star-CCM+
3. The UAS team first wanted me to teach the team how to use SimScale, but now they want me to do Star-CCM+ instead
4. My individual research project is with a supervisor who has 20 years of experience with Star-CCM+
5. Star-CCM+ is an industrial standard CFD software

In short, the answer was pretty clear, to go all-in on learning Star-CCM+.   

So that's what I did. 

