# IoT Case 06: Environmental Anomaly Alert

![auto_fit](images/case06/image10.png)
## Goal
<HR>

Create  an email alert system that automatically notifies you when the environmental temperature falls outside the optimal range for plant growth.

## Background
<HR>

<b>What is an Environmental Anomaly Alert?</b><P>

An Environmental Anomaly Alert is a monitoring system designed to detect abnormal environmental conditions that may affect plant growth. It ensures that factors such as temperature and humidity remain within the ideal range for healthy plant development. When irregularities occur, the system notifies the user so that timely actions can be taken to restore optimal growing conditions.

<b>Environmental Anomaly Alert Operation</b>

The IoT board connects to a Wi-Fi network and uses a temperature and humidity sensor to monitor environmental conditions continuously. The current temperature readings are displayed on the OLED screen every 30 seconds. If the temperature stays outside the normal range for more than 25 cycles, the system triggers a signal to an IFTTT applet. This applet then sends an email notification to the user’s specified address and continues sending alerts until the temperature returns to the normal range.

![pic](images/case06/flowchart.png)


## Part List
<HR>

![auto_fit](images/Case6.jpg)<P>


## Assembly Steps

<span id="subtitle">Step 1</span><BR><P>
To start with, build the plant pot model with soil and seedling. Install the LCD Display during the build.<BR><P>
![pic](images/case06/image14.png)<P>


<span id="subtitle">Step 2</span><BR><P>
Connect the Module Stand with the Pot base.<BR><P>

![pic](images/case06/Step2.jpg)

![pic](images/case06/Step2a.png)

<span id="subtitle">Step 3</span><BR><P>
Connect the Temperature and Humidity Sensor and Digital Light Sensor with a 3-pin and 4-pin module wire, respectively. Install them on part C1.<BR><P>

![pic](images/case06/Step3.png)

<span id="subtitle">Step 4</span><BR><P>
Put the model onto the pot tray and plastic mat. Completed!<BR><P>

![pic](images/case06/Step4.jpg)

## Hardware Connection
<HR>

1. Connect Temperature and Humidity Sensor to P2.  
2. Connect LCD Display to I2C.

![pic](images/case06/image32.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1:Initialize OLED, LCD, IoT:bit and connect to WiFi</span><BR><P>

* Snap Initialize OLED with width:128, height: 64 to on start
* Snap Set Wi-Fi to ssid pwd from IoT:bit
* Enter your Wi-Fi name and password. Here we set smarthon as SSID and 12345678 as password
* Snap initialize LCD at I2C with connects and powers up the 16x2 LCD screen using the I2C communication protocol so it can display text.

![auto_fit](images/case06/1.png)

<span id="subtitle">Step 2: Show icon “tick”  and device ID after WiFi connection</span><BR><P>

* In On WiFi connected, put a show icon tick get notice after WiFi is connected
* Show string deviceID after show icon tick

![pic](images/case06/2.png)

<span id="subtitle">Step 3: Read the data, set variable and show the data</span><BR><P>

* In forever, put a if statement and use WiFi connect? as condition
* Read the data by read temperature & humidity sensor at pin P2
* Set the variable to get the value, which is temperature
* LCD show join Temp: temperature for temperature

![pic](images/case06/3.png)

<span id="subtitle">Step 4: Examine the light intensity value and reaction</span><BR><P>

* Snap a nested if statement under the LCD show
* Set temperature < 21 or temperature > 29 as the condition
* Set the variable counter and change counter by 1 under the condition
* Snap an if statement under the change counter
* Set counter >= 25 as condition
* Send the data to Thingspeak by Send Thingspeak key XXXX field1 value XXX ..., fill in the write API key from the Thingspeak channel and the values need to be upload
* If temperature in the range 21-29, set counter to 0
* Wait for 300 second to avoid upload too frequently by pause(ms) 300000, then start another Reading and uploading

![pic](images/case06/4.png)

<span id="subtitle">Step 5: Check Thingspeak upload status</span><BR><P>

* To check the uploading status, use On thingspeak Uploaded to get the uploading result
* Insert clear OLED display for better visual effect
* Use the Status and Error_code from block placeholder respectively to showing some text explanation
* show string join Thingseak: Status for Upload status
* show string join Error: Error_code for Error code if upload failed

![pic](images/case06/5.png)

MakeCode: [https://makecode.microbit.org/\_f1EWY3VVEF9T](https://makecode.microbit.org/_f1EWY3VVEF9T)   
![auto_fit](images/case06/image92.png)<P>

## IoT (IFTTT)
<HR>

1. Go to [https://ifttt.com](https://ifttt.com), register an account and login to the platform.

![auto_fit](images/case06/image57.png)

<P>
2. On the top right menu, click “Create”.

![auto_fit](images/case06/image61.png)

<P>
3. Create tigger by:  

* Select “This”.  

* Select Smarthon IoT (micro:bit).  

* Select “IoT:bit was triggered”.  

* Input IoT:bit’s device ID and Trigger Command “alert”.  

* Click “Create trigger”.

![auto_fit](images/case06/image82.png)

<P>
4. Create action by: 
 
* Select “That”.  

* Select Email.  

* Select “Send me an email”.  

* Input email Subject and Body.  

* Click “Create action”.

![auto_fit](images/case06/image134.png)

## Result
<HR>

![auto_fit](images/case06/case6_v3_reduce.gif)
<P>