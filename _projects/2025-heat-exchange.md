---
layout: project
title: Heat Exchanger Project
description: Heat exchanger analysis
technologies: n/a
image: /assets/images/image.png
---

In a class assignment, we were given the option to complete a fixed mini-lab. We experimentally analyzed a heat transfer setup by measuring the temperatures of the water used and the external components of the heat exchanger. This analysis was intended to identify differences between ideal and real heat exchangers. 

_______________________________________________________________________________________________________________

**The setup for the project can be described as the following:**

Two containers were used to hold water. One was a bucket with an electric immersion heater, and the other was a bucket with an insulating bag and ice. The "hot" reservoir held red-dyed water, while the "cold" reservoir held blue-dyed water. The hot reservoir was held to be close to 40 °C. The cold reservoir was held from 4 to 10 °C.

Two battery powered pumps were placed within the tanks. They were connected to the heat exchanger with plastic hoses. This heat exchanger had two channels where water could flow. The channels run parallel to each other, so that there are two parallel holes on two sides of the exchanger. There were two pipe configurations used:

- **parallel flow** - the cold and hot water paths faced the same direction; they went into and out of the heat reservoir through the same side

- **counterflow** - the cold and hot water paths faced opposite directions; the outflow side for one liquid was the inflow side for the other, which meant the two liquids would flow in opposite directions

The heat exchanger flowed out to two separate plastic containers with no other additional items. 

To measure the temperature, a standard thermometer was used to measure the water before and after going through heat transfer. A thermometer device called a thermocouple was used to measure parts of the heat exchanger itself. 

_______________________________________________________________________________________________________________

![Shaded rendering of earlier version]({{ "/assets/images/parallel.png" | relative_url }}){: .inline-image-c style="width: 576px"}

*Above: diagram of parallel flow*

![Shaded rendering of earlier version]({{ "/assets/images/counter.png" | relative_url }}){: .inline-image-c style="width: 576px"}

*Above: diagram of counterflow*

_______________________________________________________________________________________________________________

A heat exchanger works by allowing two fluids of different temperature to transfer heat. In this case, the two fluids are dyed water. An ideal heat exchanger is considered adiabatic (no external heat transfer) and steady state (equal in and out flow). These assumptions will be false in real world scenarios, especially this one, because materials usually conduct some amount of heat. This exchanger was made out of metal, so it will conduct a considerable amount of heat.  

_______________________________________________________________________________________________________________

![Shaded rendering of earlier version]({{ "/assets/images/heat.png" | relative_url }}){: .inline-image-c style="width: 576px"}

*Heat transfer occurs in and out of the heat exchanger system. An adiabatic process means the external heat transfer is nonexistent. This is usually a good approximation when the system is very well insulated.*

_______________________________________________________________________________________________________________

The pumping process is not steady state, because the pumps are being used in a short amount of time. This means there is some time when there is more inflow than there is outflow. However, this difference is small, because the time the pump takes to fill the volume of the system, primarily the volume of the hoses and the exchanger, is not very long. 

The heat exchanger is not adiabatic, because it is made out of metal and is not perfectly insulated. This means the exchanger interacts with the ambient air. The rubber hosing is more insulating, but it is not a perfect insulator either. 

While it is known this setup is not adiabatic nor steady state, it can be useful to calculate how much the real process deviates from ideal processes. My group used several trials to obtain temperatures of both red and blue liquids before and after the heat exchange. 

*From now, the hot and cold reservoirs will be denoted as h and c. The initial and final states of any reservoir will be denoted as i and f. In and outflow will be denoted as i and o*

**Temperature measurements:**

Trial 1: Parallel
- T<sub>hi</sub> = 38.9 °C
- T<sub>hf</sub> = 22.7 °C
- T<sub>ci</sub> = 4.8 °C
- T<sub>cf</sub> = 19.2 °C

Trial 2: Counter
- T<sub>hi</sub> = 39.2 °C
- T<sub>hf</sub> = 16.8 °C
- T<sub>ci</sub> = 6.2 °C
- T<sub>cf</sub> = 22.0 °C

_______________________________________________________________________________________________________________

For analysis, the temperature data can help determine the heat transfer inside the exchanger. This is done through a control-volume approach, in which an equation is used to balance the energy changes within the system. This equation factors in the flow of two liquids.

![Shaded rendering of earlier version]({{ "/assets/images/1.png" | relative_url }}){: .inline-image-c style="width: 576px"}

This equation can be further simplified to a more useful form:

- The total energy change rate, factoring in all variables, is set to 0, because within the system and accounting for boundary interactions, the conservation of energy applies. 

- The work rate W dot in the system is 0, because there is no turbine or other mechanism that deals with work. The pumps do require work, but they are not part of the system being analyzed.  

- The heat rate Q dot in the system is 0 if the process is adiabatic. This is because the internal Q is related to another part of the equation. The external Q is the heat exchange with the environment.

- m<sub>i</sub> dot and m<sub>o</sub> dot are equal for both temperatures, because the process is mostly steady state. As discussed before, there is a short period where that is false, but that time is relatively small.

- m<sub>h</sub> and m<sub>c</sub> are equal, because the pumps used are the same.

- Kinetic and gravitational potential KE and PE are 0, because they are negligible. The water has mass, but it does not significantly change in elevation, and the velocity of the water from the pumps is not large. 

The above simplifications allow for a relatively accurate analysis of the system without additional data. 

The final equation is as follows:

![Shaded rendering of earlier version]({{ "/assets/images/2.png" | relative_url }}){: .inline-image-c style="width: 576px"}


_______________________________________________________________________________________________________________

For an ideal, adiabatic scenario, q is also 0. This means the change in enthalpy of one liquid is equal to the inverse of the change in enthalpy of the other. More specifically, The internal energy flows (in the form of heat) from the hotter reservoir to the colder one, in compliance with the second law of thermodynamics. 

For this real setup, there will likely be some sort of heat exchange with the environment. This exchange occurs at different points of the system. For instance, the temperature across the exchanger will be different, based on which specific part of the exchanger is measured. 

For my analysis, I am going to find the external q (specific heat transfer) of the real exchanger in two setups. I am also going to calculate the heat rejected from the hot stream and the heat introduced to the cold stream. 

_______________________________________________________________________________________________________________

**Finding necessary enthalpy h values**

The necessary quantity for my calculations was enthalpy, a type of internal energy that also factors the ability of gas to do work. Using a water data table from the school textbook *Fundamentals of Engineering Thermodynamics*, I found the approximate enthalpies of all four states in this setup. This table compared known values (temperature) to ones more difficult to measure (enthalpy). I classified my two water types as being saturated liquids at 1 atm of pressure. 

**parallel**

- h<sub>hi</sub> at 38.9 °C = 167.53
- h<sub>ho</sub> at 22.7 °C = 83.92
- h<sub>ci</sub> at 4.8 °C = 21.02
- h<sub>co</sub> at 19.2 °C  = 83.92

**counter**

- h<sub>hi</sub> at 39.2 °C = 167.53
- h<sub>ho</sub> at 16.8 °C = 62.98
- h<sub>ci</sub> at 6.2 °C = 21.02
- h<sub>co</sub> at 22.0 °C = 83.92

*Most values are approximations. Specific enthalpy is measured in kJ/kg*

_______________________________________________________________________________________________________________

**Finding heat exchange q:**

Because my group did not try to measure the flow rate from the pumps, it will be easier to compare the quantities with a formula in a slightly different form:

![Shaded rendering of earlier version]({{ "/assets/images/3.png" | relative_url }}){: .inline-image-c style="width: 576px"}

From this formula, I computed the q values to be the following:

q<sub>parallel</sub> = -20.71 

q<sub>counter</sub> = -41.65

*q is in kJ/kg*

**Finding change in h:**

The change in enthalpy of the two liquids is also useful information. Using the respective h values, I took the final minus the initial to find these values:

**parallel**

Δ h<sub>h</sub> = -83.61

Δ h<sub>c</sub> = 62.90

**counter**

Δ h<sub>h</sub> = -104.55

Δ h<sub>c</sub> = 62.90

*change in h is in kJ/kg*

_______________________________________________________________________________________________________________

**External heat exchange analysis**

It appears q<sub>counter</sub> is the greater of the two q values. Both values are negative, which signals q out, according to sign conventions. However, the results are not the most reliable. There were precision limitations with the chart I was using, which signals great error. Furthermore, only one value in the counterflow was significantly different, that being T<sub>ho</sub>. This value was lower than expected, which may have affected the results.

For an ideal heat exchanger, having minimized q should make the process better at exchanging, but in these two examples, the one with more q cooled slightly better. This suggests that either the experiment had many deviations, causing these results, or that the counterflow system really performs like this. 

The q found here would likely be minimized if many of the components in the experiment were better insulated. Notably, the hot side of the exchanger cooled by 6 °C, and the cold side warmed by 4 °C. This temperature was measured outside of the exchanger internals, so these temperatures will have some interaction with the environment. Reducing the external heat transfer should also make the heat exchanger better. 

**Change in enthalpy analysis**

From these two trials, it appears that the counterflow system was better at removing heat from the hot water, but not better at adding heat to the cold water. This is possibly also due to experimental variation, as the experiment was not run many times for more data points. 

_______________________________________________________________________________________________________________

**Conclusion**

Due to limited data collection, the results found are unreliable. The experiment took single trials, so there is no practical way to conduct a data analysis, and more trials are desired to make a more definitive conclusion. 

However, there appears to be some difference between parallel and counterflow systems; the counterflow system appears to reject more heat from the system; more heat was removed from the hot water, and more external heat loss was observed. As such, a counterflow system may be more desired for a greater cooling effect. A parallel system may be desirable for having less heat loss according to these results. 
