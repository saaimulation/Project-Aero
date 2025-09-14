# 🏁 Practice Lap — CAD  

“And away we go! The first lap of Project: Aero. The garage doors are open, the tools are out, and the focus is on turning rough ideas into geometry that can actually be tested.”  

Hi, Saaim here👋 Welcome to the practice lap! This stage begins with the 2026 F1 regulations 📜 The new rules bring narrower cars, simplified aero and movable elements, all designed to reduce dirty air and keep racing close. Within those constraints, the target is to create a baseline front wing in Siemens NX.  

NX was chosen as the baseline CAD tool after advice from industry engineers, with CATIA as a natural future step once I’m confident in NX.

I thought about including the new active aerodynamics — Z-mode for high downforce in corners and X-mode for low drag on the straights — but decided to keep it simpler for now. That can be a future project 👀  

So before any sketches or CAD, it’s time to check the rulebook!

### 📜 FIA 2026 Front Wing Regulations (condensed)

- Maximum width reduced to **1900 mm** (100 mm narrower than 2022–25).  
- Must be a **single assembly**: mainplane, flaps, endplates, pylons.  
- Up to **4 profiles** allowed, with a fixed flap rotation axis.  
- Endplates must cover the FIA’s mandated reference boxes in both top and side views.  
- Smooth transition into the nose, with limited fillet radius (≤ 25 mm).  
- Active aero (Z/X modes) is permitted, but not included in my first version.  

**What this means for me**  
- I need to design within a narrower span and tighter FIA boxes.  
- Endplates must stay simple and legal; no overcomplicated tricks.  
- Flap geometry has to respect the fixed hinge axis.  
- Active aero is allowed in the regs, but I’ll skip it for now.  
- My target is a clean, rule-aware baseline wing that can be tested in CFD and the tunnel.  

📂 The full regulations can be found in this repo:  
`/practice-lap-CAD/fia_2026_technical_regulations.pdf`

---

### 🔎 Visual references (FIA concept)

**Front view**  
![Front view](./front2.jpg)

**Three-quarter renders**  
![3/4 render](./front.jpg)  
![Side view](./side.jpg)

---

## 🧭 Build plan & scaling

I’ll model a **full-size half-span** wing in NX (so 950 mm if the full span is 1900 mm). From there I’ll produce two physical versions:

1) **Wind-tunnel test article — half-span at 25% scale**  
   - Size: **237.5 mm** span (fits my 250 mm build plate for the Bambu A1)  
   - One-piece print if possible, otherwise 2-piece with alignment pins  
   - Used for tunnel testing and comparisons to CFD

2) **Display piece — full-span at ~35% scale**  
   - Size: **~665 mm** span (for photos, not tunnel)  
   - Printed in 3–4 sections with pins & glue
   - Lets me show the full geometry without needing a huge tunnel

If the tunnel ends up smaller, I’ll drop the half-span scale to 20% to keep things practical!

---

## 🎥 Short explainers I used

- F1 2026 aero overview: https://www.youtube.com/watch?v=HIEHRR7Sy1g  
- What changes & why it matters: https://www.youtube.com/watch?v=fXPZdvkKfbA  
- Another clear breakdown of the concept car: https://www.youtube.com/watch?v=5FyFerbm6Js

---

### 🏎️ RB19 Inspiration  

The RB19 was the most dominant car of the ground effect era, winning almost every race in 2023. Its front wing was a big part of that success — not because it looked crazy, but because it was refined everywhere that mattered.  

Some highlights worth stealing:  
- The flaps tapered toward the endplate which helped push air neatly around the front tyres.  
- The outer section had just enough curvature to bias the flow outward and clean up the tyre wake.  
- The stacking line across the elements was smooth so vortices stayed stable instead of breaking up into chaos.  
- The centre section near the nose was kept simple and low drag so the wing could work hardest at the outer span.  

For my project I will use the 2026 FIA concept as the baseline but I will sneak in some RB19 flavour. Flap tapering, outer sweep and a smooth stacking line are all on the menu. The aim is not to build Red Bull’s secret sauce but to let the most successful design of recent years inspire a student version that can survive CAD CFD and eventually my wind tunnel.  

![RB19 Front View](./rb19.jpg)

## 🧩 The CAD (finally)  
Here is what you are all waiting for. FINALLY, Saaim is actually going to model and show the front wing. I would also take this opportunity to say, that this is my first time using NX.  

Ever...  

Talk about jumping into the deep end, but that’s what makes it exciting 👀  

I started by adding some expressions so that scaling down would be a lot easier, which are shown below:  

![NX Expressions](expressions.png)

---

## Reference Images

To guide the design, I brought in FIA 2026 concept renders and RB19 references (which were very hard to find).  
This way I can stay within regulations while adding some of Red Bull's innovation!

### Top View Comparison
<p align="center">
  <img src="2026top.jpg" alt="2026 Top" width="400"/>
  <img src="rbtop.jpg" alt="RB19 Top" width="400"/>
</p>

### Front View Comparison
<p align="center">
  <img src="2026front.jpg" alt="2026 Front" width="400"/>
  <img src="rbfront.jpg" alt="RB19 Front" width="400"/>
</p>

So here we go! Loaded up NX, reference images in hand, tons of time. 

"this should be okay"

SAID NO-ONE EVER!!! As I was trying to insert my reference images, I was met with an amazing greeting:

![heartbreak](heartbreak.png)

I quickly realised the free student version of Siemens NX had a limited toolbox. No fancy curvature tools, no face manipulation, not even image references for guidance.  
So the game became about loopholes: datum planes, fillets, splines and persistence. 

## 🛠️ CAD Build Log — Practice Lap  

I quickly realised that the student version of Siemens NX had a limited number of tools, since it is not meant for commercial use.  
This meant that I couldn't curve flaps and move them at my will. So I utilised angles, filleting edges and just tried to find loopholes in what I could and couldn’t do.  

---

## 🚦 The Start  

I started off by making the nose of the car, which turned out terrible:  

<p align="center">
  <img src="./screenshots/fail1.png" width="400"/>
  <img src="./screenshots/fail2.png" width="400"/>
</p>  

After trying for an hour, I realised it would be better to start with the mainplane instead.  

With regulations stating the wing can only be 950 mm wide, I made the mainplane 800 mm, leaving 150 mm for the endplate design.  

![flap1](./screenshots/flap1.png)  

This had fillets of radius 5 mm at the front and 50 mm at the rear to create downforce (at least in theory, the CFD will confirm).  

Since I couldn’t use curves, moving faces or image references, I learned how to use datum planes. Creating planes at angles allowed me to get closer to the RB19 look.  

![planeangle](./screenshots/planeangle.png)  

For reference, here’s the Audi 2026 concept, which made it easier to grasp the new regulations and shapes of the flaps, nose and endplate:  

![audiconcept](./screenshots/audiconcept.png)  

---

## 🪂 Flaps  

The second flap was sketched on a 5° datum plane, using splines and arcs, then extruded to ~8–10 mm thickness (in line with regs).  

![2ndflap](./screenshots/2ndflap.png)  

One FIA rule is that there should be no visible gaps from the top view. My first attempt vs fix:  

<p align="center">
  <img src="./screenshots/topviewgaps.png" width="400"/>
  <img src="./screenshots/topviewfixes.png" width="400"/>
</p>  

I continued the same method for the 3rd and 4th flaps, taking inspiration from the RB19.  

<p align="center">
  <img src="./screenshots/allflaps.png" width="400"/>
  <img src="./screenshots/allflaps2.png" width="400"/>
</p>  

Overall, I was happy with the result. The process became simple once I figured out how to build the first flap.  

---

## 🧱 The Endplate  

This part was tricky. Without curve tools, I created a basic 6 mm thick extrusion united with the flaps:  

![basicendplate](./screenshots/basicendplate.png)  

At first, the last flap didn’t connect:  

<p align="center">
  <img src="./screenshots/endplategap.png" width="400"/>
  <img src="./screenshots/endplategapfix.png" width="400"/>
</p>  

For the outer curve, I used arcs and splines, then a triangular cut with a 3 mm fillet radius.  

<p align="center">
  <img src="./screenshots/endplatedge.png" width="400"/>
  <img src="./screenshots/endplateside.png" width="400"/>
</p>  

To improve airflow and allow outwash past the tyres, I added slots with 80 mm fillets. These help with drag reduction and vortex management.  

<p align="center">
  <img src="./screenshots/slot1.png" width="250"/>
  <img src="./screenshots/slot2.png" width="250"/>
  <img src="./screenshots/slot3.png" width="250"/>
</p>  

---

## 👃 The Nose  

Back to the beginning. Once I had more confidence, the nose became straightforward. A couple of rectangles and arcs on the XY plane, extruded at 10°, plus some fillets gave me this:  

<p align="center">
  <img src="./screenshots/nose.png" width="400"/>
  <img src="./screenshots/nosefront.png" width="400"/>
</p>  

In the 2026 concept, only the mainplane connects to the nose. The flaps remain separate for active aero.  

![connection](./screenshots/connection.png)  

---

## 🏁 Final Model  

After mirroring across the ZY plane, I finally had the full wing.  

<p align="center">
  <img src="./screenshots/finalfront.png" width="400"/>
  <img src="./screenshots/finalfront1.png" width="400"/>
</p>  

![finalangle](./screenshots/finalangle.png)  

---

## 🖤 Carbon Fibre, Why Not?

Because every project deserves a photoshoot.  

<p align="center">
  <img src="./screenshots/carbonangle.png" width="300"/>
  <img src="./screenshots/carbonfront.png" width="300"/>
  <img src="./screenshots/carbonangle1.png" width="300"/>
</p>  

<p align="center">
  <img src="./screenshots/otherangle.png" width="300"/>
  <img src="./screenshots/carbontop.png" width="300"/>
  <img src="./screenshots/anotherangle.png" width="300"/>
</p>  

---

## 📂 Download the CAD

For anyone who wants to check it out or 3D print it, here’s the model export:  

➡️ [Download FW2026Full (.stl)](./FW2026Full.stl)

This STL is the full mirrored version of ST0.  
It’s ready for printing and can also be imported into most CAD and CFD tools.  

If you’d like the parametric file with sketches and planes, let me know! I’ll add a STEP version later.


## 📚 Summary  

This stage of Project: Aero has been fun and insightful. With no tutorials, textbooks, guidance or external assistance, I used passion and creativity to build ST0, the first of many iterations.  

Even with the limitations of NX, I was able to:  
- Adhere to FIA regulations  
- Think about aerodynamic efficiency  
- Add RB19 features
- Learn a new software
- Use my creativity to design something from scratch

I hope to continue this work and make it better, and challenge myself to even harder concepts. 
Thank you for reading! If you had any questions or any advice, please reach out to me on LinkedIn!

The next step is CFD testing, which you can find here:  
[Project-Aero/qualifying-lap-CFD](../qualifying-lap-CFD/)  

### That’s all for now. See you in qualifying 😉  
