# Adv IoT Case 13: Smart Fan Voice Control

Level: ![level](images/level5.png)


## Goal
<HR>

Make a remotely controlled fan by using a voice assistant.


## Background
<HR>

<span id="subtitle">What is Smart Fan Voice Control?</span><BR><P>
It is a fan that is connected to the internet and can be woken up by voice command using a voice assistant. The user can define different voice commands to control fan in different speeds or modes. In this case, the user can turn on and off from the voice command.<BR><P>

<span id="subtitle">Smart Fan Voice Control Principle
</span><BR><P>
In the program, the micro:bit connects to WIFI and gets the device ID. By setting the received command (turn_on_fan and turn_off_fan), the motor will be turned on and off.<BR>
In the Smarthon IoT:bit extension on IFTTT platform, commands can be pre-set such that when a specific phrase is said to the corresponding voice assistant it will send the commands through the internet to the fan and trigger on or off actions.
<BR><P>
![pic](images/Case13/Case13_flowchart.png)<P>

<span id="subtitle">Know more: What is a Voice Assistant?</span><P>
An intelligent virtual assistant (IVA) or intelligent personal assistant (IPA) is a software agent that can perform tasks or services for an individual based on commands or questions. The term "chatbot" is sometimes used to refer to virtual assistants generally or specifically accessed by online chat. Common giant examples are Amazon Alexa, Google Home and Apple Siri.<P>
It is capable of voice interaction, music playback, making to-do lists, setting alarms, streaming podcasts, playing audiobooks, and providing weather, traffic, sports, and other real-time information, such as news. They can also control several smart devices using itself as a home automation system.<P>
Nowadays, to make a home smarter, <u>Amazon Echo Dot</u> or <u>Google Home</u> or <u>Apple home pod</u> is a central control device which contains a voice assistant inside at home so that the user can use the voice command to control different electronics easily.

![pic](images/Case13/Case13_iot_device.png)<P>


## Part List
<HR>

![pic_90](images/Case13/Case13_parts.png)<P>
 
## Assembly step
<HR>

<span id="subtitle">Step 1</span><BR><P>
In this case, build the “Big Style Model” as a home base.
<BR><P>
![pic_90](images/Case13/Case13_ass1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Insert the model E1 on model A, align with the holes on model A and B3.
<BR><P>
![pic_90](images/Case13/Case13_ass2.png)<P>

<span id="subtitle">Step 3</span><BR><P>
Attach the motor fan into the model F using M4 \* 10mm screws and nuts. And the connecting wire could be bended to the hole next to it.
<BR><P>
![pic_90](images/Case13/Case13_ass3.png)<P>

<span id="subtitle">Step 4</span><BR><P>
To build a fan stand, put model F into the model B3 and B4.
<BR><P>
![pic_90](images/Case13/Case13_ass4.png)<P>

<span id="subtitle">Step 5</span><BR><P>
To build a sofa model. Put the model K3 to the two sides of model K1.
<BR><P>
![pic_90](images/Case13/Case13_ass5.png)<P>

<span id="subtitle">Step 6</span><BR><P>
Put model K2 all together to the cardboard parts (K1-K3).
<BR><P>
![pic_90](images/Case13/Case13_ass6.png)<P>


<span id="subtitle">Step 7</span><BR><P>
The sofa completed~
<BR><P>
![pic_90](images/Case13/Case13_ass7.png)<P>

<span id="subtitle">Step 8</span><BR><P>
Place the sofa next to the fan.
<BR><P>
![pic_90](images/Case13/Case13_ass8.png)<P>

<span id="subtitle">Step 9</span><BR><P>
Place the decoration board (Model H) on model B3.
<BR><P>
![pic_90](images/Case13/Case13_ass9.png)<P>

<span id="subtitle">Step 10</span><BR><P>
Completed!
<BR><P>
![pic_90](images/Case13/Case13_ass10.png)<P>

<H3><u>Optional:</u></H3>
<span id="subtitle">Step 1</span><BR><P>
Place the Amazon Alexa/Google Nest Mini/Apple Homepod mini at the living room. In this case, we put Amazon Alexa here.
<BR><P>
![pic_90](images/Case13/Case13_ass_ex_1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Assembly Completed!
<BR><P>
![pic_90](images/Case13/Case13_ass_ex_2.png)<P>


## Hardware connect
<HR>

1. Connect the motor module to P1
![pic_80](images/Case13/Case13_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED, IoT:bit and connect to WiFi</span><BR><P>
* Snap `Initialize OLED with width:128, height: 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` from `IoT:bit` to `on start`
* Snap `Set Wi-Fi to ssid pwd` from `IoT:bit`
* Enter your Wi-Fi name and password. Here we set `smarthon` as `SSID` and `12345678` as `password`
![pic_60](images/Case13/Case13_p1.png)<P>

<span id="subtitle">Step 2. Show icon “tick” and Device ID after WiFi connection</span><BR><P>
* Snap `show icon` from `basic` to `On WiFi connected` and select icon `tick`
* Draw the `Device ID` variable from `On WiFi connected` to the `show string` block placeholder
![pic_50](images/Case13/Case13_p2.png)<P>

<span id="subtitle">Step 3. Receive Command</span><BR><P>
* Inside the `On WiFi Received`, show the command on OLED display
* Clear the display before each update by `Clear OLED display`
* Show the `WAN_Command` with text explanation by `show string join Command: WAN_Command`
![pic_50](images/Case13/Case13_p3.png)<P>

<span id="subtitle">Step 4. Action with command</span><BR><P>
* put a nested `if-else` statement with different conditions
* Set the first condition as `WAN_Command = turn_off_fan`
* In the `if` segment, turn off the fan by `set Motor fan with speed 0 at P1`
* In the second `if` condition, use `WAN_Command = turn_on_fan`
* In the second `if` segment, turn on the fan by `set Motor fan with speed 1023 at P1`

![pic_80](images/Case13/Case13_p4.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/S40911-39605-55147-37667](https://makecode.microbit.org/S40911-39605-55147-37667)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/S40911-39605-55147-37667" width="100%" height="500" frameborder="0"></iframe>


## IoT (Alexa, Cloud Control, IFTTT)
<HR>

### Part 1. Setup Amazon Alexa
1. Get the amazon alexa apps.<BR>
![pic_90](images/Case13/Case13_Alexa_1.png)<P>
2. Create Amazon Account (if not have amazon account) and login. <BR>
![pic_90](images/Case13/Case13_Alexa_2.png)<P>
3. Optional:<P>
Setup the alexa device and connect to the amazon account. <BR>

### Part 2. Setup IFTTT

1. Install IFTTT from Google Play Store. <BR>
![pic_100](images/Case13/Case13_Alexa_3.png)<P>
2. Open and login to IFTTT. <BR>
3. Press create to create the applet.<BR>
4. At the IF, search “alexa “ and choose “Amazon Alexa” and choose “Say a specific phrase.” <BR>
![pic_90](images/Case13/Case13_Alexa_4.png)<P>
5. It will detect the login account from Amazon Alexa app. Then, type the phrase here. For this example, we type “turn on the fan”.<BR>
![pic_90](images/Case13/Case13_Alexa_5.png)<P>
6. Click Add and type “smarthon iot” and choose Smarthon IoT as “then” service.<BR>
![pic_90](images/Case13/Case13_Alexa_6.png)<P>
7. In the service, choose “Control Command” and then fill in the Device ID, the command name that can read from the Micro:bit, and click “continue”, DONE!<BR>
![pic_90](images/Case13/Case13_Alexa_7.png)<P>


### Result
<HR>

1. Open the Amazon Alexa App, switch to the alexa account which connected to IFTTT. <BR>
2. Talk to alexa with “Trigger turn on the fan” by pressing the button in the right bottom corner.<BR>
![pic_100](images/Case13/Case13_Alexa_8.png)<P>
3. In the first time, it will ask you whether to turn on. Press turn on and say the phase. The phase should be trigger the IFTTT and send the command to Iot:bit.<BR>
![pic_90](images/Case13/Case13_Alexa_9.png)<P>
4. When say “Alexa trigger turn on the fan”, the fan will be turn on; When say “ Alexa trigger turn off the fan”, the fan will be turn off.<BR>
![pic_100](images/Case13/Case13_Alexa_10.png)<P>
5. Optional:<P>
You can connect the real device Amazon echo dot to the app so that you can do the voice control with a real voice controller.<BR>
![pic_100](images/Case13/Case13_Alexa_11.png)<P>


## IoT (Google Assistant)
<HR>

### Part 1. Setup Google Home and Google Assistant App

1. Install Google Home and Google Assistant app.<BR>
![pic_100](images/Case13/Case13_Google_1.png)<P>
2. Login with your google account.<BR>
3. Open the google home app, switch to your google account.<BR>
4. Press the settings button, choose “Works with Google”. <BR>
![pic_100](images/Case13/Case13_Google_2.png)<P>
5. Search and select IFTTT, provide authorize of Google to access the IFTTT service.<BR>
![pic_100](images/Case13/Case13_Google_3.png)<P>
6. After linked, the IFTTT will show on the list.<BR>
![pic_100](images/Case13/Case13_Google_4.png)<P>

### Part 2. Setup IFTTT

1. Install IFTTT from Google Play Store.
![pic_100](images/Case13/Case13_Google_5.png)<P>
2. Open and login to IFTTT.
3. Press create to create the applet.
4. At the IF, search “google assistant “ and choose “Google assistant V2”.
![pic_100](images/Case13/Case13_Google_6.png)<P>
5. In “Activate scene” input the phase for trigger the command. In this case, we input “fan on”.
![pic_100](images/Case13/Case13_Google_7.png)<P>
6. At the THEN, search “iot” and choose “Smarthon IoT (micro:bit)”.
![pic_100](images/Case13/Case13_Google_8.png)<P>
7. Press the “Control Command”, input the device ID of Iot:bit and the command “turn_on_fan”.
![pic_100](images/Case13/Case13_Google_9.png)<P>
8. Then click continue and finish button to save the applet.
![pic_90](images/Case13/Case13_Google_10.png)<P>

### Result

1. Open the <u>Google Home App</u> or <u>Google Assistant App</u>. Make sure the login google account is connected to IFTTT in the previous setup on Google Home App.
2. Say “Hey google, activate (your phase)” or press the button and say “activate (your phase)”.
![pic_100](images/Case13/Case13_Google_11.png)<P>
3. The phase should be trigger the IFTTT and send the command to Iot:bit.
![pic_90](images/Case13/Case13_Google_12.png)<P>
4. The fan will be turned on.
![pic_100](images/Case13/Case13_Google_13.png)<P>
5. (Optional): <P>
You can connect the real device <u>Google Nest Mini or Google Home</u> to the app so that you can do the voice control with a real voice controller.
![pic_100](images/Case13/Case13_Google_14.png)<P>

## IoT (Apple's Siri)
<HR>

### Part 1. Setup IFTTT
1. Install “IFTTT” App from Apple store. 
![pic_100](images/Case13/Case13_Apple_1.png)<P>
2. Open the APP, login into IFTTT. 
3. Tap “Create” to create an applet.
4. Click If This “Add” button. Select the “iOS Shortcuts” and click “Shortcut automation started”.
![pic_100](images/Case13/Case13_Apple_2.png)<P>
5. Click Then That “Add” button, search “Smarthon IoT” and select the “Smarthon IoT (mirco:bit)”.
![pic_100](images/Case13/Case13_Apple_3.png)<P>
6. Choose the “Control Command”, and fill in the Device ID, and the command name that can read from the Micro:bit, and click “Continue”, then save the applet.
![pic_100](images/Case13/Case13_Apple_4.png)<P>

### Part 2. Setup IOS ShortCut on Iphone
1. Open the Shortcuts app and tap the plus button ( + ) in the top right corner.
![pic_50](images/Case13/Case13_Apple_5.png)<P>
2. Tap Add Action > Apps > IFTTT.
![pic_100](images/Case13/Case13_Apple_6.png)<P>
3. Select Trigger Applet, Tap the blue arrow ( > ) next to 'Select an Applet', then tap Choose.
![pic_100](images/Case13/Case13_Apple_7.png)<P>
4. Select the Applet you'd like this Shortcut to run (please note that only Applets that use the iOS Shortcuts - Shortcut automation started trigger will appear in this list).
![pic_70](images/Case13/Case13_Apple_8.png)<P>
5. Name your Shortcut by tapping Trigger Applet at the top of the screen. This will be the custom phrase you will use to trigger your Applet.
![pic_100](images/Case13/Case13_Apple_9.png)<P>
6. Save the shortcut.
![pic_90](images/Case13/Case13_Apple_10.png)<P>

### Results
1. Click the shortcut or Hold the button on iphone. Say “turn on the fan” or “Siri turn on the fan”.
![pic_100](images/Case13/Case13_Apple_11.png)<P>
2. The applet will be triggered.
![pic_100](images/Case13/Case13_Apple_12.png)<P>
3. (Optional) <P>
You can connect the real device <u>Apple Homepod</u> to the <u>Apple Home App</u> so that you can do the voice control with a real voice controller.
![pic_100](images/Case13/Case13_Apple_13.png)<P>



## Think
<HR>

1. Apart from "Say a specific phrase” Alexa IFTTT trigger, any other Alexa trigger can use in case? <BR>
