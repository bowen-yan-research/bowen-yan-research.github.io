---
layout: page
title: VLA-FixBench
permalink: /papers/vla-fault-recovery/
nav: false
description: Can VLMs Diagnose and Recover from VLA Manipulation Faults?
---

<link rel="stylesheet" href="{{ '/assets/css/vla-fixbench.css' | relative_url }}">

**ICML 2026**

**Bowen Yan†**, Jiahao Xiao†, Kehui Liu, Jianbo Zhang, Zicheng Zhang, Qi Jia, Zhongjie Jia, Haoming Song, Chunyi Li, Bin Zhao, and Guangtao Zhai.

† Equal contribution.<br>
Shanghai AI Laboratory · Shanghai Jiao Tong University · Nanyang Technological University

[Read the paper (PDF, 17.6 MB)]({{ '/assets/pdf/vla-fixbench.pdf' | relative_url }})

> Can a model that explains a robot's failure also help it recover? VLA-FixBench evaluates the gap between understanding a manipulation fault and producing a recovery action that works in the physical world.

<figure class="vfix-figure">
  <a href="{{ '/assets/img/papers/vla-fixbench/framework.png' | relative_url }}"><img src="{{ '/assets/img/papers/vla-fixbench/framework.png' | relative_url }}" width="1467" height="507" alt="VLA-FixBench pipeline: dataset construction, static diagnostic evaluation, and dynamic recovery evaluation in simulation and on real robots."></a>
  <figcaption>From annotated executions to static diagnosis and closed-loop recovery. Figure 2 from the paper; click to enlarge.</figcaption>
</figure>

## What does the benchmark measure?

VLA-FixBench contains **6,034 task-execution episodes** from **40 simulated task settings and two real-robot tasks**: tea preparation and charging-plug insertion. Annotations describe task stages, fault types, severity, failure timing, and spatial deviations. The dataset includes both failed and error-free executions.

The accompanying **FaultEval** framework evaluates **20 VLMs** across complementary settings:

- **Static diagnosis:** identify the fault, estimate its severity, and determine which subtasks succeeded.
- **Dynamic evaluation:** locate when execution should stop and roll back, estimate a 3D correction, and measure task completion in simulation.
- **Real-robot evaluation:** test whether diagnostic decisions translate into effective recovery on a Franka arm.

## How does recovery work?

The collaboration interface follows a **detect → rollback → correct** sequence:

1. **Detect and stop.** Identify a failure and choose when to pause execution.
2. **Roll back.** Select an earlier safe state in the execution history.
3. **Correct and resume.** Apply a 3D spatial offset and continue the task with the VLA policy.

On the real robot, diagnosis uses a **pause-and-inspect protocol**. The VLA executes for a one-second window, then robot motion and VLA inference pause while the VLM inspects the recorded segment. Each task typically involves three to six diagnoses; this is not continuous, latency-free intervention.

<figure class="vfix-figure vfix-sequence">
  <a href="{{ '/assets/img/papers/vla-fixbench/real-robot-recovery.png' | relative_url }}"><img src="{{ '/assets/img/papers/vla-fixbench/real-robot-recovery.png' | relative_url }}" width="705" height="297" loading="lazy" alt="Eight frames of a real-robot tea-preparation task, showing a stop, rollback, and successful recovery."></a>
  <figcaption>A successful recovery example in the tea-preparation task. Figure 6 from the paper; this example does not represent aggregate success rates.</figcaption>
</figure>

## Key findings

**Good diagnosis does not guarantee successful recovery.** Models must identify a useful rollback point and produce a sufficiently precise spatial correction. Incorrect interventions can interrupt trajectories that would otherwise succeed.

The real-robot results illustrate this gap:

<div class="vfix-table" markdown="1">

| Setting | Task success rate |
| :--- | ---: |
| GR00T-N1.5-3B policy without a VLM judger | 30% |
| Best automated VLM-assisted result in Table 3 (Gemini-2.5-Flash) | 25% |
| Human-expert intervention, used as an upper bound | 65% |

</div>

The **35-percentage-point improvement (30% → 65%) is the human-expert upper bound**, not an improvement achieved by the automated VLM judgers. All evaluated automated judgers in Table 3 remain below the VLA-only baseline. The human result demonstrates the potential of accurate recovery decisions; the automated results reveal the grounding and intervention problems still to solve.

## Takeaway

VLA-FixBench provides a testbed for evaluating both failure understanding and executable recovery. The results motivate more accurate temporal and spatial grounding, confidence-aware intervention, and safer correction policies—not simply more frequent fault detection.

<small>Dataset and setup: Section 3 and Appendix A. Recovery interface: Section 4.2. Real-robot results: Table 3. Inspection protocol and limitations: Section 5.4.</small>

---

[← All publications]({{ '/publications/' | relative_url }}) · [Research overview]({{ '/projects/' | relative_url }})
