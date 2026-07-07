---
title: "UAV Path Planning in Dynamic 3D Environments"
collection: portfolio
category: Research
excerpt: "Built a Space-Time A* planner that routes UAVs through 3D airspace with both static and moving obstacles."
header:
  teaser: https://github.com/Deepak-212/UAV-Path-Planning/raw/main/simulation/multi_uav_simulation_dynamic_obstacles.gif
---
<img src="https://github.com/Deepak-212/UAV-Path-Planning/raw/main/simulation/multi_uav_simulation_dynamic_obstacles.gif" style="width:100%; border-radius:8px; margin-bottom:25px;">

Python framework for planning UAV trajectories through constrained 3D airspace. The core idea is moving from a standard 3D A* search to a 4D space-time search, adding time as a fourth dimension so the planner can reason about *when* a cell is occupied, not just where obstacles are.

**Key Contributions**
- Voxel-based 3D grid for representing airspace and no-fly zones
- Extended A* into space-time so the planner can choose to wait rather than collide with a moving obstacle
- Prioritized planning across multiple UAVs to avoid mid-air conflicts
- Cost function that penalizes vertical ascent to reflect realistic battery constraints
- CSP-based departure scheduling to reduce congestion at mission start

**Code**
<a href="https://github.com/Deepak-212/UAV-Path-Planning" class="btn" target="_blank" rel="noopener">View on GitHub</a>



Team project with Adeetya Uppal, Magizhan V, and Sudeep Prajapati.