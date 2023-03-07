# IoT Case 10: Home Health Data Monitoring

Level: ![level](images/level4.png)
![auto_fit](images/Case10/intro.png)<P>

## Goal
<HR>

Make a home health data monitoring system by collecting data from the sensors inside the house. Also use the temperature and humidity value to calculate the IAQ Score as reference.<BR><P>

## Background
<HR>

<span id="subtitle">What is home health data monitoring system?</span><BR><P>
Health monitoring is the concept of tracking the conditions of different parameters inside the user’s house. For indoor, the important parameters to analyze the home comfortability are temperature, humidity, pm2.5, CO2 and VOC. In this system, we can base on temperature and humidity to measure the comfortability of the home. With the too high temperature or too low humidity will also affect the comfortability.<BR><P>

<span id="subtitle">Home health monitoring system Principle</span><BR><P>
In this case, integrated temperature and humidity sensor DHT11 is used. It will keep track of room temperature, humidity and IAQ value, display to the OLED and upload to the Thingspeak platform for further analysis.<BR><P>


![pic](images/Case10/Case10_flowchart.png)<P>

<span id="subtitle">Know more: What is an IAQ?</span><P>
Indoor Air Quality (IAQ) refers to the air quality within and around buildings and structures, especially as it relates to the health and comfort of building occupants. Understanding and controlling common pollutants indoors can help reduce your risk of indoor health concerns. The important parameters are temperature, humidity, pm2.5, CO2 and VOC.

<span id="subtitle">Know more: How to determine the IAQ Score?</span><P>
In Smarthon Smart Home IoT Maker Kit, we use 2 parameters (temperature and humidity) to determine the comfortability (IAQ Score) of the room. Below is the chart to show most comfortable value of temperature (20-22) with humidity (40-70). 
![auto_fit](images/Case10/Case10_iaq_chart.jpg)<P>
Therefore, better range of temperature will have higher score of IAQ; Better range of humidity will have higher score of IAQ.
Thus, the average value of IAQ score from temperature and humidity can determine the comfortability of the room. In other words, for the used of block on pxt from Smarthon, it will return the average value of temperature and humidity IAQ score.

## Part List
<HR>

![pic_90](images/Case10/Case10_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
In this case, “Open Style Model” is used as a home base to start with.
<P>

![pic_90](images/Case10/Case10_ass1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Put the model E4 & E1 onto model A, align with holes at model A, B2 and B3.
<P>

![pic_90](images/Case10/Case10_ass2.png)<P>

<span id="subtitle">Step 3</span><BR><P>
Attach the OLED display onto model E4 using M4 * 10mm screws and nuts.<P>

![pic_90](images/Case10/Case10_ass3.png)<P>


<span id="subtitle">Step 4</span><BR><P>
Attach the DHT11 temperature and humidity sensor onto model E4 using M2 * 10mm screws and nuts. And the connecting wire should be bended to the hole below it.<P>

![pic_80](images/Case10/Case10_ass4.png)<P>


<span id="subtitle">Step 5</span><BR><P>
To build a sofa model. Put the model K3 to the two sides of model K1.<P>

![pic_80](images/Case10/Case10_ass5.png)<P>


<span id="subtitle">Step 6</span><BR><P>
Put model K2 all together to the cardboard parts (K1-K3).<P>

![pic_80](images/Case10/Case10_ass6.png)<P>

<span id="subtitle">Step 7</span><BR><P>
Plase the sofa model behind the model E4.<P>

![pic_80](images/Case10/Case10_ass7.png)<P>

<span id="subtitle">Step 8</span><BR><P>
Assembly Completed!<P>

![pic_80](images/Case10/Case10_ass8.png)<P>


## Hardware connect
<HR>

1. Connect the temperature and humidity sensor DHT11 to P0
2. Pull up the buzzer switch to disconnect the buzzer
3. Connect the OLED display to IoT:bit I2C port with extend cable


![pic_80](images/Case10/Case10_hardware.png)<P>

## IoT (Thingspeak)
<HR>

<span id="subtitle">Step 1. Create Thingspeak channel</span><BR><P>
* Go the [Thingspeak](https://thingspeak.com) create an account and create a channel
![pic_90](images/Case10/Case10_p1.png)<P>

<span id="subtitle">Step 2. Get channel API</span><BR><P>
* After created a new channel, get the write in API
![pic_90](images/Case10/Case10_p2.png)<P>


## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED, IoT:bit and connect to WiFi, create and initialize variables</span><BR><P>

* Snap `Initialize OLED with width:128, height: 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` from `IoT:bit` to `on start`
* Snap `Set WiFi to ssid smarthon pwd 12345678` to `on start`
* Create and initialize the variables `temperature`, `humidity` and `iaq_score` to `0`
![auto_fit](images/Case10/Case10_p3.png)<P>

<span id="subtitle">Step 2. Show icon “tick” after WiFi connection</span><BR><P>
* In `On WiFi connected`, put a `show icon tick` get notice after WiFi is connected.
![pic_60](images/Case10/Case10_p4.png)<P>

<span id="subtitle">Step 3. Create the function `check_condtion`</span><BR><P>
* Create a new function `check_condition`
* Put nested `if-else` statement inside the function
* The first condition is `iaq_score < 20`, then `show string Very uncomfortable` in the segment
* The second condition is `iaq_score < 40`, then `show string Uncomfortable` in the segment
* The third condition is `iaq_score < 60`, then `show string Discomfortable` in the segment
* The fourth condition is `iaq_score < 80`, then `show string Comfortable` in the segment
* The fifth condition is `iaq_score <= 100`, then `show string Very comfortable` in the segment

![pic_80](images/Case10/Case10_p5.png)<P>

<span id="subtitle">Step 4. Read the Temperature and Humidity sensor data</span><BR><P>
* In `Forever`, put a `if` statement with condition `WiFi connected?` to make sure connected to interent before uploading to thingspeak
* Use `Read Temperature & Humidity sensor at pin P0` to read the data from DHT11 Temperature and Humidity Sensor
* After read the DHT11 data, use the three functions to get the result and set to the variable
1. `Set temperature to Get Temperature °C` for temperature
2. `Set humidity to Get Humidity ` for humidity
3. `Set iaq_score to Get IAQ Score` for iaq_score
![auto_fit](images/Case10/Case10_p6.png)<P>

<span id="subtitle">Step 4. Show the data on display</span><BR><P>
* Clear the display before each times update by `clear OLED display`
* Show the three variables respectively, with some text explanation 
1. `show string join Temperature: temperature` for temperature
2. `show string join Humidity: humidity %` for humidity
3. `show string Join IAQ Score: iaq_score` for iaq_score
![auto_fit](images/Case10/Case10_p7.png)<P>

<span id="subtitle">Step 5. Analyst the environment status</span><BR><P>
* Run the `check_condition` function to summarize the IAQ Score result

![auto_fit](images/Case10/Case10_p8.png)<P>

<span id="subtitle">Step 6. Upload to Thingspeak</span><BR><P>
* Send the data to Thingspeak by `Send Thingspeak key XXXX field1 value XXX ...`, fill in the `write API key` from the Thingspeak channel and the `values` need to be upload
* After uploading the data to Thingspeak, wait for 15 second to avoid upload too frequently by `pause(ms) 15000`, then start another Reading and uploading.

![auto_fit](images/Case10/Case10_p9.png)<P>


<span id="subtitle">Step 7. Check Thingspeak upload status</span><BR><P>
* To check the uploading status, use `On thingspeak Uploaded` to get the uploading result
* `Insert newline` for better visual effect
* Use the `Status` and `Error_code` from block placeholder respectively to showing some text explanation
1. `show string join Thingseak: Status` for Upload status
2. `show string join Error: Error_code` for Error code if upload failed

![auto_fit](images/Case10/Case10_p10.png)<P>


<span id="subtitle">Full Solution<BR><P>

MakeCode: [https://makecode.microbit.org/_Vw1ebpiE2CsR](https://makecode.microbit.org/v4#editor:_Vw1ebpiE2CsR)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/v4#pub:_Vw1ebpiE2CsR" width="100%" height="500" frameborder="0"></iframe>





## Result
<HR>

The OLED show the temperature, humidity, IAQ Score and the environment condition based on IAQ Score. After upload, show the uploading information
<P>

![auto_fit](images/Case10/Case10_result.gif)<P>


## Think
<HR>

1. Apart from temperature and humidity, what elements do you think are essential to be included in a home health monitoring system? (E.G CO2 level? PM2.5 value?)
2. What function do you think the system can also include if it is to be used in a real home? (E.G Alert when the condition is too bad for health?)
