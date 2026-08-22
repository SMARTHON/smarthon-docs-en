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

![pic](images/case02/flowchart.png)

<span id="subtitle">Know More: Why is Water Important for Plant Growth?</span><P>

Water provides the hydrogen ions needed in photosynthesis to convert sunlight into energy. It also dissolves minerals from the soil and transports them through the plant's vascular system (xylem) to different parts of the plant, supporting overall growth.

Additionally, water maintains turgor pressure in cells, keeping plants upright and enabling cell expansion. It also helps cool the plant and prevent overheating through transpiration, a process in which water evaporates from the leaves.

![alt="auto_fit"](images/case02/1.jpg)

## Part List
<HR>

![alt="auto_fit"](images/Case2.jpg)<P>

## Assembly Steps

<span id="subtitle">Step 1</span><BR><P>
To start with, build the plant pot model with soil and seedling.<BR><P>
![pic](images/case02/image14.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Assemble D1 with D3.<BR><P>
![pic](images/case02/Step2.png)

<span id="subtitle">Step 3</span><BR><P>
Assemble D2 with the above part.<BR><P>

![pic](images/case02/Step3a.png)

![pic](images/case02/Step3.png)

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

<span id="subtitle">Step 1. Program Startup</span><BR><P>
When the micro:bit powers on, it immediately configures the LCD display:

* Initialize Display: `initialize LCD at I2C` with connects and powers up the 16x2 LCD screen using the I2C communication protocol so it can output text.

![pic](images/case02/1.png)

<span id="subtitle">Step 2: Reading Soil Moisture (forever loop)</span><BR><P>
When the micro:bit powers on, it immediately configures the LCD display:

* Read Sensor: `set soilMoisture to soil moisture(0~100) at pin P1` with reads the analog signal from the soil moisture sensor connected to pin `P1` ,converts the reading into a percentage scale from 0 (completely dry) to `100` (completely wet) and stores this value inside the variable `soilMoisture`.

![pic](images/case02/2.png)

<span id="subtitle">Step 3: Updating the Display (forever loop)
</span><BR><P>
The micro:bit shows the live moisture reading on the screen::

* Show Moisture: `LCD show join "Soil Moisture:" soilMoisture at position 1 with length 16`
* Combines the text label `"Soil Moisture:"` with the live number saved in `soilMoisture`.
* Displays the combined text starting at `position 1` across a `length of 16 characters` on the screen.

![pic](images/case02/3.png)

<span id="subtitle">Step 4: Automatic Watering Condition (forever loop)
</span><BR><P>
The micro:bit evaluates whether the soil is dry and needs water:

* Check Moisture: `if soilMoisture < 50, then`
* Turn Pump On with `set water pump to intensity 1023 at P2 for 2 sec`
* If the moisture is below 50, it activates the water pump connected to `pin P2`.
* Sets the motor power to maximum speed `(intensity 1023)`.
* Keeps the pump running for `2 seconds` to water the plant.

![pic](images/case02/4.png)

<span id="subtitle">Step 5: Loop Delay (forever loop)</span><BR><P>
The micro:bit pauses briefly before taking the next reading:

* Snap pause (ms) 1000

![pic](images/case02/5.png)

MakeCode: [https://makecode.microbit.org/_gDiRMXKwzXaf](https://makecode.microbit.org/_gDiRMXKwzXaf)   
![pic](images/case02/image1.png)<P>


<H3><u>Advanced Usage: Pump water once every day</u></H3>

<span id="subtitle">Step 1: Hour Tracking Clock (first forever loop)
</span><BR><P>
A dedicated background loop keeps track of time throughout the day:

* 1-Hour Delay: `pause (ms) 3600000`with Delays for 3,600,000 milliseconds (exactly 1 hour).
* Increment Hour: `change hour by 1`with Adds 1 to the hour counter every hour.
* Midnight Reset: `if hour = 24 then set hour to 0`with Resets the clock to 0 (midnight) after reaching 24 hours.

![pic](images/case02/6.png)

<span id="subtitle">Step 2: Daily Watering Logic (second forever loop)
</span><BR><P>
The system checks once per day at 8:00 AM if the soil needs water:

* Add the Time Check: `if hour = 8 then` with Checks if the current time is `8:00 AM (hour = 8)`
* Moisture Check: `if soilMoisture < 50 then` with Checks if the soil moisture level is below `50%`.
* Turn Pump ON: `set water pump to intensity 1023 at P2 for 2 sec with` If it is 8:00 AM and the soil is dry `(< 50)`, it activates the water pump connected to pin` P2` , Sets the motor power to maximum speed `(intensity 1023)` and Keeps the pump running for 2 seconds to water the plant.
* Pause Execution: `pause (ms) 1000` with delays for 1000 milliseconds (1 second) before restarting the loop.

![pic](images/case02/8.png)

If every day at 8 am, it will check whether soil moisture sensor is low. If low, will pump water.
![pic](images/case02/image15.png)<P>
MakeCode: [https://makecode.microbit.org/_XXWT91M2vddr](https://makecode.microbit.org/_XXWT91M2vddr) 


## Result
<HR>

![auto_fit](images/case02/case2_pointing_v5_reduce.gif)

## Think
<HR>
Q1. Why do you think we need to set a pause for the water pump function? Is it because of the plant or programming?
<P>