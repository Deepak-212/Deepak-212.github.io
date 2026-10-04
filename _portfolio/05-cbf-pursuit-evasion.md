---
title: "Encirclement and Capture in 3D with Control Barrier Functions"
collection: portfolio
category: Research
excerpt: "Volume-based CBF safety filter that lets four pursuers encircle and capture an evader in 3D against any evader strategy."
header:
  teaser: /images/cbf-pursuit-evasion/normal.gif
---
<img src="/images/cbf-pursuit-evasion/normal.gif" style="width:100%; border-radius:8px; margin-bottom:25px;">

Multi-agent pursuit–evasion framework in which four speed-limited pursuers trap a single evader inside their convex hull and close in for capture. Encirclement is encoded using the signed volumes of the sub-tetrahedra formed by the evader and each face of the pursuers' tetrahedron: the evader is enclosed exactly when all four volumes are non-negative. Treating these volumes as control barrier functions, a worst-case bound on the unknown evader velocity removes the evader input from the constraint entirely, so a nominal pure-pursuit law is filtered through a hard second-order cone program (SOCP) that keeps the evader enclosed against every admissible strategy, while also enforcing inter-pursuer collision and static-obstacle avoidance.

**Key Contributions**
- Signed-volume barrier functions that characterise 3D encirclement exactly
- Evader-independent CBF condition via a tight Cauchy–Schwarz bound, attained by a worst-case "normal-escape" evader
- Hard SOCP safety filter (no slack variables) coupling encirclement, collision-avoidance and obstacle-avoidance rows
- Monte Carlo campaigns with paired initial conditions across six evader policies
- 100% capture over 100 trials against the worst-case evader, with the hard SOCP feasible at every step

**Simulation Results: Centralized Controller**

All four pursuers' inputs are computed jointly in a single SOCP at each step.

<div style="display:grid; grid-template-columns:repeat(auto-fit, minmax(260px, 1fr)); gap:18px; margin:20px 0 30px;">

  <figure style="margin:0;">
    <img src="/images/cbf-pursuit-evasion/pursuit_normal.gif" style="width:100%; border-radius:8px;">
    <figcaption style="text-align:center; font-size:0.85em; margin-top:6px;">Worst-case evader (normal escape)</figcaption>
  </figure>

  <figure style="margin:0;">
    <img src="/images/cbf-pursuit-evasion/pursuit_gp.gif" style="width:100%; border-radius:8px;">
    <figcaption style="text-align:center; font-size:0.85em; margin-top:6px;">Greedy evader</figcaption>
  </figure>

  <figure style="margin:0;">
    <img src="/images/cbf-pursuit-evasion/pursuit_sp.gif" style="width:100%; border-radius:8px;">
    <figcaption style="text-align:center; font-size:0.85em; margin-top:6px;">Switching evader</figcaption>
  </figure>

  <figure style="margin:0;">
    <img src="/images/cbf-pursuit-evasion/pursuit_clp.gif" style="width:100%; border-radius:8px;">
    <figcaption style="text-align:center; font-size:0.85em; margin-top:6px;">Closest-link evader</figcaption>
  </figure>

  <figure style="margin:0;">
    <img src="/images/cbf-pursuit-evasion/pursuit_stp.gif" style="width:100%; border-radius:8px;">
    <figcaption style="text-align:center; font-size:0.85em; margin-top:6px;">stationary evader</figcaption>
  </figure>

  <figure style="margin:0;">
    <img src="/images/cbf-pursuit-evasion/pursuit_bep.gif" style="width:100%; border-radius:8px;">
    <figcaption style="text-align:center; font-size:0.85em; margin-top:6px;">evader moving towards the bisector of the edge</figcaption>
  </figure>

</div>

**Code**
<a href="https://github.com/Deepak-212/REPO-NAME" class="btn" target="_blank" rel="noopener">View on GitHub</a>
