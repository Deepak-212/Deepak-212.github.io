---
title: "Schlieren Imaging & Supersonic Aerodynamic Analysis"
collection: portfolio
category: Research Projects
order: 4
description: "Schlieren imaging of scaled Concorde and Su-57 nose sections at Mach 2.2, compared against oblique-shock and Taylor-Maccoll theory."
advisor: "Supervisor: Prof. Sandeep Saha, Dept. of Aerospace Engineering, IIT Kharagpur"
excerpt: "Schlieren imaging of scaled Concorde and Su-57 nose models at Mach 2.2, compared against oblique-shock and Taylor-Maccoll theory."
header:
  teaser: /images/Su57gif.gif
---

The Concorde and the Su-57 sit at opposite ends of supersonic design philosophy: one is a slender, axisymmetric cruiser, the other a chined, faceted stealth fighter. We wanted to see how much that difference in geometry alone reshapes the shock in front of the aircraft. To find out, we machined scaled nose sections of both, visualized the shock structures over them at Mach 2.2 using schlieren imaging, and compared the measured shock angles against two levels of theory: 2D oblique-shock relations and the Taylor-Maccoll conical-flow equation.

<figure class="project__figure">
  <img src="/images/Su57gif.gif" alt="Schlieren video of the shock over the Su-57 nose">
  <figcaption>Schlieren footage of the attached shock over the Su-57 nose at Mach 2.2.</figcaption>
</figure>

## Making the models

We started from existing CAD and graphics files of both aircraft, isolated the nose sections, and lofted clean solid models scaled to fit the wind tunnel's 100 mm × 50 mm test section. The Concorde nose is 85 mm tall with a maximum diameter of 25 mm, and the Su-57 nose is 42.5 mm tall with a maximum diameter of 30 mm.

<figure class="project__figure project__figure--md">
  <img src="/images/schlieren-cad.jpg" alt="Concorde and Su-57 CAD nose models">
  <figcaption>CAD models of the Concorde (left) and Su-57 (right) nose sections.</figcaption>
</figure>

Both noses were machined from mild steel so that they would survive the tunnel's pressure loads. Each was turned on a lathe and drilled for a support-rod mount, then shaped on a CNC machine at the Central Workshop (SWISS Lab) with a rough cut followed by a smoothing pass. We used electrical discharge machining (EDM) to separate each finished nose from its CNC holding stock without introducing mechanical stress or deformation. Finally, a support rod was brass-welded to each model; brass's low melting point kept heat distortion to a minimum and preserved the sharp tip, which is what makes the difference between an attached shock and a detached bow shock.

<figure class="project__figure project__figure--md">
  <img src="/images/schlieren-cnc.jpg" alt="Concorde and Su-57 nose sections mounted in the CNC chuck">
  <figcaption>Nose sections mounted in the CNC chuck.</figcaption>
</figure>

<figure class="project__figure project__figure--sm">
  <img src="/images/schlieren-final-models.jpg" alt="Finished Concorde and Su-57 nose specimens with support rods">
  <figcaption>The finished models with their support rods.</figcaption>
</figure>

## The schlieren setup

We built a classic single-mirror schlieren rig. Light from a point source is collimated by a parabolic mirror, passes through the test section, and is refocused onto a knife edge. Density gradients in the flow deflect the light rays slightly, and the knife edge turns those deflections into visible changes in brightness. Before each run, we aligned the knife edge using a candle flame, whose plume gives an immediate, high-contrast check that the system is in focus.

Each model was tested in a blowdown supersonic tunnel (6 atm supply, Mach 2.2) at four angles of attack: 0°, 5°, 8°, and 10°. We recorded video of every run and used a MATLAB script to extract the frames showing the clearest shock structure at each angle.

## Results

The two noses behaved very differently. The Concorde produced a straight, attached conical shock at every angle of attack, with only mild asymmetry between the top and bottom, which is consistent with its slender, nearly axisymmetric ogive shape. The Su-57 produced a curved, attached shock at every angle, with much stronger top-to-bottom asymmetry: its chined, faceted geometry breaks axisymmetry and introduces genuinely three-dimensional effects.

<figure class="project__figure">
  <div class="project__figure-row">
    <img src="/images/schlieren-concorde.png" alt="Concorde nose schlieren image">
    <img src="/images/schlieren-su57.png" alt="Su-57 nose schlieren image">
  </div>
  <figcaption>Schlieren images of the Concorde (left) and Su-57 (right) noses.</figcaption>
</figure>

The comparison with theory was the clearest result. Modelling the Concorde nose as a cone with a 12° half-angle, the Taylor-Maccoll equation predicts a shock angle of 27.24°, which matches the measured value of about 27° almost exactly. A 2D wedge (θ-β-M) approximation of the same geometry overpredicts the shock angle by 5–10°. This gap is a direct measurement of the **3D relieving effect**: a three-dimensional body produces a weaker shock than an equivalent 2D wedge because the flow can escape sideways around it.

The two noses also responded differently to angle of attack. The Concorde's shock angle barely changed, since its smooth ogive shape lets the flow expand laterally and compress almost symmetrically. The Su-57's shock angle shifted sharply instead. Its sharp chines act like stronger wedge deflections, so as the angle of attack increases they strengthen the upper shock and weaken the lower one.

<div class="project__video">
  <iframe src="https://www.youtube.com/embed/Woik4Ry7Jgw" title="Schlieren imaging demo" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

The full [report](/files/Schlieren_Report_11zon.pdf) and [slides](/files/Schlieren_Presentation.pdf) are available for more detail.
