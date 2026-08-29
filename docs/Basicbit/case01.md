# Case 01: Automated Smart Playground Lamp

Level: ![level](images/level2.png)
![auto_fit](images/Case2/case-02.png)<P>

## Goal
<HR>

Make a smart playground lamp by detecting the motion nearby.
<BR><P>

## Background
<HR>

<span id="subtitle">What is smart playground lamp?</span><P>
Smart playground lamp is a lamp which can open automatically when someone passes by. Installing an auto-light can help the earth save electricity. When no one passes by, the light will automatically turn off.
Smart playground lamp operation
Motion sensor should be able to detect if there are people moving in the playground.
If there are people moving in the playground, the LED light should turn on, vice versa.<BR><P>

![pic_70](images/Case2/Concept-diagram-Case2.png)<P>


## Part List
<HR>

![auto_fit](images/Case2/Case2_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
Attach motion sensor and white LED to A1 model with M4 * 10mm screws and nuts.<BR><P>
![auto_fit](images/Case2/Case2_ass1.png)<P>
<span id="subtitle">Step 2</span><BR><P>
Assembly completed!<BR><P>
![auto_fit](images/Case2/Case2_ass2.png)<P>



## Hardware connect
<HR>

Connect Motion sensor to the P0 port of Smarthon Basic:bit<BR><P>
Connect LED light to the P3 port of Smarthon Basic:bit<BR><P>
Pull the buzzer switch ‘up’ to disconnect the buzzer in this execrise<BR><P>
![auto_fit](images/Case2/Case2_hardware.png)<P>
*Pull the buzzer switch 'up' to disconnect the buzzer in this execrise*

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Disable micro:bit LED.</span><BR><P>
Snap led enable false to on start.<BR><P>
Note that P3 is used as LED in default setting, LED need to be disable<BR><P>
![pic_50](images/Case2/Case2_p1.png)<P>

<span id="subtitle">Step 2. Turn on LED by motion sensor</span><BR><P>
*Drag forever from Basic<BR>
*Snap if statement into forever<BR>
*Set get motion (triggered or not) at P0 = true, into if statement that’s say motion is triggered, someone passes by.<BR>
*Then, turn white LED to 1023 at P3 as turning on white LED and pause 10 seconds.<BR>
*Else, turn white LED at P3 to 0 as turning off Full Solution.<BR>

![pic_90](images/Case2/Case2_p2.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: <a href="https://makecode.microbit.org/S68864-53853-05528-25643" target="_blank">https://makecode.microbit.org/S68864-53853-05528-25643</a>

![pic_80](images/Case2/Case2_full_program.png)<P>


## Result
<HR>

Motion sensor is used to detect if there are people moving in the playground. If there are, the LED light will be turned on; otherwise, it will be turned off.<BR><P>
![auto_fit](images/Case2/Case2_result.gif)<P>

## Think
<HR>

Q1. How can you use motion sensors, other than turning on the light automatically?<BR><P>
Q2. Can you show motion sensor value on OLED?<BR><P>
