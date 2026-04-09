---
layout: project
title: JunAir Oil-less Air Compressor Dissection
description: 
technologies: MATLAB
image: /assets/images/fluids_airc_cov_photo.png
---

### Purpose and Background
For this fluid mechanics project, we were tasked with taking apart a machine, then studying it in order to explain how it works using fluid mechanical concepts and terminology. My group dissected a Jun-Air Oil-less Rocking Piston Air Compressor. My role was examining the internal components, mapping out the fluid path, taking measurements to do analysis on both the compression and pressure ratio of the pistons. 
<br>
The compressor is a dual-action, positive-displacement reciprocating air pump. As a positive-displacement device, it moves air by trapping a fixed volume and mechanically reducing its space, making the delivered flow rate primarily a function of RPM. Its reciprocating motion varies the chamber volume and uses check valves to direct air through the system. Dual-action operation compresses air on both piston strokes, doubling the effective flow rate and providing smoother, more continuous delivery with pistons 180° out of phase. Bursting is a common failure mode for these types of pumps, and in order to prevent this, the designers ensured there was a relief valve to vent the air when internal pressure exceeds a safe threshold.

#### What we analyzed

The whole function relies on the geometry and structure of the pistons, cylinders, reed valves, and the head manifold. 
<br>
Below is a drawing of one piston assembly. We defined a time varying control volume bounded by the head, walls, and piston top. In the intake stroke, the piston head moves down, increasing the size of the control volume and thus pressure must drop inside the cylinder. Cylinder pressure becomes less than the ambient pressure, a negative pressure gradient form which pulls air through the intake valve. In the discharge stroke, as the piston head moves back up and reduces the size of control volume, the pressure in the cylinder must increase. So the piston moving back up creates slightly higher pressure inside the cylinder than inside the reservoir. The lower pressure in the reservoir pulls air up through the outlet valve and out of the cylinder, driven by this positive pressure gradient. What allows the air compressor to function is these moving control volume boundaries that creates the pressure gradients to drive flow from the intake manifold to the reservoir. 

<img src="{{ 'assets/images/fluids_suction.png' | relative_url }}" width="100%">

But where does the air that enters the cylinder come from, and where does the air that exits the cylinder go to? Within the head manifold, there are two compartents on either side. I've named these the intake chamber and discharge chamber. The two intake chambers are seperate, whereas the two discharge chambers are connected by a small metal tube, which also connects the entire head manifold together. In each suction stroke, the pressure gradient pulls air down through the respective side's intake chamber and through the intake reed valve, shown below with the green arrows. In the discharge stroke, the pressure gradient pulls air out through the outtake reed valve and into the discharge chamber where the pressure between the two discharge chambers and the reservoir are roughly equal (at high RPMs, losses will exist here due to the small diameter of the connecting pipe). This is shown by the purple and pink arrows below. 

<img src="{{ 'assets/images/fluids_headmani.png' | relative_url }}" width="100%">


### Core fluid-mechanics concepts
We explained the device using:
- Positive-displacement pump flow: $$Q_p = D_p(\theta)\,\omega_p$$
- Polytropic relationL $$P_1 = C,(\rho)\_1<sup>n</sup>$$
- Power required from pressure on each piston: $$P=\frac{Q(\delta)\p}{(\eta)\}
- Boundary layer principle, vortices and recirculation pockets


### Assumptions Used:
 - Working fluid (air) can be modeled as ideal gas
 - Entire process through the compressor is quasi-equilibrium
 - Polytropic exponent is constant throughout the compression process
 - Pressure inside the cylinder is spatially uniform
 - Negligible leakage
 - Incompressible flow


### My contributions
- Fully disassembled the machine with two other members
- Did all analysis on the pistons, from mapping out how they work to the compression and pressure ratios 
- Wrote assumptions
- Helped with excel modeling and calculations


### Final video
**Link to our fluid mechanical dissection video**  
[Watch on YouTube](https://youtu.be/kFJW_DP0QBg)
