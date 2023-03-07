# Adv IoT Case 14: Control Real Home Electronics

Level: ![level](images/level5.png)


## Goal
<HR>

Can use the Micro:bit to control the Real IoT electronics


## Background
<HR>

<span id="subtitle">What is an IOT electronics(Smart Plug/Bulb)?
</span><BR><P>
IoT electronics are a new generation of electronics, they integrate the concept of Internet of Things and have the ability to connect to the internet. Users can use different methods to control them, such as mobile apps, web service platforms, or other IoT devices. <BR><P>

<span id="subtitle">Control Real IoT electronics principle
</span><BR><P>
By using Webhooks extension on IFTTT platform, commands can be pre-set as trigger. When the micro:bit sending the command to IFTTT, the webhooks services in the applet will trigger the user’s preferences IoT electronics IFTTT service.<BR><P>

## IFTTT Platform Configuration

1. Login the IFTTT account<BR>
2. Create a new Applet <BR>
![pic_90](images/Case14/Case14_IFTTT_Config_1.png)<P>
3. Search and choose webhooks service<BR>
![pic_100](images/Case14/Case14_IFTTT_Config_2.png)<P>
4. Choose “Receive a web request”<BR>
![pic_90](images/Case14/Case14_IFTTT_Config_3.png)<P>
5. Input the command which used for micro:bit call later
![pic_90](images/Case14/Case14_IFTTT_Config_4.png)<P>
6. Choose the IFTTT service that is the IoT device you are using <BR>
![pic_90](images/Case14/Case14_IFTTT_Config_5.png)<P>
7. You may input the IoT electronics product name or brand name to search, for example: ewelink, philips hue<BR>
![pic_80](images/Case14/Case14_IFTTT_Config_6.png)<P>
8. Choose your target action<BR>
![pic_90](images/Case14/Case14_IFTTT_Config_7.png)<P>
9. For each command and action, you need to have one applet. If you need more sets of command and action, create more applets.<BR>
10. After finish applet setup, go to my service->webhooks<BR>
![pic_90](images/Case14/Case14_IFTTT_Config_8.png)<P>
11. Go to documentation <BR>
![pic_90](images/Case14/Case14_IFTTT_Config_9.png)<P>
12. Copy your key for micro:bit call later<BR>
![pic_90](images/Case14/Case14_IFTTT_Config_10.png)<P>

## Example 1: Remote Control Real Plug


### Part List
<HR>

![pic_90](images/Case14/Case14_ex1_Partlist_1.png)<P>

### How to install
<HR>

1. Install the plug <BR>
![pic_90](images/Case14/Case14_ex1_Install_1.png)<P>
2. Download the apps and config the plug connect to internet<BR>
![pic_90](images/Case14/Case14_ex1_Install_2.png)<P>

### Hardware connect
<HR>

1. Insert the micro:bit to iot:bit connect edge
![pic_90](images/Case14/Case14_ex1_connect.png)<P>

### Programming (MakeCode)
<HR>

<span id="subtitle">Step 1.</span><BR>
On Start, initialize the IoT:Bit and connect to WiFi<P>

![pic_90](images/Case14/Case14_ex1_programming_1.png)<P>


<span id="subtitle">Step 2. </span><BR>After WiFi connected, use “On WiFi connected” block to show a tick<P>

![pic_90](images/Case14/Case14_ex1_programming_2.png)<P>

<span id="subtitle">Step 3. 
</span><BR>Use button function block “on button X pressed” to receive the input action and trigger the following process<P>
<span id="subtitle">Step 4. 
</span><BR>Do it for both button A and button B<P>
<span id="subtitle">Step 5. 
</span><BR>For each button function block, put a “send IFTTT key ….” function inside<P>
<span id="subtitle">Step 6. </span><BR>Fill in the fields of key and event_name<P>
* Key: your webhooks key <BR>
* Event_name: the command that you set in the applet <BR>

![pic_90](images/Case14/Case14_ex1_programming_3.png)<P>

### Result
<HR>
press micro:bit A -> turn on plug<BR><P>


## Example 2: Motion control Real Light Bulb


### Part List
<HR>

![pic_90](images/Case14/Case14_ex1_Partlist_2.png)<P>

### How to install
<HR>

1. Install the philips hue bulb to socket or bridge <BR>
2. Config it to connect the internet <BR>
3. Go to IFTTT, search philips hue service and connect it.<BR>

### Hardware connect
<HR>

1. Connect motion sensor to P1
![pic_90](images/Case14/Case14_ex2_connect.png)<P>

### Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. </span><BR>On Start, initialize the IoT:Bit and connect to WiFi<P>

![pic_90](images/Case14/Case14_ex1_programming_1.png)<P>


<span id="subtitle">Step 2. </span><BR>After WiFi connected, use “On WiFi connected” block to show a tick<P>

![pic_90](images/Case14/Case14_ex1_programming_2.png)<P>

<span id="subtitle">Step 3. 
</span><BR>In the forever block, put a “if” statement with “wifi connected?” condition<P>
<span id="subtitle">Step 4. 
</span><BR>Put another “if-else” statement inside <P>
<span id="subtitle">Step 5.
</span><BR>For the if condition, use “Get motion (triggered or not) at Pin P1 = true” to detect the people movement<P>
<span id="subtitle">Step 6. 
</span><BR>Put the “Send IFTTT key …” block in the if statement, fill in the fields with the webhooks key and “open” command which is pre-set in the applet<P>
<span id="subtitle">Step 7. 
</span><BR>Add a pause 10 second to avoid it turn off so quick if not moving<P>
<span id="subtitle">Step 8. 
</span><BR>Put another “Send IFTTT key …” block at the else statement, fill in with same key but "close" command<P>

![pic_90](images/Case14/Case14_ex2_programming_3.png)<P>

### Result
<HR>
Walking in front of motion sensor –> the light turn on<P>

## More Idea
<HR>
You may take a review of previous case, and make use of the concept you was learnt to apply on the project that control real electronics, such as:  <P>

* Turn Case 03 Motor Fan to a real electronic fan with the smart plug<BR>

![pic_90](images/Case14/Case14_extra_1.png)<P>

* Turn Case 08 servo curtain to a real electronic IoT curtain <BR>

![pic_90](images/Case14/Case14_extra_2.png)<P>




