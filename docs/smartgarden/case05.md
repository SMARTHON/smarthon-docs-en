# IoT Case 05: Garden Environment Data Monitoring

![pic](images/case05/image125.jpg)

## Goal
<HR>

Create a plant health monitoring system that will track the environment's humidity, temperature, light intensity and the plant’s soil moisture. The data is then sent and stored in thingspeak where it can be remotely monitored and analyzed over long periods of time. 


## Background
<HR>

<b>What is Plant Health Data Monitoring?</b><P>

Monitoring plant data is immensely important. However, if you will only monitor the immediate data you risk not seeing the bigger picture. If you have the habit of measuring and recording plant data over long periods of time it can show you patterns that you could have easily missed. Maybe there is a consistent overtime degradation of the plant health that is not noticeable in day-to-day life. Or there is a sudden growth spurt and you want to study what caused it. Moreover, if you implement a system that will categorize and sort the data automatically into easy to analyze graphs, it can greatly increase your efficiency as a botanist as well as save you enormous amounts of time. 

<b>Plant Health Data Monitoring Operation</b>

The pot is mounted with three modules: temperature and humidity sensor, soil moisture sensor, light intensity sensor. The board attempts to connect to the internet, and if it is connected successfully the sensor readings are sent to thingspeak. Afterwards there is a 15 second break. After the break, the cycle repeats.

![pic](images/case05/flowchart.png)

## Part List
<HR>

![alt="auto_fit"](images/Case5.jpg)<P>

## Assembly Steps

<span id="subtitle">Step 1</span><BR><P>
To start with, build the plant pot model with soil and seedling. Install the LCD Display during the build.<BR><P>
![pic](images/case04/image14.png)<P>


<span id="subtitle">Step 2</span><BR><P>
Connect the Module Stand with the Pot base.<BR><P>

![pic](images/case04/Step2a.png)

![pic](images/case05/Step2.jpg)

<span id="subtitle">Step 3</span><BR><P>
Connect the Temperature and Humidity Sensor and Digital Light Sensor with a 3-pin and 4-pin module wire, respectively. Install them on part C1, with the Digital Light Sensor above and the Temperature Humidity Sensor below the part.<BR><P>

![pic](images/case05/Step3.png)

![pic](images/case05/Step3a.jpg)

<span id="subtitle">Step 4</span><BR><P>
Connect the soil moisture sensor with a 3-pin module wire and put it into the soil.<BR><P>

![pic](images/case05/Step4.jpg)

<span id="subtitle">Step 5</span><BR><P>
 Put the model onto the pot tray and plastic mat. Completed!<BR><P>

![pic](images/case05/Step5.jpg)

## Hardware Connection
<HR>

1. Connect Temperature and Humidity Sensor to P1.  
2. Connect Soil Moisture Sensor to P2.  
3. Connect LCD Display to I2C.  
4. Connect Digital Light Sensor to I2C.

![pic](images/case05/image43.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1:Initialize OLED, LCD, IoT:bit and connect to WiFi</span><BR><P>

* Snap Initialize OLED with width:128, height: 64 to on start
* Snap initialize LCD at I2C with connects and powers up the 16x2 LCD screen using the I2C communication protocol so it can display text.
* Snap Set Wi-Fi to ssid pwd from IoT:bit
* Enter your Wi-Fi name and password. Here we set smarthon as SSID and 12345678 as password

![pic](images/case05/1.png)

<span id="subtitle">Step 2: Read the data and set variable</span><BR><P>

* In forever, put a if statement and use WiFi connect? as condition
* Read the data by read temperature & humidity sensor at pin P0
* Set four variables to get the value, which are temperature, humidity, soilMoisture and lightIntensity

![pic](images/case05/2.png)

<span id="subtitle">Step 3: Show the data on LCD at different position</span><BR><P>

* Show the four variables respectively, with some text explanation
* LCD show join Temp: temperature for temperature
* LCD show join Humd: humidity for humidity
* LCD show join Soil: soilMoisture for soil moisture
* LCD show join Ligt: lightIntensity for light intensity

![pic](images/case05/3.png)

<span id="subtitle">Step 4: Upload to ThinkSpeak</span><BR><P>

* Send the data to Thingspeak by Send Thingspeak key XXXX field1 value XXX ..., fill in the write API key from the Thingspeak channel and the values need to be upload
* After uploading the data to Thingspeak, wait for 15 second to avoid upload too frequently by pause(ms) 15000, then start another Reading and uploading

![pic](images/case05/4.png)

MakeCode: [https://makecode.microbit.org/_LzThHDRXg3HC](https://makecode.microbit.org/_LzThHDRXg3HC)  
![pic](images/case05/image69.png)<P>

## IoT (ThingSpeak)
<HR>

1. Go to https://thingspeak.com, Choose Channels \-\> My Channels \-\> New Channel<P>

![pic](images/case05/image144.png)

<P>
2. Input Channel name, Field 1-4, then click “Save Channel”  

* Channel name: Smart Garden Monitoring  

* Field 1: temperature  

* Field 2: humidity  

* Field 3: soil moisture  

* Field 4: light intensity

<P>
3. Select your channel \> “API Keys”, copy the API key as follows:

![pic](images/case05/image187.png)

## Result
<HR>

![pic](images/case05/case5_pointing_v3.gif)<P>
