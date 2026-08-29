# Case 09: Smart House door control

Level: ![level](images/level4.png)
![auto_fit](images/Case9/case-09.png)<P>

## Goal
<HR>

Use the "IoT microbit" app to control the door of the house via Bluetooth. <BR><P>

## Background
<HR>

<span id="subtitle">What is IoT microbit APP?</span><BR><P>
IoT microbit is a ready-to-use application available on Google Play and App Store. It allows users to control micro:bit sensors and actuators (like LED and Servos) directly via Bluetooth without building an app from scratch.<BR><P>
<span id="subtitle">Smart House door operation</span><BR><P>
When the micro:bit receives the Bluetooth signal "a" (triggered by the icon ON in the app), the 180° servo will turn to 45° to open the door.
When the micro:bit receives the Bluetooth signal "b" (triggered by the icon OFF in the app), the 180° servo will turn to 180° to close the door.<BR><P>
![auto_fit](images/Case9/Concept-diagram-Case9.png)<P>

## Part List
<HR>

![auto_fit](images/Case9/case9_parts.png)<P>

## Assembly step
<HR>

* Materials: 6 Cardboards(11.5cm x 13cm ) , scissors , tape and swastika clip .<BR><P>
![auto_fit](images/Case9/Case9_ass1.png)<P>
* Make the holes :<BR><P>
![auto_fit](images/Case9/Case9_ass2.png)<P>
* Back: Attached to the 180° Servo using a swastika clip.<BR><P>
![auto_fit](images/Case9/Case9_ass3.png)<P>
* Finished look:<BR><P>
![auto_fit](images/Case9/Case9_ass4.png)<P>



## Hardware connect
<HR>

Connect the 180ᵒ servo to P0 port of Basic:bit<BR><P>

Micro:bit P0|Servo
-:-|-:-
S (yellow)|S (orange)
V (red)|V (red)
G (black)|G (brown)

![auto_fit](images/Case9/Case9_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Start-up:
* When the micro:bit powers on, `basic.showIcon(IconNames.Heart)` displays a heart icon on the LED screen to show the program is running. 
![pic_60](images/Case9/Case9_p1.png)<P>

<span id="subtitle">Step 2. Button A Action: </span><BR><P>
* Pressing `Button A` triggers `pins.servoWritePin(AnalogPin.P0, 45)`, rotating the motor on pin `P0 to 0 degrees`, and displays a checkmark icon.
![pic_60](images/Case9/Case9_p2.png)<P>

<span id="subtitle">Step 3. .Button B Action: </span><BR><P>
* Pressing `Button B` triggers `pins.servoWritePin(AnalogPin.P0, 180),` rotating the motor on pin `P0 to 90 degrees`, and displays an "X" icon.
![pic_60](images/Case9/Case9_p3.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_1sH0s1bLTDdb](https://makecode.microbit.org/_1sH0s1bLTDdb)<BR><P>

![auto_fit](images/Case9/Case9_fullsolution.png)<P>

You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/_1sH0s1bLTDdb" width="100%" height="500" frameborder="0"></iframe>


## Result

![auto_fit](images/Case9/image18.gif)<P>


## Think
<HR>

Q1. How can we add password authentication to open the door?<BR><P>
Q2. We can install the servo to different position in the house (tips: modify the turning angle of the servo)<BR><P>
