# IoT Case 09:  Remote Water Pump Control

![auto_fit](images/case09/image203.png)

## Goal
<HR>

Use Blynk to create a mobile app for monitoring soil moisture levels and remotely controlling the water pump for irrigation. 

## Background
<HR>

<b>What is Blynk?</b><P>

Blynk is a platform designed for creating Internet of Things (IoT) applications, enabling users to connect and control hardware devices remotely. With Blynk, users can easily build mobile applications by utilizing a drag-and-drop interface to customize their app's design. Users can employ pre-built widgets to monitor sensors, control actuators and visualize data in real time. 

<b>Mobile App Soil Moisture Control Operation</b>

After setting up the model with the water pump and soil moisture sensor, it will connect to the internet and communicate with Blynk via a token. The soil moisture level measured by the sensor will be sent to Blynk, while Blynk will send the switch signal to the model for controlling the water pump.

## Part List
<HR>

![auto_fit](images/case09/case09-parts.png)<P>

<!-- ## Assembly Steps

1. To start with, build the plant pot model with soil and seedling. Install the LCD Display during the build.

![][image39]

2. Install parts D1 and D2.

![][image157]    ![][image158]

3. Connect the water pump with the pump tube.

![][image159]

4. Put the water pump into the pump cup, then insert the pump tube between D1 and D2 as shown in the picture.

![][image160]

5. Connect the soil moisture sensor with a 3-pin module wire and put it into the soil.

![][image161]

6. Put the model onto the pot tray and plastic mat. Completed\!

![][image162] -->

## Hardware Connection
<HR>

1. Connect Water Pump to P0.  
2. Connect Soil Moisture Sensor to P1.  
3. Connect LCD Display to I2C.

![auto_fit](images/case09/image55.png)<P>

## Programming (MakeCode)
<HR>

MakeCode: [https://makecode.microbit.org/\_gxY2b6FhcHmp](https://makecode.microbit.org/_gxY2b6FhcHmp)   
![auto_fit](images/case09/image56.png)<P>

## IoT (Blynk)

### Part 1: Setup Blynk
<HR>

1. Go to [https://www.blynk.io](https://www.blynk.io), register an account and login to the platform. 

![auto_fit](images/case09/image180.png)

<P>
2. On the left menu, click “Developer Zone” \> “New Template”.

![auto_fit](images/case09/image71.png)

<P>
3. Create a new template by:  

* Input name “Soil Moisture Control”.  

* Click “Done”.

![auto_fit](images/case09/image77.png)

<P>
4. On the left menu, click “Datastreams” \> “New Datastream” \> “Virtual Pin”.

![auto_fit](images/case09/image140.png)

<P>
5. Add the first Virtual Pin by:  

* Input name “Soil Moisture”.  

* Set Max to 100\.  

* Click “Create”.

![auto_fit](images/case09/image16.png)

<P>
6. Click “New Datastream” \> “Virtual Pin”. Add the second Virtual Pin by:  

* Input name “Water Pump Switch”.  

* Click “Create”.

![auto_fit](images/case09/image106.png)

<P>
7. On the left menu, click “Web Dashboard”. Add a Gauge for displaying detected soil moisture value by:  

* Drag a Gauge to the dashboard.  

* Hover over the added Gauge and click “...” \> Settings“.  

* Select Soil Moisture (V0).  

* Click “Save”.

![auto_fit](images/case09/image177.png)
![auto_fit](images/case09/image161.png)

<P>
8. Add a Switch for controlling water pump by:  

* Drag a Switch to the dashboard.  

* Hover over the added Switch and click “...” \> Settings“.  

* Select Water Pump Switch (V1).  

* Click “Save”.

![auto_fit](images/case09/image90.png)

<P>
9. Click “Save” to save the dashboard configuration.

![auto_fit](images/case09/image118.png)

<P>
10. On the left menu, click “Devices” \> “New Device” \> “From template”.

![auto_fit](images/case09/image133.png)

<P>
11. Create a device with the template by:  

* Select template “Soil Moisture Control”.  

* Click “Create”.

![auto_fit](images/case09/image47.png)

<P>
12. Copy the Auth Token of the device for programming. You may also find the Auth Token by clicking “Devices” on the left menu.

![auto_fit](images/case09/image105.png)

### Part 2: Install and Setup the Blynk App on Smartphone
<HR>

1. Go to Play Store or App Store to search and download the Blynk app.

![auto_fit](images/case09/image183.jpg)

<P>
2. Login to your Blynk account.

![auto_fit](images/case09/image213.jpg)

<P>
3. Click the device “Soil Moisture Control”.

![auto_fit](images/case09/image89.png)

<P>
4. Click the green button at the top to open the mobile dashboard edit page. Add a Gauge to display detected soil moisture value by:  

* Click the green button at the button to open the widget box.  

* Select Gauge.  

* Click the added Gauge to open its settings.  

* Select Soil Moisture \[v0\] for datastream.  

* Click the top left button to return to the edit page.

![auto_fit](images/case09/image148.png)
<P>
5. Add a Switch to control water pump by:  

* Click the green button at the button to open the widget box.  

* Select Switch.  

* Click the added Switch to open its settings.  

* Select Water Pump Switch \[v1\] for datastream.  

* Click the top left button to return to the edit page.

![auto_fit](images/case09/image193.png)

<P>
6. Click the top left button to close the dashboard edit page.

![auto_fit](images/case09/image65.png)<P>

## Result
<HR>

![auto_fit](images/case09/image101.jpg)<P>
![auto_fit](images/case09/image117.png)<P>
![auto_fit](images/case09/image164.jpg)
<P>