# Case 03: Garbage disposal system 

Level: ![level](images/Case3/image1.png)
![auto_fit](images/Case3/case-03.png)<P>


## Goal
<HR>

Make a smart garbage bin by showing different colors of light according to the volume of garbage inside.<BR><P>

## Background
<HR>

<span id="subtitle">What is garbage disposal system?</span><P>
LED light on the garbage bin can show people the amount of garbage inside the garbage bin so that garbage truck can easily determine if the garbage is full or not. This can minimize the wastage of the garbage bags and become a more environmental-friendly city.<BR><P>

<span id="subtitle">Garbage disposal system operation</span><P>
The distance sensor should be able to sense the amount of garbage is inside the garbage bin. Multi-colour LED can be used to emit different colour of light (green and red light), which represent the emptiness of the garbage bin.<BR><P>
![pic_70](images/Case3/Concept-diagram-Case3.png)<P>

## Part List
<HR>

![pic](images/Case3/Case3_parts.png)<P>

## DIY Installation & Mounting

<span id="subtitle">1. Materials: Cardboard , scissors and tape.</span><BR><P>
![auto_fit](images/Case3/Case3_ass1.png)<P>

<span id="subtitle">2. Make the holes:</span><BR><P>
![auto_fit](images/Case3/Case3_ass2.png)

<span id="subtitle">3. Finished look:</span><BR><P>
![auto_fit](images/Case3/Case3_ass3.png)

*You can buy the material set from smarthon website.

## Hardware connect
<HR>

Connect the Distance Sensor to P14 (trig)/ P15 (echo) port of IoT:bit<BR>
Connect Multi-color LED to P1 port of IoT:bit<BR>
![pic](images/Case3/Case3_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Set variable and initialize multi-colour LED</span><P>
* Inside `on start`, snap `set variable distance to 0` from `variables`
* Snap `set strip to NeoPixel at pin... ` from `Neopixel`. Set pin P1 with 1 led of the block.
* Snap `strip set brightness` from `Neopixel` > `more` and set brightness 50
* Snap `pause` to wait 5 seconds
![auto_fit](images/Case3/Case3_p1.png)<P>

<span id="subtitle">Step 2. Get distance value</span><P>
* Inside block `forever`. Set `distance` to `get distance unit cm trig P14 echo P15`, that’s say get the distance value by connecting the distance sensor to P14 and P15
* Snap `if statement` into `forever`, set `distance ≤ 4` into `if statement`
* Snap `Pause` to the loop to wait 1 second for next checking
![pic_90](images/Case3/Case3_p2.png)<P>

<span id="subtitle">Step 3. Show indicating colours with distance value</span><P>
* If distance ≤ 4, then `strip show color red`, else `strip show color green`
![pic_90](images/Case3/Case3_p3.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: <a href="https://makecode.microbit.org/S69465-27557-58756-99835" target="_blank">https://makecode.microbit.org/S69465-27557-58756-99835</a>
![pic_90](images/Case3/Case3_full_program.png)<P>


## Result
<HR>

The distance sensor can return the distance value between the top of the garbage bin and the level of garbage inside the garbage bin. The LED light is used to indicate if the bin is full or not. If it is empty or there are some garbage, the LED turns green, if it is full, the LED turns red.<BR><P>
![pic](images/Case3/image13.gif)<P>

## Think
<HR>

Q1. How to make sound notification if there are full of garbage (i.e. using buzzer)?<BR><P>
