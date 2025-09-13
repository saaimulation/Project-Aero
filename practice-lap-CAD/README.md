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

---

### 🚦 The Start  

My first attempt? The nose.  
Disaster.  

![fail1](./screenshots/fail1.png)  
![fail2](./screenshots/fail2.png)  

After an hour of pain, I decided to start simpler with the mainplane.  

According to the FIA 2026 regs, the front wing can be 1900 mm wide in total. Since I only needed half-span, I went with 800 mm for the mainplane, leaving ~150 mm clear for the endplate.  

![flap1](./screenshots/flap1.png)  

What I built:  
- Leading edge fillet radius 5 mm for smoother airflow  
- Trailing edge fillet radius 50 mm to encourage downforce rather than lift  
- Thickness set to 10 mm in line with regs  

Not the perfect aerofoil, but as a baseline it ticked FIA boxes and gave me a platform for the stack.  

---

### 📐 Datum Planes: My Secret Weapon  

Since I couldn’t curve or sweep faces, I leaned on angled datum planes to create flaps at different incidences.  
This was the breakthrough that let me mimic some RB19 flavour.  

![planeangle](./screenshots/planeangle.png)  

For context, here’s the Audi 2026 concept I referenced alongside the FIA renders. Having these in mind kept me within the legal boxes while still aiming for something F1-inspired.  

![audiconcept](./screenshots/audiconcept.png)  

---

### 🪂 Flap 2, 3 and 4  

Using angled datum planes:  
- Flap 2 at +5°  
- Flap 3 at +10°  
- Flap 4 at +20° (my “DRS-inspired” big hitter)  

Each was extruded to 8–10 mm thickness with filleted edges for realism.  

![2ndflap](./screenshots/2ndflap.png)  

One FIA rule I had to watch carefully: no visible slot gaps from top view.  
My first try? Fail.  

![topviewgaps](./screenshots/topviewgaps.png)  

Quick fix by adjusting the plane offsets:  

![topviewfixes](./screenshots/topviewfixes.png)  

With all four stacked, the wing finally started to look like something that belonged on an F1 car rather than a student assignment.  

![allflaps](./screenshots/allflaps.png)  
![allflaps2](./screenshots/allflaps2.png)  

---

### 🧱 The Endplate  

Trickier than expected. Without surface sweeps, I built the endplate as a 6 mm thick extrusion, then sculpted it with arcs and triangle cut-outs.  

![basicendplate](./screenshots/basicendplate.png)  

At first the final flap didn’t meet the endplate cleanly:  

![endplategap](./screenshots/endplategap.png)  

Fixed it by adjusting the sketch and re-aligning with the flap edge:  

![endplategapfix](./screenshots/endplategapfix.png)  

To improve airflow and allow some outwash past the tyres, I added slots with 80 mm fillets. These are a common trick for managing the Y250 vortex and reducing drag.  

![slot1](./screenshots/slot1.png)  
![slot2](./screenshots/slot2.png)  
![slot3](./screenshots/slot3.png)  

---

### 👃 The Nose  

Back to where I started, but this time with more confidence.  
Two rectangles, a couple of arcs, extruded at 10° with fillets — and I had a legal FIA-style nose.  

![nose](./screenshots/nose.png)  
![nosefront](./screenshots/nosefront.png)  

In the 2026 regs, only the mainplane connects to the nose. The active flaps remain free for movable aero.  

![connection](./screenshots/connection.png)  

---

### 🏁 Final Model  

After mirroring across the ZY plane, I finally had a full-span wing.  

![finalfront](./screenshots/finalfront.png)  
![finalfront1](./screenshots/finalfront1.png)  
![finalangle](./screenshots/finalangle.png)  

---

### 🖤 Carbon Fibre Glam Shots  

Because every project deserves a photoshoot.  

![carbonangle](./screenshots/carbonangle.png)  
![carbonfront](./screenshots/carbonfront.png)  
![carbonangle1](./screenshots/carbonangle1.png)  
![othernangle](./screenshots/othernangle.png)  
![carbontop](./screenshots/carbontop.png)  
![anotherangle](./screenshots/anotherangle.png)  

---

### 📚 Lessons Learned  

- Work with the tools you’ve got. No curves? Use datum planes, arcs, and fillets. Creativity > features.  
- Regulations drive design. Width, thickness, gap rules — everything is boxed in.  
- RB19 inspiration works. Even simple tapering and angle changes made the design feel more “F1” than generic.  
- Iterate fast. Once flap 1 was sorted, 2–4 came much quicker.  
- Details matter. Fixing slot gaps and adding outwash slots might feel small, but they’re exactly what separates a legal design from an effective one.  

---

### ✅ Summary  

This is ST0, the first version of my 2026-spec front wing.  
- Built under student NX restrictions  
- Legal to FIA regs  
- RB19-inspired geometry where possible  

It’s not perfect and it’s not proven, but it’s a foundation. The next step is to validate this in CFD and see whether my logic holds up in the flow field.  

👉 CFD testing can be found here:  
[Project-Aero/qualifying-lap-CFD](../qualifying-lap-CFD/)  

That’s all for now. See you in qualifying 😉
