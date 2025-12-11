---
layout: project
title: Torque Wrench Design Project
description: Mechanics of Engineering Materials final project, analyzing a torque wrench
technologies: [Autodesk Fusion 360, Ansys]
image: /assets/images/Torque_wrench_isometric.png
---

---


This final project for my Mechanics of Engineering Materials class involved designing, modeling, and anlyzing a torque wrench. Our design was based off several factor of safety requirements.

---
<br>
### CAD Model
<br>
All dimensions in inches

<img src="{{ 'assets/images/twrench_dimensions_1.png' | relative_url }}" width="100%">
<img src="{{ 'assets/images/twrench_dimensions_2.png' | relative_url }}" width="65%">
<img src="{{ 'assets/images/twrench_dimensions_3.png' | relative_url }}" width="30%">

---
<br>
### Material Selection
<br>
Typically used in the aerospace, defense, and high performance automotive industries, 300M is a highly resilient material with exceptionally high yield and fatigue strengths. While likely considered overkill for a tool, a material choice of 300M for our wrench allowed us to make the thickness dimensions relatively slim, allowing the torque wrench to be used on bolts in tight spaces. The dimensions do not compromise performance with our geometry producing a normal stress of about 64ksi, which is only about 28% of the yield limit of 230 ksi.
<br>
The material properties used in FEM and all hand calculations were:


| Property | Symbol | Value |
|----------|--------|-------|
| Young’s Modulus | E | 29 × 10<sup>6</sup> psi |
| Poisson’s Ratio | ν | 0.32 |
| Yield Strength | σ<sub>o</sub> | 230 × 10<sup>3</sup> psi |
| Fracture Toughness | K<sub>IC</sub> | 45 × 10<sup>3</sup> psi·√in |
| Fatigue Strength @ 10<sup>6</sup> cycles &emsp;| σ<sub>fatigue</sub> &emsp; &emsp; &emsp;| 125 × 10<sup>3</sup> psi |

<br>
Our material and geometry had to satisfy:
<br>

&ndash; Strength safety factor ≥ 4  
&ndash; Fracture toughness safety factor ≥ 2  
&ndash; Fatigue safety factor ≥ 1.5  
&ndash; 1.0 mV/V output at the rated torque of 600 in-lbf.

Our geometry with 300M steel meets all of these requirements when evaluated with both hand calculations and FEM analysis.

---
### FEM Boundary Conditions and Loading
<br>

<img src="{{ 'assets/images/twrench_boundary_conditions.png' | relative_url }}" width="100%">

---

### Strain Contour in the Gauge Direction
<br>

<img src="{{ 'assets/images/twrench_strain_contour_1.png' | relative_url }}" width="100%">
<br>

<img src="{{ 'assets/images/twrench_strain_contour_2.png' | relative_url }}" width="100%">

---

### Maximum Principle Stress Contour
<br>

<img src="{{ 'assets/images/twrench_stress_contour.png' | relative_url }}" width="100%">
<br>

<img src="{{ 'assets/images/twrench_stress_contour_2.png' | relative_url }}" width="100%">

---

## Summary of FEM Results

<br>

<img src="{{ 'assets/images/twrench_max_normal_stress.png' | relative_url }}" width="100%">
Max Normal Stress (anywhere): 63935 psi
<br>

<img src="{{ 'assets/images/twrench_deflection.png' | relative_url }}" width="100%">
Deflection at Load Point: 0.2023 in
<br>

<img src="{{ 'assets/images/twrench_strain_probe.png' | relative_url }}" width="100%">
Strain at Strain Gauge Location: 1161 µε
<br>

## Torque Wrench Sensitivity

1.16 mV/V at 600 in-lbf using half bridge

## Strain Gauge Selected

VISHAY- C2A series strain gages- 062LW

C2A-06-062LW-350

<img src="{{ 'assets/images/twrench_strain_gauge.png' | relative_url }}" width="100%">

At just 0.08 in wide, this strain gauge has more than enough room to fit comfortably on the dimensions of our CAD. Additionally, it has a fatigue life of 10<sup>5</sup> cycles at ±1700 microstrain and 10<sup>6</sup> cycles at ±1500 microstrain. Our FEM calculated a strain of 1161 microstrain at the strain gauge, which would insinuate a fatigue life larger than the provided range, making it more than sufficient.