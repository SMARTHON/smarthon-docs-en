# IoT Case 07: Smart defense system

Level: ![level](images/Case7/level3.png)
![auto_fit](images/Case7/case-07.png)<P>

## Goal
<HR>

Make a smart defense system which emits sound and sends an email to the house owner if there are any suspicious movement near the door.<BR><P>

## Background
<HR>

<span id="subtitle">What is a Motion Sensor?</span><BR><P>
A motion sensor (PIR) is a device that detects moving objects, especially people, by measuring infrared light radiating from objects in its field of view.<BR><P>
<span id="subtitle">Smart defense system operation</span><BR><P>
The motion sensor can deliver a motion signal to the micro:bit. When the micro:bit detects the signal, the buzzer will emit sound to alert the owner immediately. Also, a monster icon will be shown on the micro:bit to warn any suspicious people passing by.<BR><P>
![auto_fit](images/Case7/Concept-diagram-Case7.png)<P>

## Part List
<HR>

![auto_fit](images/Case7/Case7_parts.png)<P>

## DIY Installation & Mounting

<span id="subtitle">1. Materials: 6 Cardboards(11.5cm x 13cm ) , scissors and tape.</span><BR><P>
![auto_fit](images/Case7/4.png)<P>

<span id="subtitle">2. Make the holes:</span><BR><P>
![auto_fit](images/Case7/7.png)

<span id="subtitle">3. Finished look:</span><BR><P>
![auto_fit](images/Case7/10.png)

*You can buy the material set from smarthon website.

## Hardware connect
<HR>

Connect the Motion Sensor to P1 port of IoT:bit<BR>
Turn on the Buzzer Switch on P0 port of IoT:bit<BR>
![auto_fit](images/Case7/Case7_hardware.png)<P>

*Pull the buzzer switch <B>'down'</B> to connect the buzzer in this execrise*


## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize System</span><BR><P>
* Snap `show icon (tick)` to `on start`. This indicates the program has started successfully and the system is ready. 
![auto_fit](images/Case7/Case7_p1.png)<P>

<span id="subtitle">Step 2: Check motion sensor value</span><BR><P>
* Snap `if statement` into `forever block`. `If Get motion` at `Pin P1 = true`, then it means someone is near the door.
![auto_fit](images/Case7/Case7_p5.png)<P>

<span id="subtitle">Step 3. Sound and Visual Alarm</span><BR><P>
*If triggered, `play tone` `Middle C `for `1 beat` and show icon `monster`.
*Else, show icon `smile`.
*Snap `pause (ms) 1000` at the end of the `loop` for 1 second delay.
![auto_fit](images/Case7/Case7_p4.png)<P>
 
<span id="subtitle">Full Solution<BR><P>
MakeCode: <a href="https://makecode.microbit.org/_fmLDcg39ERhx" target="_blank">https://makecode.microbit.org/_fmLDcg39ERhx</a>
![auto_fit](images/Case7/Case7_full_program.png)<P>

## Result 
<HR>

If there is any suspicious movement detected near the door, the buzzer will emit an alarm sound immediately and a monster icon will be shown on the micro:bit to warn the intruder. When it is safe, a smile icon will be shown.<BR><P>
![auto_fit](images/Case7/image5.gif)

## Think
<HR>

Q1. How to prevent the buzzer from beeping continuously when someone stays near the door? (tips: using a variable as a 'flag')<BR><P>
Q2. How to let the owner pass without triggering the alarm (e.g. pressing a specific button as a password)<BR><P>

