---
layout: project
title: Ryobi Drill Dissection
description: 
technologies: MATLAB
image: /assets/images/sdissection-cover.png
---


---


 For this project, me and a group disassembled a Ryobi corded 5.5 Amp drill to directly connect course concepts to a tangible device that a lot of us use in our work on project teams. We chose the drill specifically as it connects electrical and mechanical subsystems together, like the DC motor, gear train, clutch, etc. Within the drill system, we developed an ODE model for the motor and gear train. We then used this to derive the governing equation, then obtained the transfer functions relating trigger input to motor speed. Additionally, we also analyzed the transient response through a step change in input, and investigated the open loop response via a simple experimental set-up under no load.

My role was taking the laplace transforms of the ODEs to find both the open loop and closed loop transfer functions and create an open loop model for the system in matlab, using the time constant and gain found in high speed video analysis of the drill. I also looked into how implementing a feedback control law (P/PI/PID) might benefit the system, especially in terms of disturbance rejection.


## Dissection

<img src="{{ 'assets/images/sdissection-main.png' | relative_url }}" alt="Drill dissection main view" class="inline-image inline-image-r" width="50%" />
<p>We began this exploration by dissecting the drill, with the goal of closely examining the physical components to map them to the parameters that may appear in the ODE based on the DC motor models we have looked at in class and in Lab 1 [1]. During this process, we removed half of the drill casing and pressed the trigger switch to observe how each component moved. To help us name the components and learn more about them, we followed a labeled image that looked similar to our drill [2].  Once we triggered the drill, it was easy to identify the components that rotated, including the windings, rotor, gear train, and chuck. We also observed what the wires from the trigger switch connected to in order to understand how the electrical and mechanical components interacted with each other. After this first inspection, we took apart the individual parts to examine them more closely. We observed the brushes, windings, planetary gear systems, gear grease, and chuck. As we advanced through each component, we filled out the table below to map each component to the ODE variables we learned about in the semester, identify the type, and in what ODE it might show up. This set us up to later model the system as two coupled ODEs. </p>


| Variable &emsp; | Name | Variable Type | Relation to Physical Component | ODE and Sign |
|---------------|--------|-------|-------|---------|--------|
| v(t) | Applied voltage | Input | Trigger switch (controlled by user), battery, motor | Electrical (+) |
| L | Inductance | Physical property | Motor casing and windings | Electrical (-) |
| R | Resistance | Physical property | Windings, motor brushes | Electrical (-) |
| i(t) | Current | Internal | Trigger switch, windings, magnets | Coupled |
| J | Rotational inertia | Physical property | Motor rotor, windings, gear train, chuck (and drill bit) | Mechanical (-) |
| b | Damping coefficient | Physical property | Motor brushes, gear train grease | Mechanical (-) |
| T<sub>m</sub> | Torque from motor | Internal | Motor windings, magnets, motor rotor | Mechanical (+) |
| &omega;(t) | Angular speed | Ouput | Motor rotor, gear train, chuck (and drill bit) | Coupled |
| T<sub>d</sub>  | Torque from load | Disturbance input | Drill bit contacting material, user-applied force | Mechanical (-) |


## Modeling

### ODEs

After dissecting the drill, we proceeded to model it as a coupled electromechanical system where the electrical subsystem is composed of the trigger circuit and motor, while the mechanical subsystem includes the rotor, gear train, and chuck. To capture the behavior of the drill, we came up with two differential equations, one for each subsystem. The electrical ODE follows Kirchoff’s Voltage Law while the mechanical ODE follows Newton’s second law in rotation. These ODEs are coupled, showing how the input voltage v generates the motor torque Tm, and the torque yields the rotational speed. 

v=Lddti+Ri+Ke , where: 
&ndash; v is the input voltage
&ndash; Lddti is the inductive effect of the motor windings (L is the inductance, ddti is the current derivative)
&ndash; Ri is the voltage drop across the resistance (R is the resistance, i is the current)
&ndash; Ke is the back EMF generated when the motor spins and produces a voltage that opposes v (Ke is the back EMF constant) 
Tm=Jddt+b+TL , where:
&ndash;  Tm=Kmi, the torque from the motor (Km is the motor torque constant)
&ndash; Jddt is the angular acceleration of the rotor, gears, and chuck (J is the total rotational inertia from these components, ddt is the rotational speed derivative)
&ndash; b is the damping torque that results from friction (b represents the losses from friction,  is the rotational speed)
&ndash; TL is the torque from the load when drilling into a material ( TL=0 in free space)

Rearranging in terms of the highest derivatives, the ODEs become: 

Lddti= -Ri-Ke+v
Jddt= -b+Kmi-TL 

The ODEs are coupled by the terms Kmi(t) and Ke(t) , accounting for how the current affects the motor torque via Kmi(t) and the speed affects the electrical subsystem through Ke(t). 

In order to track how the internal states of the drill, namely i(t) and (t) , change with time, we derived a state space model of the system. This allowed us to understand how the voltage creates current, the current creates the motor torque, and the torque accelerates the drill.
Define variables
States:  x1=(t) and x2=i(t)       ⇒ n=2
Inputs: u(t)=v(t)                            ⇒ m=1
Outputs: d(t)=TL(t)                        ⇒ p=1

Isolate highest derivatives
ddt= -bJ-1JTL+KmJi 
ddti= -RLi-KeL+1Lv
Substitute x1 and x2
ddtx1= -bJx1-1Jd+KmJx2 
ddtx2= -RLx2-KeLx1+1Lu
Write in matrix form      and  
                
                
Substitute variables back in 


### Data Acquistion and Analysis

To model the drill we used a high speed camera to record data of the drill ramping up to full speed. Looking back at the data we were able to use step inputs of the amount of time it took the drill to make one rotation as it ramped up to full speed. From the video, the set of times it took the drill to complete one full rotation in seconds was:

[0.0656, 0.0574, 0.0543, 0.0521, 0.0489, 0.0482, 0.0475, 0.0481, 0.0467, 0.0461, 0.0459, 0.0454, 0.0458, 0.0461, 0.0455]

It is important to note that these times were all measured by hand with a stop watch, and were originally about 8-20 seconds before being transferred into real time. From these numbers the frequency step response and bode plots above were generated. Some other experimental parameters we were able to calculate from the video are:

The rotational speed from the first rotation: 95.8 rad/s (915 RPM)
The steady state rotational speed: 138.1 rad/s (1319 RPM)
Time constant: 0.176 s
Step magnitude/gain: 42.6 rad/s (404 RPM)
Bandwidth 1/T= 5.69 rad/s (0.91 Hz)

### Performance Limits
With these values, the steady state speed ceiling of the drill of 915 RPM and the acceleration limit from the time constant of 0.176s show the max speed of the drill and how long it will take to get there. These values show how quickly the drill reaches usable speed. 
The bandwidth of 0.91 Hz describes the range of input frequencies that the drill can accelerate at before the lag from the time constant begins to take effect. This value describes how quickly the drill can follow changes to input. 
There is a variability of about 0.0023 s per revolution or 6.6 rad/s (65 RPM) in the steady state velocity of the drill. This means that there is either variability with the steady state velocity or with our calculations, probably some combination of both. 	
The fitted first‑order exponential model closely follows the measured speed data, with deviations within ±5%. This confirms that the drill’s ramp‑up can be approximated as a first‑order system, though small discrepancies are expected due to manual timing and load fluctuations.	
Overall, the drill reaches steady‑state speed of 1319 RPM in under one second, with a bandwidth of 0.91 Hz and variability of ±65 RPM. These values define the drill’s performance envelope and can be used to model the drill, for controller design or for comparative analysis of similar systems.

### Bode Plots

<img src="{{ 'assets/images/sdissection-bode.png' | relative_url }}" width="100%">
                
Figure 1 and 2, Bode Plot showing open loop magnitude and phase vs input frequency. 

<img src="{{ 'assets/images/sdissection-step.png' | relative_url }}" width="100%">

Figure 3 and 4, Frequency step response graphs in rad/s and RPM showing the speed step response, with a fitted first order curve from the calculated system parameters. 

### Open Loop System

In open loop, the drill behaves like a DC motor driven directly by the trigger voltage with no feedback controller beyond the manual control of the variable speed trigger. The trigger position directly sets the motor voltage and the drill does not internally measure any speed. We can derive a transfer function from input voltage v(t) to output speed (t) by taking the Laplace transform of the coupled ODEs from above, where I(s), (s), V(s), TL(s) are the Laplace transforms of i(t), (t), v(t), TL(t), respectively:
Lddti= -Ri-Ke+v 			LsI(s) + RI(s)+Ke(s)=V(s)
Jddt= -b+Kmi-TL 	           	Js(s)+b(s)=KmI(s)-TL(s)

Solving these, we obtain:
(s) = KmV(s)-(Ls+R)TL(s)JLs2+(JR+Lb)s+(KeKm+Rb)

While this is a second order system, we can approximate it as a first order system by neglecting L, as the armature inductance is typically extremely small. This equation now becomes:
(s) = KmV(s)-RTL(s)(JR)s+(KeKm+Rb)

With no load disturbance torque (TL=0), the transfer function from voltage to speed is:
G(s)=(s)V(s)=Km(JR)s+(KeKm+Rb) . The denominator [(JR)s+(KeKm+Rb)] defines the poles of the open loop drill system.

Using this open loop model, with the time constant () found above and roughly estimated values for Km, Ke, R, and b, we obtain a plot (fig. 5) comparable to figures 3 and 4 above. 

<img src="{{ 'assets/images/sdissection-normalized-step.png' | relative_url }}" width="100%">

Figure 6, plot of normalized speed vs time using open loop model.

### Closed Loop System

To study feedback control, we conceptually added a speed sensor and a controller such that when the drill encounters a load disturbance TL(t), the controller will automatically adjust the applied voltage v(t) to correct for the load disturbance and ensure the drill remains at the desired speed.
We let:
r(t) be the step input, or speed commanded by the user
(t) be the measured speed
C(s) be the controller transfer function 

The error is then:	 			e(t) = r(t)-(t)

The controller generates the control voltage:	V(s) = C(s)E(s)= C(s)[R(s)-(s)]

Adding in a nonzero disturbance torque, the transfer function from load torque to speed is:

GTL= (s)TL(s)=R(JR)s+(KeKm+Rb)
From Gv(s)= (s)V(s), derived above, and GTL	
(s)=Gv(s)C(s)[R(s)-(s)]+GTL(s)TL(s)  (s)=C(s)Gv(s)1+C(s)G(s)R(s)+GTL(s)1+C(s)GTL(s)TL(s),
Where C(s)Gv(s)1+C(s)G(s) and GTL(s)1+C(s)GTL(s) are the closed-loop transfer functions from user-commanded speed to drill speed ((s)R(s)) and from disturbance torque to drill speed ((s)TL(s)), respectively.
If C(s) is a just proportional control, the response will be sped up, and under a constant trigger input and load torque, will reduce the steady state error but not eliminate it. When the bit encounters a disturbance torque, the speed with drop and error will grow. The controller will see this error and increase the input voltage in order to pull the speed back up, however even in steady state, there will still be some error between the commanded trigger input and the drill speed. If C(s) is a proportional integral control, disturbance rejection will be much better than if solely proportional control is used. Steady state error, even under load will be nearly zero, as the controller will keep winding up the integral term until the drill speed matches that of the commanded trigger input. PID control would further benefit the system, ensuring the error doesn’t change too fast and thus reducing overshoot, however this feels overkill and unnecessary. 
If we were to improve this drill, we would add a speed sensor and PI controller. Using the model above, with C(s)=Kp+Kis, we can determine the values for Kp and Ki needed to meet “better drill” design specifications.



