# IoT Case 06: Weather Station 

Level: ![level](images/Case6/level2.png)
![auto_fit](images/Case6/case-06.png)<P>

## Goal
<HR>

Make a weather station which gets the values from the raindrop sensor and built-in temperature sensor.<BR><P>

## Background
<HR>

<span id="subtitle">Local Data Monitoring</span><BR><P>
The weather station provides an instant display of environmental data. In this case, we will use the Serial Monitor to observe the sensor data trends in real-time.<BR><P>

<span id="subtitle">Weather station operation</span><BR><P>
Collecting temperature and raindrop values consistently. This helps us observe environmental changes more conveniently through data graphs on the computer.<BR><P>
![auto-fit](images/Case6/Concept-diagram-Case6.png)<P>

## Part List
<HR>

![auto_fit](images/Case6/Case6_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">1. Materials: 6 Cardboards(11.5cm x 13cm ) , scissors and tape.</span><BR><P>
![auto_fit](images/Case6/Case6_ass1.png)<P>

<span id="subtitle">3. Finished look:</span><BR><P>
![auto_fit](images/Case6/Case6_ass2.png)

*You can buy the material set from smarthon website.



## Hardware connect
<HR>

Connect the Raindrop Sensor to P0 port of Basic:Bit<BR><P>
![auto_fit](images/Case6/Case6_hardware.png)<P>

*Pull the buzzer switch 'up' to disconnect the buzzer in this execrise*

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize variables and show status</span><BR><P>
* Set `variable` `raindrop` and `temperature` to `0`.<BR>
* Snap `show icon (tick)` from `Basic` to `on start`<BR>
* Snap `serial redirect to USB` to `on start`<BR>
![auto_fit](images/Case6/Case6_p1.png)<P>

<span id="subtitle">Step 2. Get temperature and raindrop values in loop</span><BR><P>
* Drag the `forever block` from `Basic`.<BR>
* Snap `set temperature` to temperature (°C) from `Input`<BR>
* Snap `set raindrop` to get `raindrop` value (percentage) at Pin `P0`<BR>
* Snap `serial write value` "Temp" = `temperature to send data to computer`<BR>
* Snap `serial write value` "Rain" = `raindrop to send data to computer`<BR>
* Snap pause (ms) 500 to the loop

![auto_fit](images/Case6/Case6_p2.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: <a href="https://makecode.microbit.org/_7f8VVCJ7WMAf" target="_blank">https://makecode.microbit.org/_7f8VVCJ7WMAf</a>

![auto_fit](images/Case6/Case6_full_program.png)<P>


## Result
<HR>

When micro:bit is turned on, the LED matrix will show a “tick” icon to indicate that the initialization is complete. The micro:bit will then consistently collect weather information, and you can see the real-time data values directly on the micro:bit device.<BR><P>
![auto_fit](images/Case6/image1.gif)<P>
Additionally, by clicking the “Show console device” button in MakeCode, you can view more detailed data and instant graphs of temperature and raindrop values on your computer for better monitoring.<p>
![auto_fit](images/Case6/Case6_result2.png)<P>
## Think
<HR>

Q1. How can we monitor other sensor values (e.g., noise) using the Serial Monitor?<BR><P>
