# IoT Case 10: Smart Street Light

Level: ![level](images/level4.png)
![auto_fit](images/Case10/case-10.png)<P>

## Goal
<HR>

Make a smart streetlight that automatically controls the LED based on simulated time and ambient light levels. <BR><P>

## Background
<HR>

<span id="subtitle">What is Smart Street Light?</span><BR><P>
To improve the living standards of citizens and save electricity, smart street lights can be automatically adjusted according to the time of day and environmental brightness.<BR><P>
<span id="subtitle">Smart Streetlight operation</span><BR><P>
The system uses a timer to simulate a 24-hour cycle. During the active daytime period (e.g., 6 AM to 6 PM), the micro:bit monitors the light value at Pin P2. If the environment becomes too dark (light < 40%), the LED will automatically turn on to ensure safety.<BR><P>
![auto_fit](images/Case10/Concept-diagram-Case10.png)<P>

## Part List
<HR>

![auto_fit](images/Case10/case10_parts.png)<P>

## Assembly step
<HR>

* Materials:Cardboards, scissors and tape.<BR><P>
![auto_fit](images/Case10/Case10_ass1.png)<P>
* Make the holes :<BR><P>
![auto_fit](images/Case10/Case10_ass2.png)<P>
* Finished look :<BR><P>
![auto_fit](images/Case10/Case10_ass3.png)<P>
* You can buy the material set from smarthon website.<BR><P>



## Hardware connect
<HR>

Connect the white LED Light to P0 port of Basic:bit.<BR><P>
Connect the Light Sensor to P2 port of Basic:bit.<BR><P>

![auto_fit](images/Case10/Case10_hardware.png)<P>
Pull the buzzer switch ‘up’ to disconnect the buzzer in this execrise<BR><P>


## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize the simulated timer
* Create a new variable named time. 
* Snap `set time to 0` to `on start` 
![pic_60](images/Case10/Case10_p1.png)<P>

<span id="subtitle">Step 2. Simulate Time and Read Light Levels</span><BR><P>
* Snap `pause (ms) 3600000` into the `forever` block.This represents 1 hour (60 mins × 60 secs × 1000 ms).
* Create a new `variable` named light
* Below the `pause`, snap `change time by 1` to simulate the passing of each hour
* Snap `set light to Get light value (percentage) at Pin P2` below the time update
![pic_60](images/Case10/Case10_p2.png)<P>

<span id="subtitle">Step 3. Logic Judgment for Time and Brightness</span><BR><P>
* Snap an `if block with the logic: time > 6 and time < 18`
* Inside the first `if`, nest another `if` block with the logic: `light < 40`
* If the condition is met, `Turn White LED to 1023 at P0`. Otherwise (else), `Turn White LED to 0 at P0`
![pic_60](images/Case10/Case10_p3.png)<P>

<span id="subtitle">Step 4. Reset the Timer</span><BR><P>
* Click the (+) on the bottom of the `if` block to add an `else if` section
* Set the condition to `time = 24`
* Snap `set time to 0` inside this section to restart the daily cycle
![pic_80](images/Case10/Case10_p4.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode:<a href="https://makecode.microbit.org/_KbHfEVbTPaT8"
target="_blank">https://makecode.microbit.org/_KbHfEVbTPaT8</a> 

![pic_100](images/Case10/Case10_p5.png)<P>

 
 
## Result
The micro:bit automatically monitors the time and ambient light levels. During the simulated daytime (6:00 to 18:00), the LED light will automatically turn on (intensity 1023) if the environment becomes dark (light < 40%). At all other times or when it is bright enough, the LED remains off. The timer resets to 0 every 24 hours to ensure continuous daily operation.<BR><P>

![auto_fit](images/Case10/Case10_result.gif)<P>



## Think
<HR>

Q1.  If the street light turns on too early in the evening, which value in the code should you adjust to make it more sensitive to darkness?<BR><P>
