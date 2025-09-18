# IoT Case 11: Kitchen Safety Flame Monitoring Alert

Level: ![level](images/level4.png)
![auto_fit](images/Case11/intro.png)<P>

## Goal
<HR>

Make a flame monitoring alert system by detecting the existence of strong fire nearby.

## Background
<HR>

Nowadays, fire accidents always happen when the homeowner is sleeping or outside the home. It is good to install an IOT system in the kitchen or living room to alert the user on his/her phone when he/she is sleeping or in the office so that he/she will wake up and rush out from the home to prevent a terrible accident happened. 

<BR><P>
<span id="subtitle">Kitchen Safety Flame Monitoring Alert Principle</span><BR><P>
By installing a flame sensor in the area, the system will trigger an alarm and blink the red LED to alert the home owner inside the home when there is fire detected. At the same time, it will send a IFTTT notification to the house owner's phone so that can alert user when he/she is sleeping or outside the home.
<BR><P>


![pic](images/Case11/Case11_flowchart.png)<P>

## Part List
<HR>

![pic_90](images/Case11/Case11_parts.png)<P>
 
## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
In this case, build the “Big Style Model” as a home base.<BR><P>
![pic_90](images/Case11/Case11_ass1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
To build a kitchen, put model E3 & E1 onto model A, align with holes at model A and B2 & B1.
<BR><P>
![pic_90](images/Case11/Case11_ass2.png)<P>

<span id="subtitle">Step 3</span><BR><P>
Attached the flame sensor to the model B2 using M4\*10mm screws and nuts. And the connecting wire should be bended to the hole nearby.
<BR><P>

![pic_90](images/Case11/Case11_ass3.png)<P>

<span id="subtitle">Step 4</span><BR><P>
Attached multi-color LED to the model B2 using M4\*10mm screws and nuts. And the connecting wire should be bended to the hole below.
<BR><P>

![pic_90](images/Case11/Case11_ass4.png)<P>

<span id="subtitle">Step 5</span><BR><P>
To build a stove model. Put the model L2 to model L1 from the top to bottom.<BR><P>

![pic_90](images/Case11/Case11_ass5.png)<P>

<span id="subtitle">Step 6</span><BR><P>
Fold the model L1 into the model L2 according to the arrow.<BR><P>

![pic_90](images/Case11/Case11_ass6.png)<P>

<span id="subtitle">Step 7</span><BR><P>
Fold the another side of model L1 into the model L2 according to the arrow.
<BR><P>

![pic_90](images/Case11/Case11_ass7.png)<P>

<span id="subtitle">Step 8</span><BR><P>
Stick the paper with a cooking stove pattern.<BR><P>

![pic_90](images/Case11/Case11_ass8.png)<P>

<span id="subtitle">Step 9</span><BR><P>
The cooking stove Completed!<BR><P>

![pic_90](images/Case11/Case11_ass9.png)<P>


<span id="subtitle">Step 10</span><BR><P>
Place the cooking stove model at the kitchen.<BR><P>

![pic_90](images/Case11/Case11_ass10.png)<P>

<span id="subtitle">Step 11</span><BR><P>
To build a fridge, attach light sensor onto model G1 using M4 \* 10mm screws and nuts. And the connecting wire could be bended to the hole below it.<BR><P>

![pic_90](images/Case11/Case11_ass11.png)<P>

<span id="subtitle">Step 12</span><BR><P>
Fold and bend the Model G1 accordinglyand put Model G3 into the Model G1, align with the holes.
<BR><P>

![pic_90](images/Case11/Case11_ass12.png)<P>

<span id="subtitle">Step 13</span><BR><P>
Put Model G2 onto the Model G1, align with the holes.
<BR><P>

![pic_90](images/Case11/Case11_ass13.png)<P>

<span id="subtitle">Step 14</span><BR><P>
The fridge completed!<BR><P>

![pic_90](images/Case11/Case11_ass14.png)<P>

<span id="subtitle">Step 15</span><BR><P>
Place the fridge model at the coner of the kitchen.<BR><P>

![pic_90](images/Case11/Case11_ass15.png)<P>

<span id="subtitle">Step 16</span><BR><P>
The fridge Completed!<BR><P>

![pic_90](images/Case11/Case11_ass16.png)<P>



## Hardware connect
<HR>

1. Connect the flame sensor to P2
2. Connect the Multi-Color LED to P1
3. Pull down the buzzer switch to connect buzzer

![pic_80](images/Case11/Case11_hardware.png)<P>


## Programming (MakeCode)
<HR>




<span id="subtitle">Step 1. Initialize OLED, IoT:bit and connect to WiFi, create variable</span><BR><P>
* Snap `Initialize OLED with width:128, height: 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` from `IoT:bit` to `on start`
* Snap `Set Wi-Fi to ssid pwd` from `IoT:bit`
* Enter your Wi-Fi name and password. Here we set `smarthon` as `SSID` and `12345678` as `password`
* Snap `Set strip to NeoPixel at pin P1 with 1 leds as RGB(GRB format)`
![pic_60](images/Case11/Case11_p1.png)<P>

<span id="subtitle">Step 2. Show icon “tick” and Device ID after WiFi connection</span><BR><P>
* Snap `show icon` from `basic` to `On WiFi connected` and select icon `tick`
* Draw the `Device ID` variable from `On WiFi connected` to the `show string` block placeholder
![pic_50](images/Case11-Fix/Case11-Fix_p1.png)<P>

<span id="subtitle">Step 3. Check the internet connection status</span><BR><P>
* In the `Forever`, put a `if` statement with condition `WiFi connected?` to check the connection status
![pic_50](images/Case11/Case11_p3.png)<P>

<span id="subtitle">Step 4. Check the flame sensor result and action on OLED display</span><BR><P>
* Put another `if` statement with condition `Get flame detection at Pin P2 = true` to recognize the flame 
* Play a warning sound when the flame was detected 
![pic_70](images/Case11/Case11_p4.png)<P>

<span id="subtitle">Step 5. Action on Warning LED</span><BR><P>
* The LED should be blinking to telling dangerous 
* Put `strip show color red` to turn on the LED in red color
* Add a `pause (ms) 100` to wait for 0.1 second
* Put `strip show color black` to turn off the LED
* Pause for 0.1 second again
![auto_fit](images/Case11/Case11_p5.png)<P>

<span id="subtitle">Step 6. Action on IFTTT</span><BR><P>
* Put a `Send IFTTT event_name* XXXXX` to send the event to IFTTT
* Fill in the Applet's `event_name`
![pic_50](images/Case11-Fix/Case11-Fix_p2.png)<P>

<span id="subtitle">Step 7. Know the Upload result</span><BR><P>
* To check the upload state, use the `On IFTTT Uploaded` to get the sending result
* Inside the `On IFTTT Uploaded`, use OLED display to show the information
* Clear the OLED display before each update by `clear OLED display`
* Show upload state by `show string join IFTTT: Status`, the `Status` value is from the function's placeholder
* Show error_code by `show string join Error: Error_code`, the `Error_code` value is from the function's placeholder
![pic_50](images/Case11/Case11_p7.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/S90038-27905-10105-17023](https://makecode.microbit.org/S90038-27905-10105-17023)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/S90038-27905-10105-17023" width="100%" height="500" frameborder="0"></iframe>

## IoT (IFTTT)
<HR>

### Part 1: Setup IFTTT

<span id="subtitle" >Step 1</span><BR><P>
Go to [http://www.ifttt.com](http://www.ifttt.com), register an account and login to the platform<BR><P>
![auto_fit](images/Case11-Fix/Case11-Fix_p6.png)<P>
<span id="subtitle" >Step 2</span><BR><P>
On the top right menu, click “Create” > “Applets”<BR><P>
![auto_fit](images/Case11-Fix/Case11-Fix_p7.png)<P>
<span id="subtitle" >Step 3</span><BR><P>
* Select this 
* Select Smarthon IoT
* Input Device ID and Event Name. (eg. Device ID: 0x55a842e3477a, Event Name: Fire)
* Click “Create trigger” <BR><P>
![auto_fit](images/Case11-Fix/Case11-Fix_p3.png)<P>
<span id="subtitle" >Step 4</span><BR><P>
* Select “That”
* Notifications 
* Send a notification from the IFTTT app 
* Message (eg. There is a fire in the house!), the click “Create action”
![auto_fit](images/Case11-Fix/Case11-Fix_p4.png)<P> <BR>

<span id="subtitle" >Optional: Use email as notification method</span><BR><P>
In the THEN field, search for the “email” and use it to replace the “notifications” in previous step
![pic_100](images/Case11-Fix/Case11-Fix_p5.png)<P><BR>



### Part 2: Install the IFTTT App on smartphone
1. Go to <U>play store</U> or <U>app store</U> to search and download the IFTTT App
![auto_fit](images/Case11/Case11_iot11.png)<P>
2. Login to your IFTTT account
![auto_fit](images/Case11/Case11_iot12.png)<P>


## Result
<HR>

When the flame source is detected by the flame sensor, it will trigger to blink the LED, making alert sound, and send the warning notification to IFTTT
<BR><P>
![auto_fit](images/Case11/Case11_result.gif)<P>
![auto_fit](images/Case11/Case11_result2.png)<P>

## Think
<HR>

1. Other than warning, any task we can do when we detect the flame? (e.g add a fan or sprinkler to extinguish the fire, call the police?)
<BR><P>
