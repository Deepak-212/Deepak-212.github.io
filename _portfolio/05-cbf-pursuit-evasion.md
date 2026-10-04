---
title: "Encirclement and Capture in 3D with Control Barrier Functions"
collection: portfolio
category: Research Projects
order: 1
description: "A volume-based control barrier function safety filter that lets four pursuers encircle and capture an evader in 3D, whatever strategy the evader uses."
advisor: "Advised by Prof. Ashish Hota, Dept. of Electrical Engineering, IIT Kharagpur"        # uncomment and fill in if applicable
excerpt: "Volume-Based Control Barrier Functions for Encirclement and Capture in 3D."
header:
  teaser: /images/cbf-pursuit-evasion/pursuit_normal.gif
---

In multi-agent pursuit–evasion, chasing the evader directly is rarely enough: a faster or cleverer evader simply slips through the gaps between the pursuers. A more reliable strategy is to first surround the evader and then tighten the net. This project studies that problem in three dimensions, where four speed-limited pursuers must trap a single evader inside their convex hull, a tetrahedron, and then close in for capture, without ever letting it escape along the way.

<figure class="project__figure">
  <img src="/images/cbf-pursuit-evasion/pursuit_normal.gif" alt="Four pursuers encircling and capturing an evader in 3D">
  <figcaption>Four pursuers keep the evader enclosed in their tetrahedron while closing in for capture.</figcaption>
</figure>

## Encoding encirclement

The key observation is that encirclement in 3D can be expressed exactly through volumes. The evader and each face of the pursuers' tetrahedron together form a smaller sub-tetrahedron, and the signed volume of each of these four sub-tetrahedra tells us which side of that face the evader is on. The evader is enclosed precisely when all four signed volumes are non-negative. This turns a geometric condition into four smooth scalar functions, which we treat as control barrier functions (CBFs).

The difficulty is that the barrier conditions depend on the evader's velocity, which the pursuers do not know. We remove this dependence with a worst-case bound on the evader's velocity, derived from the Cauchy–Schwarz inequality. The bound is tight: it is attained by a "normal-escape" evader that moves straight out through a face of the tetrahedron. Because the resulting condition no longer contains the evader's input at all, any pursuer action that satisfies it keeps the evader enclosed against every admissible evader strategy.

## The safety filter

The pursuers follow a simple nominal pure-pursuit law, and every command is passed through a safety filter before it is applied. The filter is a second-order cone program (SOCP) that finds the action closest to the nominal one while satisfying the encirclement constraints together with inter-pursuer collision avoidance and static-obstacle avoidance. The constraints are enforced as hard constraints, with no slack variables, so the filter never trades safety for performance.

## Results: centralized controller

In the centralized version, the inputs of all four pursuers are computed jointly in a single SOCP at each time step. We evaluated it in Monte Carlo campaigns that used paired initial conditions across six different evader policies, so that every policy faced exactly the same starting configurations. Against the worst-case normal-escape evader, the pursuers achieved capture in all 100 trials, and the hard SOCP remained feasible at every step.

<div style="display:grid; grid-template-columns:repeat(auto-fit, minmax(240px, 1fr)); gap:1.25rem; margin:1.75rem 0;">
<figure class="project__figure" style="margin:0;">
  <img src="/images/cbf-pursuit-evasion/pursuit_normal.gif" alt="Worst-case normal-escape evader">
  <figcaption>Worst-case evader (normal escape)</figcaption>
</figure>
<figure class="project__figure" style="margin:0;">
  <img src="/images/cbf-pursuit-evasion/pursuit_gp.gif" alt="Greedy evader">
  <figcaption>Greedy evader</figcaption>
</figure>
<figure class="project__figure" style="margin:0;">
  <img src="/images/cbf-pursuit-evasion/pursuit_sp.gif" alt="Switching evader">
  <figcaption>Switching evader</figcaption>
</figure>
<figure class="project__figure" style="margin:0;">
  <img src="/images/cbf-pursuit-evasion/pursuit_clp.gif" alt="Closest-link evader">
  <figcaption>Closest-link evader</figcaption>
</figure>
<figure class="project__figure" style="margin:0;">
  <img src="/images/cbf-pursuit-evasion/pursuit_stp.gif" alt="Stationary evader">
  <figcaption>Stationary evader</figcaption>
</figure>
<figure class="project__figure" style="margin:0;">
  <img src="/images/cbf-pursuit-evasion/pursuit_bep.gif" alt="Evader moving toward the bisector of an edge">
  <figcaption>Edge-bisector evader (heads toward the bisector of an edge)</figcaption>
</figure>
</div>