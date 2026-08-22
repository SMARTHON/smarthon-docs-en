# IoT Case 08: Weather-Adaptive Irrigation (Outdoor)
![auto_fit](images/case08/image15.png)
## Goal
<HR>

Create an irrigation system that automatically adjusts the watering schedule according to the weather.

## Background
<HR>

<b>What is Weather Adjustment Irrigation?</b><P>

A Weather Adjustment Irrigation system is an automated solution designed to optimize watering schedules based on real-time weather conditions. By automatically adjusting the watering frequency according to rainfall, users can ensure that their plants receive the right amount of water. This system not only conserves water but also promotes healthier plant growth.

<b>Weather Adjustment Irrigation Operation</b>

In this case, we use a fog module to simulate the irrigation process.

The board connects to the Wi-Fi and displays a tick signal when successful. When there are changes in the current weather conditions, the IFTTT applet will send a signal to the IoT board. After receiving the signal, the board will skip the next scheduled irrigation.

![pic](images/case08/flowchart.png)


## Part List
<HR>

![auto_fit](images/Case8.jpg)


## Assembly Steps

<span id="subtitle">Step 1</span><BR><P>
Step 1. To start with, build the plant pot model with soil and seedling.<BR><P>
![pic](images/case08/image14.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Connect the Fog Module with a 3-pin module wire. Install the Fog Module and Fog Accessories as shown in the pictures. (The detail sheps is shown on the pictures. Please follow the order of the pictures from left to right to do this step)
<BR><P>

![pic](images/case08/Step4_combined.jpg)

<span id="subtitle">Step 3</span><BR><P>
Put the Fog Module and Fog Accessories components into the Humidifier Cup.<BR><P>

![pic](images/case08/Step3.png)

![pic](images/case08/Step3a.jpg)

<span id="subtitle">Step 4</span><BR><P>
Put the model onto the pot tray and plastic mat. Completed!<BR><P>

![pic](images/case08/Step4.jpg)

## Hardware Connection
<HR>

1. Connect Fog Module to P0.
![auto_fit](images/case08/image62.png)<P>

## Programming (MakeCode)
<HR>

MakeCode: [https://makecode.microbit.org/\_2kRdtYeAEThv](https://makecode.microbit.org/_2kRdtYeAEThv)   
![auto_fit](images/case08/image72.png)<P>


## IoT (IFTTT)
<HR>

1. Go to [https://ifttt.com](https://ifttt.com), register an account and login to the platform.
![auto_fit](images/case08/image61.png)

<P>
2. On the top right menu, click “Create”.

![auto_fit](images/case08/image57.png)

<P>
3. Create tigger by:  

* Select “This”.  

* Select Weather Underground.  

* Select “Current condition changes to”.  

* Input the Current condition (Rain) and location. 
 
* Click “Create trigger”.

![auto_fit](images/case08/image102.png)

<P>
4. Create action by:  

* Select “That”.  

* Select Smarthon IoT (micro:bit).  

* Select “Control Command”.  

* Input IoT:bit’s device ID and Command “stopIrrigationOnce”. 
 
* Click “Create action”.

![auto_fit](images/case08/image39.png)

## Result
<HR>

![auto_fit](images/case08/image93.gif)<P>