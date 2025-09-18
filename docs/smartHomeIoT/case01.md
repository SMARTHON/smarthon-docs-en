# Case 01: Smart Saving Light Bulb

Level: ![level](images/level1.png)
![auto_fit](images/Case1/intro.png)<P>


## Goal
<HR>
Make a smart light bulb by detecting motion around the environment.<P>

## Background
<HR>
<span id="subtitle">What is a Smart Light Bulb?</span><P>

Smart light bulb is a smart light bulb that helps automation and saving electricity. When there is people coming in, the bulb will be turned on automatically. People always forget to turn off the light when he/she leave. After 10 mins, if there are no any motions inside the room, it will close the LED to save energy. <P>

<span id="subtitle">Smart Saving Light Bulb Principle</span><P>

Motion sensor is used to detect the presence of human activity in the room. If there are people moving in the room, the light bulb will be turned on, vice versa.<BR>


![pic_70](images/Case1/Case1_flowchart.png)<P>

## Part List
<HR>

![pic_90](images/Case1/Case1_parts_new.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
Step 1. To start with, build the Big House Model.<BR><P>
![auto_fit](images/Case1/Case1_ass1_new.png)<P>
<span id="subtitle">Step 2</span><BR><P>
 Pick one corner of the house. In this example, we pick the left upper corner, install the 2 walls (E1 & E2) to build a small room.<BR><P>
![auto_fit](images/Case1/Case1_ass2_new.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Attach the PIR Motion Sensor to model B3 using M4 * 10mm screws and nuts.<BR><P>
![auto_fit](images/Case1/Case1_ass3_new.png)<P>
<span id="subtitle">Step 4</span><BR><P>
Attach the Multi-color LED to the model B3 using M4 * 10mm screws and nuts.<BR><P>
![auto_fit](images/Case1/Case1_ass4_new.png)<P>
<span id="subtitle">Step 5</span><BR><P>
Installation completed!<BR><P>
![auto_fit](images/Case1/Case1_ass5_new.png)<P>
<span id="subtitle">Step 6</span><BR><P>
To build a Bed. Put model J2 onto the model J1, then put together all the cardboard parts (J1-J3).<BR><P>
![auto_fit](images/Case1/Case1_ass6_new.png)<P>
<span id="subtitle">Step 7</span><BR><P>
The bed completed!<BR><P>
![auto_fit](images/Case1/Case1_ass7_new.png)<P>
<span id="subtitle">Step 8</span><BR><P>
Place the bed inside the bedroom. <BR><P>
![auto_fit](images/Case1/Case1_ass8_new.png)<P>
<span id="subtitle">Step 9</span><BR><P>
Assembly completed!<BR><P>
![auto_fit](images/Case1/Case1_ass9_new.png)<P>


## Hardware connect
<HR>

1. Connect the motion sensor to P0<BR>
2. Pull up the switch to avoid interference from buzzer<BR>
3. Connect the Multi-color LED(WS2812) to P1<BR>

<BR>![auto_fit](images/Case1/Case1_hardware.png)
<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize Multi-Color LED</span><BR><P>
* Before using the Multi-Color LED, need to do initialize
* Pull the `set strip to NeoPixel at pin P1 with 1 leds as RGB(GRB format)` to `on start`

![pic_90](images/Case1/Case1_p1.png)<P>

<span id="subtitle">Step 2. Change the LED Color by motion sensor result</span><BR><P> 
* In `Forever`, add a `if-else` statement
* Set (`Get motion (triggered or not) at Pin P0` = `true`) as condition
* Snap `strip show color white` into the `if` segment
* Snap `pause(ms) 10000` into `if` segment to keep light up for 10 second
* Snap `strip show color black` into the `else` segment
* When the condition is correct, that’s say motion is triggered, someone passes by.<BR>The program will run the `if` segment to turn on the light
* Otherwise, the program will run the `else` segment to turn off the light
![pic_90](images/Case1/Case1_p2.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: <a href="https://makecode.microbit.org/S44525-40482-50586-80115" target="_blank">https://makecode.microbit.org/S44525-40482-50586-80115</a><BR><P>
You could also download the program from the following website:<BR>

<iframe src="https://makecode.microbit.org/S44525-40482-50586-80115" width="100%" height="500" frameborder="0"></iframe>

<P>

## Result
<HR>

When the people are moving in the room, the motion sensor will trigger and keep the LED turned on. When there is no one moving, the LED will turn off.<BR><P>
![auto_fit](images/Case1/Case1_result.gif)<P>

## Think
<HR> 

Q1. Besides implementing the smart light bulb into the toilet, where other places can the light bulb also be implemented? Discuss the place and briefly explain the point on energy reservation.<BR><P>
Q2. Suggest addition of any component that allows the light bulb to be even smarter.
<BR><P>
Q3. Can you add the timer in the program to make it only turn off after 10min of no activity? <BR><P>