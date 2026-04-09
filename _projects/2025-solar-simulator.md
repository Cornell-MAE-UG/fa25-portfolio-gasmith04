---
layout: project
title: Solar Simulator
description: Design and construction of indoor solar simulator for testing purposes
technologies: [Autodesk Fusion360]
image: /assets/images/solar_simulator.jpeg
---

#### Purpose and Background:
<br>
The purpose of the Solar Simulator Project is to create a dependable indoor testing environment that eliminates Ithaca’s weather-related limitations. Originally working in collaboration with the Energy and Environment Research Laboratory (EERL) under Professor K. Max Zhang, we designed the simulator to provide consistent irradiance conditions for our refurbishment testing and coating studies.
<br>
We started the project in Spring 2025, we completed the CAD modeling, structural analysis, material procurement and full assembly of the simulator frame using 80/20 aluminum. After evaluating several concepts, we selected a static rectangular design because it offered the best balance of stability, modularity, and ease of fabrication. We also designed custom 3D-printed brackets and installed the initial set of LED rods before beginning performance testing. By the end of that semester, we had a fully assembled simulator, validated the structural design, and nearly finalized our lighting approach.

In Fall 2025, our focus shifted towards refining the lighting system to produce stable, uniform irradiance while preparing the simulator for Environmental Health and Safety (EHS) approval. Early testing revealed periodic oscillations in IV curves caused by flicker from the LED rods, so we worked on implementing and evaluating multiple design modifications to increase irradiance and mitigate the flickering phenomenon.

#### Frame Design:
<br>
A robust, stable, and safe simulator structure was the teams utmost priority. Our mechanical engineering team created several CAD drafts before producing a final design, with each stage of the process peer-reviewed by grad and PhD mechanical engineers for efficiency and safety. 

<img src="{{ 'assets/images/solar_simulator_rendering.png' | relative_url }}" width="100%">

The design utilizes 8020 Aluminum T-slot framing. It's quite modular and gave us easy ability to attach the necessary lighting equipment. 


#### Lighting Options:
<br>
In order to achieve an even distribution of irradiance as close as possible to a sunny day (1000 W/m2), we conducted extensive research into lighting options (intensity and spectrum)  and dimming via PMW (pulse width modulation). Our results: several 15,000 lumen, 650 K color, and 8ft long LED rods!

However there were several issues...

##### Issue 1: Flickering and IV Curve Oscillations
A second challenge arose from the internal construction of the LED rods. Early panel tests within the simulator produced IV curves with unusual periodic oscillations not observed in outdoor tests (Fig. 2.7). Although this behavior is not visible to the human eye, LEDs require drivers to convert high-voltage AC power to low-voltage DC power and to regulate current. These drivers protect the LEDs from supply fluctuations, control brightness, and extend the LED’s lifetime. If the drivers are of poor quality, they can deliver slightly unstable, oscillatory power. Slow-motion video recordings of the simulator in operation confirmed the presence of LED flicker.
An option was to upgrade or replace the internal drivers but it was deemed impractical due to high cost and installation complexity. Because eliminating the flicker at the source was not feasible without replacing the driver circuitry, an alternative data-processing approach was adopted. By extracting and averaging the data at the oscillation peaks, a much smoother IV curve was obtained (Fig. 2.8), and it closely approximated the IV behavior measured under stable outdoor sunlight at 1000 W/m² (Fig. 2.9).

One side effect of the LEDs is that, unless you have a costly driver that provides perfectly steady DC current, they will flicker. On our first trial, the IV curve trace presented noticeable oscillations due to this flickering (Fig. 1). Without changing the internal drivers, which is both expensive and very difficult, there isn’t a way to get rid of the flickering. So instead, we extracted the data from each oscillation peak to produce a cleaner IV curve (Fig. 2), which is a much closer representation of the IV curve trace taken in sunny, outdoor conditions (Fig. 3).

<img src="{{ 'assets/images/simulator_trace_fig1.png' | relative_url }}" width="49%">
<img src="{{ 'assets/images/simulator_trace_fig2.png' | relative_url }}" width="49%">

<p style="text-align: center; font-size: 15px;">
    Figure 2 and 3, IV curve before and after averaging peaks, respectively.
</p>  



##### Issue 2: Low Irradiance
With the simulator fully set up, we realized the irradiance measurements we were achieving were far from outdoor, even on a cloudy day. Thus, we needed to figure out a way to raise panel’s irradiance without sacrificing spatial uniformity. The key design parameters were LED-to-panel height and rod spacing/overlap. Too close meant high irradiance but striping; too far resulted in smooth but low irradiance. The goal was to find the closest mounting height that still met the necessary uniformity spec of about 5.5 inches. 

<img src="{{ 'assets/images/led_spacing.png' | relative_url }}" width="100%">

While the panel height optimization helped, we still wanted to improve the irradiance, so we added Mylar film around the sides to reflect the edge light back onto the panel. Additionally, we integrated halogen lamps to supplement the LEDs. This addition initially raised numerous new light distribution concerns, initial testing with the Mylar, halogens, and LEDs had shown promise of reaching irradiance measurements  close to, if not exceeding, 400 W/m2.

<img src="{{ '3-halogens.png' | relative_url }}" alt="3 halogen rendering" class="inline-image inline-image-r" width="50%" />

Determing the optimal number of halogen lamps and their orientation on the simulator was no easy task. This took numerous lab sessions, testing all sorts of configurations until we landed on three halogens, evenly spaced across the PV panel length, attached to the sides of the simulator.

In the Spring 2026 semester, we moved into a new lab space within a campus greenhouse (for reasons concering some of our other current projects). The move required us to make the simulator more modular, with full tear down and rebuild only taking 20 minutes. Rendering of initial greenhouse setup shown below.  

<img src="{{ 'assets/images/greenhouse_rendering.png' | relative_url }}" width="100%">

As of late March, we have officially finished the simulator project up and have moved onto testing refurbished panels. 

<img src="{{ 'assets/images/current_simulator.png' | relative_url }}" width="100%">