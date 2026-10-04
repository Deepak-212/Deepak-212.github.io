---
title: "Toward Safe and Efficient Predictive Control for Spacecraft Proximity Operations"
collection: portfolio
category: Research Internship
order: 1
description: "Convex tube MPC for coupled 6-DoF spacecraft motion using Difference-of-Convex dynamics, deployed on the DISCOWER ATMOS free-flyer."
advisor: "Caltech SURF Fellowship · Advised by Prof. Aaron D. Ames · with Yana Lishkova, Joe Moeller and Pedro Roque"
excerpt: "Difference-of-Convex tube MPC for spacecraft proximity operations, from 6-DoF simulation to free-flyer hardware."
header:
  teaser: /images/dc-tmpc-atmos/cbfatmos_teaser.webp
---

<p style="font-size:0.9em; opacity:0.8;"><em>Submitted to ICRA. A detailed write-up with full results will follow once the review process is complete.</em></p>

Close-proximity operations such as rendezvous and docking require a spacecraft to control its position and attitude together, perform efficiently, and never violate safety-critical constraints. This project tackles the full nonlinear, coupled 6-DoF problem with a tube-based convex Model Predictive Control (MPC) approach, using Difference-of-Convex (DC) functions to represent the nonlinear dynamics in a convex formulation.

## Approach in brief

We derive an analytical DC representation of the spacecraft model and also explore learned alternatives based on Input Convex Neural Networks (ICNNs) and SOS-convex polynomials. The complete 6-DoF formulation is evaluated numerically, and its planar restriction is deployed on the DISCOWER ATMOS free-flyer inside a layered control architecture with state estimation, safety filtering, and physical thruster actuation. Software-in-the-loop and hardware experiments demonstrate online operation and waypoint transfer on the platform.

## Experimental setup

The free-flyer is tracked by an OptiTrack motion-capture system, which provides the pose measurements used by the state estimator.

<div style="display:grid; grid-template-columns:repeat(auto-fit, minmax(240px, 1fr)); gap:1.25rem; margin:1.75rem 0;">
<figure class="project__figure" style="margin:0;">
  <img src="/images/dc-tmpc-atmos/optitrack_setup.jpg" alt="OptiTrack motion-capture setup around the ATMOS test table">
  <figcaption>OptiTrack motion-capture setup around the test table.</figcaption>
</figure>
<!-- <figure class="project__figure" style="margin:0;">
  <img src="/images/dc-tmpc-atmos/optitrack_calibration.gif" alt="Setting up and calibrating the OptiTrack system">
  <figcaption>Setting up the OptiTrack system.</figcaption>
</figure> -->
</div>

## Safety filter on hardware

Before closing the loop with MPC, the safety layer was tested on its own. A nominal controller deliberately tries to push the free-flyer off the table, and the control barrier function (CBF) filter minimally modifies each command so the robot stays inside the safe region.

<div style="display:grid; grid-template-columns:repeat(auto-fit, minmax(240px, 1fr)); gap:1.25rem; margin:1.75rem 0;">
<figure class="project__figure" style="margin:0;">
  <video src="/images/dc-tmpc-atmos/cbfatmos_web.mp4" autoplay loop muted playsinline preload="metadata" aria-label="CBF safety filter keeping the ATMOS free-flyer on the table"></video>
  <figcaption>Standalone CBF filter: the nominal command pushes outward, the filter keeps the robot on the table.</figcaption>
</figure>
<figure class="project__figure" style="margin:0;">
  <img src="/images/dc-tmpc-atmos/result.png" alt="Results of the standalone CBF filter experiment">
  <figcaption>Results from the standalone CBF experiment.</figcaption>
</figure>
</div>


