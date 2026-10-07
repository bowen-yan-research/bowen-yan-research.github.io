---
layout: page
title: research
permalink: /projects/
nav: true
nav_order: 1
description: From reasoning and recovery to sensing and soft robotic systems.
---

<link rel="stylesheet" href="{{ '/assets/css/bowen.css' | relative_url }}">

<div class="bw-project" markdown="1">
## Diagnosing and recovering from manipulation failures

How can a robot understand why an action failed—and decide how to recover? My work on VLM-guided VLA fault recovery connects fault diagnosis with spatial corrections and temporal rollback decisions.

**Related work:** _Can VLMs Diagnose and Recover from VLA Manipulation Faults?_ · ICML 2026
</div>

<div class="bw-project" markdown="1">
## Reasoning about constraints and communicating actions

**TextMani** studies how language models can translate tasks into explicit physical constraints, diagnose failures during execution, and repair the relevant part of a plan. **ActBox** investigates visual boxes, image grids, and textual coordinates as ways to communicate actions to vision-language models.

TextMani is under review at ICLR 2027. ActBox is under review at ICASSP 2027.
</div>

<div class="bw-project" markdown="1">
## Soft robots and optical sensing

My earlier work spans soft robotic mechanisms, custom actuators, optical sensing hardware, finite element analysis, and system-level experiments. **Puff-Pssss** brings these components together for adaptive pipe inspection; the manuscript is under major revision at IEEE Robotics and Automation Letters.

I have also explored fiber-optic sensing, shape-sensing grippers, soft sensor simulation, and the integration of tactile information with robot learning.

<img class="bw-media" src="{{ '/assets/img/sensing-prototype.jpg' | relative_url }}" alt="A flexible sensing prototype and its interface electronics on a laboratory workbench" loading="lazy">
<p class="bw-note">A sensing prototype from my earlier experimental work.</p>
</div>

<div class="bw-project" markdown="1">
## Experiments in simulation and tactile learning

These demonstrations document explorations of soft sensor simulation and tactile information in robot learning.

### Soft sensor simulation

<video class="bw-media" controls playsinline preload="none" poster="{{ '/assets/video/soft-sensor-simulation.mp4.jpg' | relative_url }}" aria-label="Soft sensor simulation demonstration"><source src="{{ '/assets/video/soft-sensor-simulation.mp4' | relative_url }}" type="video/mp4">Your browser does not support embedded video.</video>

### Tactile learning experiment

<video class="bw-media" controls playsinline preload="none" poster="{{ '/assets/video/tactile-learning.mp4.jpg' | relative_url }}" aria-label="Tactile learning experiment"><source src="{{ '/assets/video/tactile-learning.mp4' | relative_url }}" type="video/mp4">Your browser does not support embedded video.</video>
</div>
