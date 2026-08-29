# Case 04: Urban noise detection

Level: ![level](images/Case4/level2.png)
![auto_fit](images/Case4/case-04_1.png)<P>

## Goal
<HR>

Make a noise detection point to detect the noise volume near the roadside using noise sensor.<BR><P>

## Background
<HR>

<span id="subtitle">What is urban noise detection?</span><P>
It is a system to detect noise near the road as noise pollution caused by cars on the road seriously affect the living standard of people. By installing a monitor to detect the noise volume near the roadside can help engineer to gather noise information and find solution to solve the problem in the future.<BR><P>

<span id="subtitle">Noise detection operation</span><P>
The noise sensor can detect the volume in dB near the roadside. A bar graph of sound intensity will be shown on the micro:bit LED display to represent the noise level in real-time.<BR><P>
![pic_70](images/Case4/Concept-diagram-Case4.png)<P>


## Part List
<HR>

![pic](images/Case4/Case4_parts.png)<P>

## Assembly step 
<HR>

<span id="subtitle">Step 1 Materials: micro:bit ,Basic:bit
.</span><P>
![pic](images/Case4/Case4_ass1.png)<P>

<span id="subtitle">Step 2 Finished look:</span><P>
![pic](images/Case4/Case4_ass2.png)<P>

*You can buy the material set from smarthon website.
## Hardware connect
<HR>

Connect Noise Sensor to P1 port of IoT:bit<BR><P>
Extend the connection of OLED to I2C connection port of IoT:bit<BR><P>
![pic](images/Case4/Case4_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize the variable</span><P>
* Drag Set `Noise` to `0` from the `variables` category to the on `start` block.
![auto_fit](images/Case4/Case4_p1.png)<P>

<span id="subtitle">Step 2. Display the noise level as a bar graph on the LED matrix.</span><P>
*In the `forever` block, Set `Noise` to sound level.
* Use the `plot bar graph` of block to visualize the `Noise` variable. Set the `maximum value` to `255` to represent the scale.
*Add a `pause (ms) 500` block to the `loop` for a smoother update interval.
![auto_fit](images/Case4/Case4_p2.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: <a href="https://makecode.microbit.org/_0kAEuieuuLqF" target="_blank">https://makecode.microbit.org/_0kAEuieuuLqF</a>

![pic_80](images/Case4/Case4_full_program.png)<P>

## Results
<HR>

After the program starts, the micro:bit will display a real-time bar graph on its LED matrix representing the sound intensity. The more LEDs that light up, the louder the ambient noise.<BR><P>
![pic](images/Case4/Case4_result.gif)<P>
![pic](images/Case4/Case4_result2.png)<P>
## Think
<HR>

Q1. How to make a notification if noise pollution problem is serious? i.e. showing red LED<BR><P>

