---
layout: post
title: "PhD Summary | Optimizing for Holistic VR Interaction"
excerpt: "Three years of doctoral research distilled into key actionable takeaways for VR UI designers, accessibility advocates, current VR Developers and HMD manufacturers."
categories: [VR🥽,Publication📕]
comments: true
image:
  feature: feature/11.jpg
galleries:
 1:
   - { url: '/img/filter/filter.PNG', alt: '1-Euro VR filter diagram' }
 2:
   - { url: '/img/filter/vr.png', alt: 'Illustration of VR UI placement guidelines' }
   - { url: '/img/filter/Capture.PNG', alt: 'Experiment screenshot - tremor reduction' }     
 3:
   - { url: '/img/filter/noise.gif', alt: 'GIF showing tremor noise in VR' }
   - { url: '/img/filter/ev.gif', alt: 'GIF showing tremor reduction with filter' }
 4:
   - { url: '/img/filter/slider.png', alt: 'Slider interaction experiment' }
   - { url: '/img/filter/button.png', alt: 'Button interaction experiment' }
 5:
   - { url: '/img/modular/ui.gif', alt: '3D modular interface in VR' }
   - { url: '/img/modular/panel.PNG', alt: 'Panel placement in VR' }
 6:
   - { url: '/img/modular/yove.gif', alt: 'Kinematic UI panel physics interaction' }
 7:
   - { url: '/img/modular/new.PNG', alt: 'Point cloud data with modular UI overlay' }
---

# TL;DR – Developer-Focused Takeaways
✅ Tremors can be reduced in consumer VR using a 1-Euro filter.  
✅ 3D Interfaces can be modular.  
✅ 3D Interfaces can be multi-modal.  
✅ There is a comfort range based on human anatomy to place VR UI.  

---

# Introduction
This post distills my doctoral research *Optimising for Holistic VR Interaction* into practical, immediately applicable insights for VR developers, UX designers, and HMD manufacturers. While grounded in academic methodology, the focus here is accessibility, comfort, and efficiency in real-world VR development.

---

## Chapter 1 – Accessible VR Interaction Model
This research investigates the use of a 1-Euro low-pass filter to reduce involuntary tremors during fine motor control tasks in VR. While natural tremors occur in all humans, they are exaggerated in VR due to controller sensitivity and tracking noise. A lightweight, velocity-based low-pass filter can significantly reduce tremor impact without interfering with intentional fast movements, making interactions smoother and more precise.

{% include gallery.html gallery=1 %}
*Figure 1. Diagram of the 1-Euro Filter process for tremor reduction.*

> I want to see this filter integrated into every VR HMD Accessibility Menu with a toggle. It’s just a single script.

**Pre-Print** available [here](https://arxiv.org/abs/2405.07335)  
**Git Study Repo** available [here](https://github.com/corriedotdev/vr-tremor-reduction)  

All of us have benign essential tremors. In VR, these become especially noticeable when selecting items in menus using laser pointers. The 1-Euro filter removes much of this noise while preserving responsiveness.

{% include gallery.html gallery=3 %}
*Figure 2. Visual comparison of pointer movement with and without tremor filtering.*

### Study
30 participants (no known neuromuscular disorders) interacted with 2D buttons and sliders at various distances. The filter was toggled on and off in timed intervals.

### Results
{% include gallery.html gallery=4 %}
*Figure 3. Example slider and button interfaces used in the experiment.*

| Button Range | T-Test Result| 
|:--------|:-------:|
| 1m   | t(29)= 1.0608, p=0.2975  | 
| 5m   | t(29)= 2.1426, p=0.0406  | 
| 10m  | t(29)= 4.5569, p < 0.01  | 

| Slider Range | T-Test Result | 
|:--------|:-------:|
| 1m   | t(29)= 0.7833, p=0.4397  | 
| 5m   | t(29)= 1.8518, p=0.0742  | 
| 10m  | t(29)= 3.1750, p=0.0035  | 

Significance was found for 10m buttons, 5m sliders, and 10m sliders, with overall improvements across all distances.

---

## Chapter 2 – Modular 3D Interface Design
Most VR UIs are not designed with accessibility in mind. This modular 3D interface system was developed with an **accessibility-first** design philosophy, allowing:

- **Free-floating or anchored placement** in 6DOF to accommodate user-specific viewing requirements.
- **Multimodal input support** (controller, hand tracking, gaze) so users can select preferred interaction modes.
- **Contextual display** of UI elements, reducing clutter and increasing task predictability.

{% include gallery.html gallery=7 %}
*Figure 4. Example of point cloud data displayed with contextual UI overlay.*

{% include gallery.html gallery=5 %}
*Figure 5. Panels with protective borders to prevent accidental selection.*

{% include gallery.html gallery=6 %}
*Figure 6. Kinematic UI panels interacting with virtual environments.*

> Pre-print: [here](https://arxiv.org/abs/2304.10541) | Published in Springer Notes: [here](https://link.springer.com/chapter/10.1007/978-3-031-35634-6_2)

---

## Chapter 3 – Holistic VR Optimisation
Holistic VR optimisation means designing for **human constraints**, not just system performance.

### Key constraints
- **Vergence–Accommodation Conflict**: Avoid placing interactive UI closer than ~0.5m to reduce eye strain.
- **Motion-to-Photon Latency**: Aim for <20ms to reduce simulator sickness; use asynchronous reprojection where possible.
- **Dynamic Distortion**: Apply edge correction to maintain stable target acquisition.
- **Biomechanics**: Respect ergonomic limits for reach, typically 130–150cm vertical from shoulder origin.

| Constraint | Cause | Recommended Guideline |
|------------|-------|-----------------------|
| VAC | Fixed focal distance | Place UI 0.5–2.5m from user |
| Latency | Slow render pipeline | Target <20ms motion-to-photon |
| Edge distortion | Lens & FOV | Apply dynamic correction |
| Overreach | Poor placement | Keep vertical reach <150cm |

---

## Chapter 4 – 3D Data Processing and Visualisation
With VR adoption in fields like GIS and photogrammetry, handling large 3D datasets is becoming essential.

### Study A – Point Cloud Navigation
Tested varying LOD thresholds to balance clarity and frame rate.  
**Finding:** Adaptive streaming improved usability without harming accuracy.

### Study B – Multi-Scale Visualisation
Compared fixed-scale vs adaptive-scale rendering.  
**Finding:** Adaptive scale allowed more efficient navigation in large datasets.

### Study C – Contextual Interface Placement
Compared anchored vs free-floating analytical tools.  
**Finding:** Anchored tools aided repetitive analysis, free-floating benefited exploration.

{% include gallery.html gallery=7 %}
*Figure 7. Contextual UI used in large dataset visualisation.*

---

# Final Thoughts
Three years of work led to one clear outcome: **precision in VR can be improved dramatically with one line of code** — the 1-Euro Filter. Beyond that, modular and ergonomically aware UI, perceptually optimised experiences, and scalable 3D visualisation form the foundation of holistic VR design.

Please cite this work or reach out if you’re building related solutions.

<div markdown="0"><a href="https://arxiv.org/abs/2405.07335" class="btn btn-outline-info">Pre-Print on arXiv</a></div>
<div markdown="0"><a href="https://github.com/corriedotdev/vr-tremor-reduction" class="btn btn-outline-info">Code & Dataset</a></div>

# References
* [Pre-Print](https://arxiv.org/abs/2304.10541)
* [Springer Paper](https://link.springer.com/chapter/10.1007/978-3-031-35634-6_2)
* [YouTube Video](https://youtu.be/3NhJOPAUMCs)
* [GitHub Repo](https://github.com/corriedotdev/vr-modular-3d-gui)
