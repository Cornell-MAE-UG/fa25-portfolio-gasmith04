---
layout: project
title: Open Design Project
description: Designed and prototyped a split water bottle, focused on easy and convenient clean-ability
technologies: MATLAB
image: /assets/images/Open-up_sketch.png
---
### Purpose and Background

The main objective of this project was to discover an issue with a current product and engineer a new product that solves it. We targeted the reusable water bottle market, as while they prevent waste and are more economically viable compared to plastic water bottles, they harbor high levels of bacteria, sometimes 40,000 times more than a toilet seat, resulting in harsh odors and health risks. Market-leading competitors, like Nalgene and Hydroflask, feature either narrow necks or small diameters that hinder thorough cleaning without seperate cleaning tools. Customer interviews revealed a significant segment of reusable bottle users struggle with the motivation to clean their water bottles daily (like research suggests to limit bacterial growth) because the process is often ineffective, labor intensive, or requires seperate tools. We engineered a reusable water bottle, without any complicated internal components or sharp corners, that eliminates bacterial and mold growth by providing complete internal access for convenient, daily cleaning. By utilizing a split-body architecture with a high-compression sealing mecahnism, our design aims to offer the same durability of premium insulated bottles while solving the "cleanability gap" that leads many users to prematurely discard their containers due to odor buildup. 

### Design Process and Prototype Evolution 
The project followed a rigorous iterative design process, starting from broad lateral brainstorming to high-fidelity functional prototyping.
<br> 

#### Initial Brainstorming

##### Ideation: 
We generated 30 distinct concepts using "sticky note" brainstorming, exploring solutions ranging from UV self-sanitization to internal scrubbing fans.
<br>
<img src="{{ 'assets/images/ideation.png' | relative_url }}" width="100%">

##### Selection: 
We removed all infeasible ideas (e.g., electronics-heavy or overly complex folding mechanisms), then pivoted toward a vertical thinking approach focused on physical access. 
<br>
<br>

#### Technical Iterations

##### Scrappy Prototyping: 
We used cardboard and popsicle sticks to model and test the physical logic of our vertical vs. horizontal splits.
<br>
<img src="{{ 'assets/images/scrappy1.png' | relative_url }}" width="33%">
<img src="{{ 'assets/images/scrappy2.png' | relative_url }}" width="33%">
<img src="{{ 'assets/images/scrappy3.png' | relative_url }}" width="33%">

<br>

##### Modeling and 3D Printed Prototype: 

We printed a functional 1:1 scale model in order to test the feasibility of our "two-big-halves" concept.

<br>
<img src="{{ 'assets/images/rending_redblue.png' | relative_url }}" width="47%">
<img src="{{ 'assets/images/exploded_view.png' | relative_url }}" width="51.2%">
<br>

We then added an o-ring to the split and clamps using JB-Weld to verify our compression calculations and initial "seal-ability". We found that the JB-Weld epoxy would continously fail under colder temperatures and the necessary clamping force required for a water tight seal.
<br>

<img src="{{ 'assets/images/leak1.png' | relative_url }}" width="32.5%">
<img src="{{ 'assets/images/leak2.png' | relative_url }}" width="30.8%">
<img src="{{ 'assets/images/broken_clamp.png' | relative_url }}" width="34.6%">

<br>

##### Refined Prototype: 
We reprinted the prototype with adjusted dimensions for an x-profile o-ring to  decrease compression force needed for a water-tight seal and integrated heat-set inserts to replace the epoxy-based clamp attachments.
<br>
<img src="{{ 'assets/images/heatset_inserts.png' | relative_url }}" width="49%">
<img src="{{ 'assets/images/X-profile_oring.png' | relative_url }}" width="49%">
<br>

### Engineering Specifications and Performance

Our final design combined a horizontal split at the midpoint with a secure draw-latch system.
<br>
Core Metrics:

| Parameter &emsp; | Target Specification &emsp; | Achievement &emsp; |
|-------------------|-----------------------|---------------------|
| Weight | 350g Maximum | Successfully met |
| Dimensions | 8.25 cm x 25 cm | Optimized for cup holders |
| Sealing | Leak-proof at 1 atm | Achieved with X-profile O-rings |
| Capacity | 750 ml | Comparable to industry standard |

<br>

### Future Plans and Design for Manufacturing, Quality, and Sustainability:
For our next and final iteration of the design, we propose replacing the 3D-printed plastic components with stainless steel parts. 3D printed plastic gave an affordable and easy option for early protytping but the overall quality and aging of the material are limited. Switching to stainless steel would not only improve the bottle's durability but also improve the "feel". Higher quality products are metal, not plastic. The top, bottom, and cap will all be produced through deep drawing in order to gradually form each piece into a seamless cylindrical shape with high strength and corrosion resistance. The top and bottom halves will be formed by sequentional deep drawing steps, followed by trimming and necking operations to achieve the final dimensions. the finalized design will utilize a dual-layer stainless steel construction with an internal air gap in order to provide superior insulation. For the threads in the top half and cap, we will roll the form into the steel which is cheaper, faster, and will produce less waste than machinging. The slot for the latch in the bottom half willl be pressed into the bottle with a die. The latches will be spot-welded directly onto the metal body which is faster to produce in a factory. Once tooling is developed in a factory, we can easily scale up the processes to mass production for sale. Additionally, CO2 emission calculators showed our plastic design would produce 47% more carbon emissions than the stainless steel design. Making this switch would significantly reduce the carbon footprint of the OpenUp water bottle.






