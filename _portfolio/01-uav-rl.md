---
title: "Safe Reinforcement Learning for Fixed-Wing UAV Control"
collection: portfolio
category: Research Projects
order: 2
description: "Altitude tracking for a 6-DOF fixed-wing aircraft with a learned controller and a control barrier function safety filter."
role: "Research Intern, Robotics Research Center, IIIT Hyderabad"
excerpt: "Developed a safe RL controller for altitude tracking of a 6-DOF fixed-wing UAV."
header:
  teaser: /images/uav-rl.png
---

Reinforcement learning can produce controllers for dynamics that are hard to model by hand, but a learned policy offers no built-in guarantee that it will stay within safe operating limits, either while it is being trained or once it is deployed. For a fixed-wing aircraft, the most immediate of these limits is stall. This project combines a learned altitude controller with a safety filter that keeps the aircraft away from stall.

The first step was a simulator. I implemented a nonlinear six-degree-of-freedom fixed-wing aircraft model in Python, following the formulation of Beard & McLain, and wrapped it as a custom Gymnasium environment so that standard reinforcement learning tooling could be used on it directly.

On this environment I trained PPO agents with Stable Baselines3 to hold and climb to a commanded altitude, including in the presence of wind gusts. The actions from the learned policy pass through a control barrier function (CBF) safety filter, which enforces stall-avoidance constraints and corrects the commanded action whenever it would take the aircraft outside the safe region. I then evaluated the combined controller across a range of flight conditions.

<figure class="project__figure">
  <img src="/images/uav-rl.png" alt="Altitude-hold performance of the trained RL agent">
  <figcaption>Altitude-hold performance of the trained agent.</figcaption>
</figure>
