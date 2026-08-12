---
title: "Aerodynamic Analysis of Concorde and Su-57 Nose Sections Using Schlieren Imaging"
collection: portfolio
category: Research
excerpt: "Schlieren imaging of scaled Concorde and Su-57 nose models at Mach 2.2, compared against oblique-shock and Taylor-Maccoll theory."
header:
  teaser: /images/Su57gif.gif
---
<img src="/images/Su57gif.gif" style="width:100%; border-radius:8px; margin-bottom:25px;">

**Aerodynamics Lab Project, IIT Kharagpur** — with my teammates Sai Palani Kumar G S, Viswasarathi N M, and Dinesh Bavan M P, under Prof. Sandeep Saha.

## Overview
We visualized supersonic shock structures over scaled nose models of the Concorde and the Su-57 at Mach 2.2 using schlieren imaging, then checked the measured shock angles against two levels of theory: 2D oblique-shock relations and the Taylor-Maccoll conical-flow equation. The two aircraft sit at opposite ends of supersonic design philosophy — a slender, axisymmetric cruiser versus a chined, faceted stealth fighter — so the comparison is really a study in how geometry alone reshapes the shock.

## Model Manufacturing
- Started from existing CAD/graphics files for both aircraft, isolated the nose sections, and lofted clean solid models scaled to fit the wind tunnel's 100 mm × 50 mm test section (Concorde: 85 mm tall, 25 mm max diameter; Su-57: 42.5 mm tall, 30 mm max diameter)

<img src="/images/schlieren-cad.jpg" style="width:70%; border-radius:6px; margin: 12px 0;" alt="Concorde and Su-57 CAD nose models">

- Machined both noses from mild steel to survive the tunnel's pressure loads: lathe-turned and drilled for a support-rod mount, then CNC-shaped (rough cut + smoothing pass) at the Central Workshop (SWISS Lab)

<img src="/images/schlieren-cnc.jpg" style="width:70%; border-radius:6px; margin: 12px 0;" alt="Concorde and Su-57 nose sections mounted in the CNC chuck">

- Used EDM (electrical discharge machining) to cleanly separate the finished nose from the CNC holding stock without inducing any mechanical stress or deformation
- Brass-welded a support rod to each model — brass's low melting point kept heat distortion minimal, preserving the sharp tip that's critical for getting an attached (rather than bow) shock

<img src="/images/schlieren-final-models.jpg" style="width:60%; max-width:400px; display:block; margin: 12px auto; border-radius:6px;" alt="Finished Concorde and Su-57 nose specimens with support rods">


## Schlieren Setup 
- Built a classic single-mirror schlieren rig: point light source collimated through a parabolic mirror, refocused through the test section onto a knife edge that converts density-gradient-driven ray deflection into visible brightness variation
- Used a candle flame to align the knife edge before each run — its plume gives an immediate, high-contrast check that the setup is in focus
- Ran the blowdown-type supersonic tunnel (6 atm supply, Mach 2.2) across four angles of attack (0°, 5°, 8°, 10°) for each model, recording video and extracting frames via a MATLAB script for the clearest shock structure at each angle

## Results & Analysis
- **Concorde:** a straight, attached conical shock at every angle of attack, with only mild top/bottom asymmetry — consistent with its slender, nearly axisymmetric ogive nose
- **Su-57:** a curved, attached shock at every angle, with much stronger top/bottom asymmetry — its chined, faceted geometry breaks axisymmetry and drives real 3D effects
- **Theory check:** modeling the Concorde nose as a 12° half-angle cone, the Taylor-Maccoll equation predicts a shock angle of 27.24°, matching the experimental ~27° almost exactly. A 2D wedge (θ-β-M) approximation of the same geometry overpredicts the shock angle by 5-10° — a direct, measured demonstration of the **3D relieving effect**, where a 3D body produces a weaker shock than an equivalent 2D wedge because flow can escape laterally around the body
- **AoA sensitivity:** the Concorde's shock angle barely moves with angle of attack (its smooth ogive shape lets flow expand laterally and compress nearly symmetrically), while the Su-57's shock angle shifts sharply — its sharp chines act like intensified wedge deflections that strengthen the upper shock and weaken the lower one as AoA increases

**Photos**
<div style="display:flex; gap:10px; flex-wrap:wrap; margin-bottom:20px;">
  <img src="/images/schlieren-concorde.png" style="width:48%; border-radius:6px;" alt="Concorde nose schlieren image">
  <img src="/images/schlieren-su57.png" style="width:48%; border-radius:6px;" alt="Su-57 nose schlieren shock wave, animated">
</div>

**Video**
<div style="position:relative; padding-bottom:56.25%; height:0; overflow:hidden; border-radius:8px; margin-bottom:20px;">
  <iframe src="https://www.youtube.com/embed/Woik4Ry7Jgw" title="Schlieren imaging demo" style="position:absolute; top:0; left:0; width:100%; height:100%; border:0;" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

**Report & Slides**
<a href="/files/Schlieren_Report.pdf" class="btn" target="_blank" rel="noopener">Download Report</a>
<a href="/files/Schlieren_Presentation.pptx" class="btn" target="_blank" rel="noopener">Download Slides</a>

