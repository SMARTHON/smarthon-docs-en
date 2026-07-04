# Case 02: Automated Watering System

![pic](images/case02/image49.png)

## Goal
<HR>
Create an automatic irrigation system that will water the plant whenever the soil moisture sensor senses the lack of water in the soil.<P>


## Background
<HR>
<b>What is an Automatic Irrigation System?</b><P>

Automatic Irrigation System tracks the soil moisture in real time using a sensor without having to rely on our guesses. It will water the plant for you whenever the soil moisture gets dangerously low. This type of system is used in modern farming and increases the crop yield and consequently reduces the unnecessary use of water. 

<b>Automatic Irrigation System Operation</b>

The soil moisture sensor is embedded in the plant pot. Whenever the soil moisture gets low, the water pump is triggered, and pumps water through a tube that water the plant until the soil moisture level is satisfactory, upon which the pump stops. 

<b>Know More: Why is Water Important for Plant Growth?</b>

Water provides the hydrogen ions needed in photosynthesis to convert sunlight into energy. It also dissolves minerals from the soil and transports them through the plant's vascular system (xylem) to different parts of the plant, supporting overall growth.

Additionally, water maintains turgor pressure in cells, keeping plants upright and enabling cell expansion. It also helps cool the plant and prevent overheating through transpiration, a process in which water evaporates from the leaves.

![alt="auto_fit"](images/case02/image151.png)  ![pic](images/case02/image64.png)

## Part List
<HR>

![alt="auto_fit"](images/case02/case02_parts.png)<P>

## Assembly Steps

<span id="subtitle">Step 1</span><BR><P>
To start with, build the plant pot model with soil and seedling.<BR><P>
![pic](images/case02/image14.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Assemble D1 with D3.<BR><P>
![pic](images/case02/Step2.png)

<span id="subtitle">Step 3</span><BR><P>
Assemble D2 with the above part.<BR><P>

![pic](images/case02/Step3.png)

![pic](images/case02/Step3a.png)

<span id="subtitle">Step 4</span><BR><P>
Fixed them with two F. Complete this part!.<BR><P>
![pic](images/case02/Step4.png)


<span id="subtitle">Step 5</span><BR><P>
Combine the above part with the plant pot.<BR><P>

![pic](images/case02/Step5.png)

<span id="subtitle">Step 6</span><BR><P>
Put the water pump into the pump cup, then insert the pump tube between D1 and D2 as shown in the picture.<BR><P>

![pic](images/case02/Step6.png)

![pic](images/case02/Step6a.jpg)

![pic](images/case02/Step6b.png)


<span id="subtitle">Step 7</span><BR><P>
Put the soil moisture sensor into the soil. Complete!<BR><P>

![pic](images/case02/Step7.png)


<span id="subtitle">Points to Note</span><BR><P>

Keep the water tube end higher than the water level in the cup to prevent the siphon effect, which causes water to flow uncontrollably to the plant.  
![pic](images/case02/image157.png)

## Hardware Connection
<HR>

1. Connect Soil Moisture Sensor to P1.  
2. Connect Water Pump to P2.  
3. Connect LCD Display to I2C.

![pic](images/case02/image188.png)


## Programming (MakeCode)
<HR>

MakeCode: [https://makecode.microbit.org/\_fh8PjhV7cXPp](https://makecode.microbit.org/_fh8PjhV7cXPp)   
![pic](images/case02/image1.png)<P>

Advanced \- time control: [https://makecode.microbit.org/\_V0gEzw1bhDtH](https://makecode.microbit.org/_V0gEzw1bhDtH)   
![pic](images/case02/image15.png)<P>


## Result
<HR>

![auto_fit](images/case02/image153.jpg)

## Think
<HR>
Q1. Why do you think we need to set a pause for the water pump function? Is it because of the plant or programming?
<P>