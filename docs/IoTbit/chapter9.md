# Chapter 9: Upload Data and Get Controlled by Blynk

Blynk is a powerful IoT (Internet of Things) platform that allows users to build and control connected devices with ease. It provides a user-friendly mobile and web dashboard that lets developers and hobbyists remotely monitor and manage microcontrollers, sensors, and actuators.<br>

![](images/Ch9/Ch9_1.png)<br>

## Session 1: Upload Data to Blynk

<span id="subtitle">Goal:<p>
Upload sensor values to Blynk and display them using Gauges on the Blynk platform.<br>

![](images/Ch9/Ch9_2.png)<br>

<span id="subtitle">Description:<p>
In this example, there are 2 parts involved.<br>
In Part 1, we will create a device on Blynk and obtain its token.<br>
In Part 2, we will program the micro:bit to send sensor values to Blynk.<br>

### Part 1: Blynk Configuration

<span id="subtitle">Goal:<p>
Create a device on Blynk and obtain its token.<br>

<span id="subtitle">Step 1: Create an Account<p>
1. Go to https://blynk.io/<br>
2. Register an account and log in to the platform according to the website's instructions.<br>

<span id="subtitle">Step 2: Create a Template<p>

1. Go to Developer Zone > My Templates, and click “+ New Template”.<br>
2. Input name, hardware and connection type accordingly. Click “Done” when finished.<br>
- Name: iotbit<br>
- Hardware: Other<br>
- Connection type: WiFi<br>

![](images/Ch9/Ch9_3_2.png)<br><br>

<span id="subtitle">Step 3: Configure the Datastream - Add V0<p>

1. Go to Datastreams, click “+ New Datastream” and select “Virtual Pin”.<br>
![](images/Ch9/Ch9_4_2.png)<br><br>

2. Change the configuration of the Pin accordingly. Click “Create” when finished.<br>
- Name: Sensor Value<br>
- Max: 100<br>
![](images/Ch9/Ch9_5_2.png)<br>

<span id="subtitle">Step 4: Configure the Web Dashboard<p>

1. Go to Web Dashboard.<br>
2. Drag a Gauge to the Dashboard area.<br>
3. Hover over the Gauge, click the button shown below to change its settings<br>
![](images/Ch9/Ch9_6_2.png)<br><br>

4. Choose Sensor Value (V0) as the Datastream. Click “Save” when finished.<br>
![](images/Ch9/Ch9_7_2.png)<br>

<span id="subtitle">Step 5: Disable Notification Upon Interaction<p>
Since the device will always be offline, a notification will be triggered with every interaction. By disabling this notification, we can prevent alerts about the offline status when interacting with the device.<br>
1. Go to Connection Lifecycle.<br>
2. Scroll down to Offline and click Settings.<br>
3. Disable “Display notification upon user interaction”.<br>
![](images/Ch9/Ch9_8_2.png)<br><br>

4. Click “Save” to save the entire template.<br>
![](images/Ch9/Ch9_32_1.png)<br><br>

<span id="subtitle">Step 6: Create a Device With the Template<p>

1. Go to Devices. Click “+ New Device”.<br>
![](images/Ch9/Ch9_9_2.png)<br><br>

2. Click “From template” and select the template we just created.<br>
3. Rename the device as “iotbit 1” at Device Name. Click “Create” when finished.<br>
![](images/Ch9/Ch9_10_2.png)<br><br>

4. Go to the Devices page and copy the token as shown below. Keep the copied token in a safe place for future use.<br>
![](images/Ch9/Ch9_11_2.png)<br>

<span id="subtitle">Step 7 (Optional): Configure the Mobile Dashboard<p>

1. Open the Blynk App and log in to your account.<br>
2. After logging in, you will find the device you just created on the page.<br>
3. Switch to Developer Mode by clicking the button at the top right-hand side.<br>
4. Click on the template you just created.<br>
5. Click “+” and choose “Gauge”. A Gauge will be shown on the dashboard automatically.<br>
6. Click the newly created Gauge and choose Sensor Value (v0) as its datastream.<br>
![](images/Ch9/Ch9_34_1.png)<br><br>

### Part 2: Programming (MakeCode)
<span id="subtitle">Goal:<p>

Program the micro:bit to send sensor values to Blynk.<br>

<span id="subtitle">Step 1: Connect to WiFi<p>

1. Initialize IoT:bit to connect to a designated WiFi network and display the connection status when successful. You may refer to the first chapter for instructions on how to connect to WiFi.<br>
2. Snap “initialize OLED with width 128 height 64” to “on start”.<br>
![](images/Ch9/Ch9_12.png)<br>

<span id="subtitle">Step 2: Send Data to Blynk<p>

For demonstration, a random number is sent to Blynk every 1 second.<br>
1. In “forever”, use if-statement to check WiFi connection status.<br>
2. Snap the “Send Blynk token.....” block inside the if-statement.<br>
3. Copy the token from Blynk and fill it into “Send Blynk token”.<br>
4. Snap “pick random 0 to 10” to V0 value inside “Send Blynk token”. Change the range to “0 to 100”.<br>
5. Snap a pause to the loop. Set the pause to be 1000 ms (1 second).<br>
![](images/Ch9/Ch9_13.png)<br>

<span id="subtitle">Step 3: Show Blynk Upload Status<p>
1. Get the “On Blynk Uploaded” handler from IoT:bit > IoT Services.<br>
2. Use OLED to display the upload status and error code.<br>
![](images/Ch9/Ch9_14.png)<br>

<span id="subtitle">Full Solution<p>

MakeCode: [https://makecode.microbit.org/_2v1FqMJebYJU](https://makecode.microbit.org/_2v1FqMJebYJU)<br>
<iframe src="https://makecode.microbit.org/_2v1FqMJebYJU" width="100%" height="500" frameborder="0"></iframe><P>

### Result

If the upload is successful, it will show OK as the status with error code 0.<br>
On Blynk, you will see the value of the Gauge keep changing randomly, which is controlled by the data sent from your Micro:bit.<br>
![](images/Ch9/Ch9_16.jpg)<br><br>
**<u>Web Dashboard:</u>**<br>
![](images/Ch9/Ch9_33_4.gif)<br><br>

**<u>Mobile Dashboard:</u>**<br>
![pic_40](images/Ch9/Ch9_35.gif)<br><br>

If the upload fails, it will show FAIL as the status with the respective error code which represents the reason of failure.<br>
- Error code 400: The user inputted the wrong token.<br>
- Error code -28674: There is no internet connection.<br>

![](images/Ch9/Ch9_18.jpg)

## Session 2: Get Controlled by Blynk

<span id="subtitle">Goal:<p>
Create a switch on Blynk to control the output of the micro:bit.
<br>

![](images/Ch9/Ch9_19.png)<br>

<span id="subtitle">Description:<P>

In this example, there are 2 parts involved. <br>
In Part 1, we will create a switch on Blynk and configure it to send data to the micro:bit. <br>
In Part 2, we will program the micro:bit to respond to input from Blynk. <br>

### Part 1: Blynk Configuration 

<span id="subtitle">Goal:<p>

Create a switch on Blynk and configure it to send data to the micro:bit.<br>

<span id="subtitle">Step 1: Use Existing Template<p>

We will continue to use the template created in section 9.1.1. Go to Developer Zone > My Templates. Choose the template we just created. <br>
![](images/Ch9/Ch9_20_2.png)<br><br>

Otherwise, create a new template following the first half chapter of step 1 and 2.<br>

<span id="subtitle">Step 2: Update the Datastream - Add V1<p>

1. Go to Datastreams and click “Edit”.<br>
2. Click “+ New Datastream” and select “Virtual Pin”.<br>
3. Change the name of the pin to “on_off switch”. Click “Create” when finished.<br>

![](images/Ch9/Ch9_21_2.png)<br>

<span id="subtitle">Step 3: Add a Switch to the Web Dashboard<p>

1. Go to Web Dashboard, drag a Switch to the Dashboard area.<br>
2. Hover over the Switch and go into its settings.<br>
![](images/Ch9/Ch9_22_2.png)<br><br>

3. Choose on_off switch (V1) as the Datastream. Click “Save” when finished.<br>
![](images/Ch9/Ch9_23_2.png)<br><br>

4. Click “Save And Apply” to save the entire template.<br>
![](images/Ch9/Ch9_24_1.png)<br><br>

<span id="subtitle">Step 4 (Optional): Configure the Mobile Dashboard<p>

1. Open the Blynk App.<br>
2. Switch to Developer Mode by clicking the button at the top right-hand side.<br>
3. Click on the template you just updated.<br>
4. Click “+” and choose “Switch”. A Switch will be shown on the dashboard automatically.<br>
5. Click the newly created Switch and choose on_off switch (v1) as its datastream.<br>

![](images/Ch9/Ch9_34_1.png)<br><br>


### Part 2: Programming (MakeCode)
<span id="subtitle">Goal:<p>

Program the micro:bit to respond to input from Blynk.<br>

<span id="subtitle">Step 1: Connect to WiFi<p>

1. Initialize IoT:bit to connect to a designated WiFi network. You may refer to the first chapter for instructions on how to connect to WiFi.<br>
2. Snap “initialize OLED with width 128 height 64” to “on start”.
![](images/Ch9/Ch9_25.png)<br>

<span id="subtitle">Step 2: Read Data from Blynk<p>

1. In “forever”, use if-statement to check WiFi connection status.<br>
2. Snap the “read Blynk token.....” block inside the if-statement.<br>
3. Copy the token from Blynk and fill it into “read Blynk token”.<br>
4. Choose V1 for “read Blynk token.....”.<br>
5. Snap a pause to the loop. Set the pause to be 1000 ms (1 second).<br>
![](images/Ch9/Ch9_26.png)<br>

<span id="subtitle">Step 3: Display the Data Read<p>

1. Get the “On Blynk Readed” handler from IoT:bit > IoT Services.<br>
2. Create a variable to store the value read from Blynk.<br>
3. Use OLED to display the read pin and its value.<br>
4. Show the respective icon according to the read data.<br>
![](images/Ch9/Ch9_27.png)<br>

<span id="subtitle">Full Solution<p>
MakeCode: [https://makecode.microbit.org/_CfDHut4T7Eif](https://makecode.microbit.org/_CfDHut4T7Eif)<br>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/_CfDHut4T7Eif" width="100%" height="500" frameborder="0"></iframe><P>

### Result

We can change the value of the read pin using the switch on Blynk to check if the micro:bit can correctly receive the data.<br>

1. When the Switch in on<br>
![](images/Ch9/Ch9_30.jpg)<br><br>

**<u>Web Dashboard:</u>**<br>
![](images/Ch9/Ch9_29.png)<br><br>
**<u>Mobile Dashboard:</u>**<br>
![](images/Ch9/Ch9_36_1.jpg)<br>


2. When the Switch is off<br>
![](images/Ch9/Ch9_32.jpg)<br><br>
**<u>Web Dashboard:</u>**<br>
![](images/Ch9/Ch9_31.png)<br><br>
**<u>Mobile Dashboard:</u>**<br>
![](images/Ch9/Ch9_37_1.jpg)<br>