---
title: "UAV Path Planning in Dynamic 3D Environments"
collection: portfolio
category: Research
description: "A space-time A* planner that routes multiple UAVs through 3D airspace with static and moving obstacles."
team: "Team project with Adeetya Uppal, Magizhan V, and Sudeep Prajapati"
excerpt: "Built a Space-Time A* planner that routes UAVs through 3D airspace with both static and moving obstacles."
header:
  teaser: https://github.com/Deepak-212/UAV-Path-Planning/raw/main/simulation/multi_uav_simulation_dynamic_obstacles.gif
---

We built a Python framework for planning UAV trajectories through constrained 3D airspace. The airspace, including its no-fly zones, is represented as a voxel-based 3D grid. A standard 3D A* search on this grid only knows *where* obstacles are, which is not enough once some of them move. Our central idea was to extend the search from three dimensions to four by adding time, so that the planner can reason about *when* a cell is occupied. This lets a UAV choose to wait in place for a moving obstacle to pass instead of colliding with it.

The planner also handles several UAVs at once. We use prioritized planning, in which each vehicle plans around the trajectories already reserved by higher-priority vehicles, to avoid mid-air conflicts. The cost function penalizes vertical ascent to reflect the higher battery cost of climbing, and a constraint-satisfaction (CSP) scheduler staggers departure times to reduce congestion at the start of a mission.

<figure class="project__figure">
  <img src="https://github.com/Deepak-212/UAV-Path-Planning/raw/main/simulation/multi_uav_simulation_dynamic_obstacles.gif" alt="Multiple UAVs planning around moving obstacles">
  <figcaption>Multiple UAVs routing through 3D airspace with moving obstacles.</figcaption>
</figure>

The code is available on [GitHub](https://github.com/Deepak-212/UAV-Path-Planning).
