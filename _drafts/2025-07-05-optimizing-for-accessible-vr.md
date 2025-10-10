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
   -
     - { url: '/img/filter/filter.PNG', alt: 'vr filter'}
 2:
   -
     - { url: '/img/filter/vr.png', alt: 'vr filter'}
     - { url: '/img/filter/Capture.PNG', alt: 'vr filter'}     
 3:
   -
     - { url: '/img/filter/noise.gif', alt: 'vr filter'}
     - { url: '/img/filter/ev.gif', alt: 'vr filter'}
 4:
   -
     - { url: '/img/filter/slider.png', alt: 'vr filter'}
     - { url: '/img/filter/button.png', alt: 'vr filter'} # section 1
 5:
   -
     - { url: '/img/modular/ui.gif', alt: '5'}
     - { url: '/img/modular/panel.PNG', alt: '6'}
 6:
   -
     - { url: '/img/modular/yove.gif', alt: '7'}
 7:
   -
     - { url: '/img/modular/new.PNG', alt: '8'}


---

# TL;DR – Developer Focused Takeaways
✅ Tremors can be reduced in consumer VR using a 1-Euro filter.
3D Interfaces can be modular
3D Interfaces can be multi-modal
There is a comfort range based on human anatomy to place VR UI


# Introduction
todo


## Chapter 1 - Accessible VR Interaction Model
This research investigates the use of a 1-Euro low-pass filter to reduce involuntary tremors during fine motor control tasks in virtual reality. While natural tremors are present in all humans, they become exaggerated in VR due to controller sensitivity and tracking noise. A lightweight, velocity-based low-pass filter can significantly reduce tremor impact without interfering with intentional fast movements, making interactions smoother and more precise.

![JWT Screen]({{ site.url }}/img/filter/filter.PNG)
{: .pull-center}
> I want to see this filter integrated into every VR HMD Accessibility Menu with a Toggle. It's just a single script.

Paper pending Publication at my preferred journal which is Springer Nature Virtual Reality
**Pre-Print** Paper available [here](https://arxiv.org/abs/2405.07335)          

**Git Study Repo** Paper available [here](https://github.com/corriedotdev/vr-tremor-reduction)      

All of us have benign essential tremors, you may notice these shakes in VR when you are selecting an item in a menu using a laser pointer. Some tremors are exaggerated due to the tracking of controllers or hand tracking techniques when using vision. These can be system signal noise or, essential tremors. Between the range of 4-12Hz we have psychotic tremors (sometimes refferred to as essential tremors). Some tremors have a high frequency but a low amplitude resulting in them barely being noticable. Unlike parkinsons tremors where the high amplitude often makes them much more obvious. 

In VR selecting UI components, often at a distance, we neglect to take these tremors into consideration. 

{% include gallery.html  gallery=3 %}


With the use of a low pass filter like the 1-Euro Filter, we can almost remove these tremors found in every healthy individual to increase engagement and prevent frustration when interacting with 2D UI in VR. We can also use this filter during any 3D interaction in VR, as the filter is lightweight and has a delta cut off where the filter is disabled during fast velocity hand movement and only enabled for fine control. My hypothesis is we can reduce symptomatic parkinson tremors with this filter.


## Study
I completed a 30 participant user study, the demographic included the general population with and without exposure to VR before. No participants were aware of neuromuscular disorders and were considered healthy. 

The study required users to interact with 2D buttons and sliders at various ranges. The filter was enabled and disabled at set intervals and their times recorded for integer selection. 

I found that there was significant improvement for buttons at 10m ranges and sliders at 5m and 10m ranged tasks. However, there was average improvement across all interactions with the filter enabled. 

## Results
{% include gallery.html  gallery=4 %}

**Remember** Degrees of Freedom in the T-Test for Means is N-1 
{: .notice}


| Button Range | T-Test Result| 
|:--------|:-------:|
| 1m   | t(29)= 1.0608, p=0.2975  | 
| 5m   | t(29)= 2.1426, p=0.0406  | 
| 10m  | t(29)= 4.5569, p < 0.01  | 
|----


| Slider Range |T-Test Result| 
|:--------|:-------:|
| 1m   | t(29)= 0.7833, p=0.4397  | 
| 5m   | t(29)= 1.8518, p=0.0742  | 
| 10m  | t(29)= 3.1750, p=0.0035  | 
|----

{: rules="groups"}

In summary, the t-test proves significance for 10m button, 5m slider and 10m slider. However we see an overall average improvement time across the board. The charts above show this clearer, grey is filter off so standard VR interaction and white is interaction with the filter enabled.

## Improve Your Item Placement in VR
I will make another post here soon for this as there is a lot to break down but as I am disclosing this research in pre-print format for now and awaiting Journal publication, this graphic can be used to help with item placement in VR. All demos include this so you can experience it first hand.

**Minimum Comfort Angle** = (HMD FoV/2)+30 
{: .notice}

**Maximum Comfort Angle** = (HMD FoV/2)+55 
{: .notice}

### Fitts Law
As distance increases, movment time for user interaction also scales. Something to consider and discussed throughout the paper.
**Movement Time** = a+b (log) ^2  (distance/(size+1))
{: .notice}

{% include gallery.html  gallery=2 %}
<div markdown="0"><a href="https://corrie.dev/img/filter/vr.png" class="btn btn-success" download >Download Graphic</a></div>


## Conclusion
The use of a laser pointer for interacting with 2D UI elements in VR space could be considered as an interim solution for most VR interactions as many UI elements are similar to that of traditional UI and don’t take advantage of 3D space. By combining the accessibility approaches discussed, an outline of key considerations has been discovered to support developing an ability-first design approach.

Please cite if you use this, its been 3 years of work in short. I really think this can help improve many peoples quality of life. 


### Experience the filter, Download 
You can download the study Git Repository [here](https://github.com/corriedotdev/vr-tremor-reduction) and experience it yourself via Desktop VR. You can also see how to implement the filter, its a single script!

<div markdown="0"><a href="https://github.com/corriedotdev/vr-tremor-reduction/releases/tag/vr" class="btn btn-info" download >GitHub Study Build</a></div>

If you want to experience it on Quest standalone, please download the experience mentioned in my Modular 3D interface post. 
<div markdown="0"><a href="https://drive.google.com/file/d/1a3d-kjpbjUMr74AmUbnhwgbjU7NUtXv4/view?usp=sharing" class="btn btn-success" download >Download Quest</a></div>



# Chapter 2 - Modular 3D Interface Design
The paper has been published in Springer notes which can be found [here](https://link.springer.com/chapter/10.1007/978-3-031-35634-6_2) the pre-print is available [here](https://arxiv.org/abs/2304.10541). This page will cover the basics of the system to allow you to integrate into your own projects. I would recommend watching the youtube video, which is a more "entertaining" version of the presentation I did at HCI International 2023. 

<p style="text-align:center;">
<iframe width="560" height="315" src="https://www.youtube.com/embed/3NhJOPAUMCs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</p>

## Key Features
Existing interfaces are not, if ever, designed with accessibility in mind. It's a difficult thing for developers to implement as its not clear on exactly what makes a design accessible. This interface has been developed with an accessible first design philosophy, aiming to remove this responsibility from the developer allowing for a multimodal input approach allowing users to select their preferred input mechanism whilst also providing support for relocating the positions of UI elements. 

- Free-floating allows for adjustment in 6-DOF for users with specific viewing angle requirements and allows for anchored placement in 3D space.

- Contextual, allowing elements to only be displayed when relevant to the location in the environment resulting in;

- Predictable task-focused interactions, using skeuomorphs and colors around 3D interface trims in designated context zones

## Demo Download 
The [Github repo](https://github.com/corriedotdev/vr-modular-3d-gui) you can download various demonstrations of the application. You can integrate this into your project by creating a panel with a border that allows for grabbable interactions. The 

{% include gallery.html  gallery=7 %}

> Point cloud, video, photogrammetry and GIS dataset visualisation with custom placement for UI 

{% include gallery.html  gallery=5 %}

> Panels with borders which act as buffer zones to prevent interacting with UI componenets attached
{% include gallery.html  gallery=6 %}

> The panels are kinematic and work with the physics engine allowing for static placement but also interact with the envionment

## Chapter 3 - Holistic VR Optimisation
This chapter focuses on optimising VR through a lens that includes the constraints of human perception, ergonomics, and real-world motor control. It moves beyond performance metrics like frame rate and instead considers the physiological thresholds and perceptual limitations that define the quality of a VR experience.

One of the most critical aspects discussed is the issue of fixed focal distances in modern HMDs. Most consumer VR headsets present imagery at a fixed optical focal distance of around 1.5 metres. This creates a mismatch between convergence (how the eyes turn inwards to look at something) and accommodation (how the lens in the eye focuses). This mismatch is referred to as the vergence-accommodation conflict (VAC), and it’s a key cause of visual discomfort and fatigue. Despite visual elements being rendered at varying simulated depths, the eyes are always focused physically at the same distance, which breaks the natural coordination between focus and depth.

In practice, this means VR UI and content should avoid placing critical or interactive elements too close to the user. The comfortable range for most users begins at approximately 0.5m and extends to around 2.5m. Anything placed within 30–40cm, while sometimes necessary, can lead to visual strain — particularly during sustained interactions or when precision is required.

Other perceptual factors explored in this chapter include motion-to-photon latency, dynamic distortion, and force-feedback approximations. Motion latency, particularly in fast interactions like climbing or reaching, can impact immersion and increase the risk of simulator sickness. Similarly, visual distortion at the edge of the field of view becomes more pronounced if not dynamically corrected, leading to inconsistent object recognition or unstable target acquisition. These effects accumulate in ways that degrade overall usability.

The goal in this part of the research was to identify where perceptual mismatches occur — not just through system latency or rendering artefacts, but in the way VR interacts with our sensory and motor systems — and then explore optimisation strategies that accommodate the user, not just the system.

## Study
The empirical part of this chapter involved evaluating a variety of VR interaction models and rendering strategies. A series of usability-focused studies were conducted, with participants engaging in tasks that included climbing, selection, and observation under different rendering and interaction configurations.

Specific variables studied included the impact of asynchronous reprojection, eye-tracked foveated rendering, frameless rendering models, and distortion correction on usability and comfort. Additionally, physical interaction models were tested using force-based mechanics such as PID-controlled climbing, and the effect of placement distance for UI and objects on user preference and performance was recorded.

Participants were asked to complete tasks that involved interacting with UI elements positioned at various depths and angles, or completing locomotion-based movements under different simulation conditions. Feedback was captured through structured interviews and qualitative usability scoring.

## Results
Findings from this chapter reaffirm the role of human-centered constraints in determining the effectiveness of VR design. Participants reported higher comfort and improved task completion when UI elements were positioned at or beyond 0.5m. Elements closer than this were consistently associated with eye strain, particularly when tasks required extended focus or fine motor control.

Dynamic distortion compensation was positively received, particularly at the edges of the display. Without it, there were frequent issues with clarity, alignment, and motion consistency. These effects increased at wider fields of view or when tasks moved the user’s attention away from the centre of the display.

Motion-to-photon latency was noticeable, particularly in scenarios involving dynamic movement. Techniques such as asynchronous reprojection reduced the perceptual delay but did not eliminate the problem entirely. Users remained aware of inconsistencies when input movement and visual feedback were out of sync, especially in fine motor tasks.

Climbing mechanics that implemented PID-based force simulation provided smoother, more predictable movement and better user feedback compared to standard velocity-based movement. The benefit was most evident in vertical reach interactions, where natural biomechanical limits (approximately 130–150cm vertical reach from shoulder origin) were respected.

In summary, the optimisation of VR must account for the perceptual and physical limitations of the human body. Visual clarity, response timing, and movement mapping all benefit from considering how humans actually see, reach, and interact. These insights provide a foundation for system-level improvements that better support user comfort, precision, and long-term engagement in VR environments.


## Chapter 4 - 3D Data Processing and Visualisation
insert text about intro to chapter


## Study
insert section about key human highlights of the 3 studies completed

### Results


## Chapter 5 - Future Work
insert text about the future work ideas but focus on the portals

## Study 1
insert about pixel arcade, 3d interface design, available on quest and steam and also using portals as discussed

## Study 2

## Study 3


---


# Final Thoughts

Three years of work led to one clear outcome: **precision in VR can be improved dramatically with one line of code.** The 1-Euro Filter is not just academic — it’s practical, fast, and should be integrated into every VR HMD system’s accessibility toolkit.

Please cite this work or reach out if you're building related solutions.

<div markdown="0"><a href="https://arxiv.org/abs/2405.07335" class="btn btn-outline-info">Pre-Print on arXiv</a></div>
<div markdown="0"><a href="https://github.com/corriedotdev/vr-tremor-reduction" class="btn btn-outline-info">Code & Dataset</a></div>
<a href="#" id="emailclick" onclick="replace_email()">My Email</a>

## Further Reading
Check out the following links for inspiration and further reading about this topic
* [Pre-Print](https://arxiv.org/abs/2304.10541)
* [Springer Paper](https://link.springer.com/chapter/10.1007/978-3-031-35634-6_2)
* [Youtube Video](https://youtu.be/3NhJOPAUMCs)
* [GitHub Repo](https://github.com/corriedotdev/vr-modular-3d-gui)

# References
insert references



<!-- SCRIPTS -->
<script>
var email;

function add_mailto() {
  const elem = document.getElementById("emailclick");
  elem.href = `mailto:${email}`;
}

function replace_email() {
  const domain = "cjgstudio.com";
  const name = [16, 28, 1, 1, 26, 22];
  const xor_with = 115;
  let constructed = "";
  name.forEach(function(i) {
    constructed += String.fromCharCode(i ^ xor_with);
  })
  email = `${constructed}@${domain}`;
  const elem = document.getElementById("emailclick");
  elem.text = email;

  window.setTimeout(add_mailto, 100);
}
</script>
