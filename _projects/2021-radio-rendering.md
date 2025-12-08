---
layout: project
title: Solar Simulator
description: Design and construction of indoor solar simulator for testing purposes
technologies: [Autodesk Fusion]
image: /assets/images/solar_simulator.jpeg
---

Purpose:
By removing the variability that comes with outdoor weather-related inconsistencies, an indoor solar simulator can evaluate photovoltaic (PV) performance under consistent intensity/irradiance levels and serve as a reference point for the further evaluation of PVs in comparative studies (ex: resin).

Frame Design:
A robust, stable, and safe simulator structure was the teams utmost priority. Our MechE team created several CAD drafts before producing a final design, with each stage of the process peer-reviewed by grad and PhD MechEs for efficiency and safety.

Insert CAD Rendering here

Lighting Options:
In order to achieve an even distribution of irradiance as close as possible to a sunny day (1000 W/m2), we conducted extensive research into lighting options (intensity and spectrum)  and dimming via PMW (pulse width modulation). Our results: several 15,000 lumen, 650 K color, and 8ft long LED rods!

However there were several issues...

Issue 1: Flickering and IV Curve Oscillations
One side effect of the LEDs is that, unless you have a costly driver that provides perfectly steady DC current, they will flicker. On our first trial, the IV curve trace presented noticeable oscillations due to this flickering (Fig. 1). Without changing the internal drivers, which is both expensive and very difficult, there isn’t a way to get rid of the flickering. So instead, we extracted the data from each oscillation peak to produce a cleaner IV curve (Fig. 2), which is a much closer representation of the IV curve trace taken in sunny, outdoor conditions (Fig. 3).

Expand... show irradiance plots... show excel calculations

Issue 2: Low Irradiance
With the simulator fully set up, we realized the irradiance measurements we were achieving were far from outdoor, even on a cloudy day. Thus, we needed to figure out a way to raise panel’s irradiance without sacrificing spatial uniformity. The key design parameters were LED-to-panel height and rod spacing/overlap. Too close meant high irradiance but striping; too far resulted in smooth but low irradiance. The goal was to find the closest mounting height that still met the necessary uniformity spec of about 5.5 inches. 

Show distance optimization calculations

While the panel height optimization helped, we still wanted to improve the irradiance, so we added Mylar film around the sides to reflect the edge light back onto the panel. Additionally, we are working on integrating halogen lamps to supplement the LEDs. Although this addition raises new light distribution concerns, initial testing with both the Mylar and LEDs has shown promise of reaching irradiance measurements  close to, if not exceeding, 400 W/m2.

Insert more photos

Insert future work with simulator (what still has yet to be done in this project)

fluids
