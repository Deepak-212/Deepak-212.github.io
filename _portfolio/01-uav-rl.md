---
title: "Safe Reinforcement Learning for Fixed-Wing UAV Control"
collection: portfolio
category: Research
excerpt: "Developed a safe RL controller for altitude tracking of a 6-DOF fixed-wing UAV."
header:
  teaser: /images/uav-rl.png
---
<img src="/images/uav-rl.png" style="width:100%; border-radius:8px; margin-bottom:25px;">
Research Intern • Robotic Research Centre, IIIT Hyderabad

Designed and implemented a nonlinear 6-DOF fixed-wing aircraft simulator based on the Beard & McLain aircraft model. Built a custom Gymnasium environment and trained a PPO controller for altitude tracking while incorporating a Control Barrier Function (CBF) safety filter to improve safety during learning and deployment.

**Key Contributions**
- Developed a nonlinear 6-DOF aircraft dynamics simulator in Python.
- Built a custom Gymnasium environment for reinforcement learning.
- Trained PPO agents using Stable Baselines3.
- Integrated Control Barrier Functions for safe control.
- Evaluated controller performance under different flight conditions.

**Tools**
Python • PyTorch • Gymnasium • Stable Baselines3 • NumPy