# Case 03: Environmental Motor Fan

Level: ![level](images/level2.png)
![auto_fit](images/Case3/blank.png)<P>


## Goal
<HR>

Make an environmentally friendly automated motor fan by detecting the surrounding temperature.<BR><P>

## Background
<HR>

<span id="subtitle">What is smart motor fan?</span><P>
Smart motor fan is a fan that can adjust the power, turn on and off automatically to save electricity when not needed.<BR><P>

<span id="subtitle">Environmental motor fan principle</span><P>
The temperature and humidity sensor installed in the house will scan for surrounding conditions continuously. When the temperature is too low or at average, the fan will change the intensity to off or low. When the temperature is high the fan will adjust to max power.<BR><P>
![pic_70](images/Case3/blank.png)<P>

## Part List
<HR>

![pic](images/Case3/blank.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step1</span><P>
Use M4 screws and nuts to install the Temperature and Humidity sensor (DHT11) on the Wall<BR><P>
Use M4 screws and nuts to install the OLED display on the Wall<BR><P>
![pic](images/Case3/Case3_ass1.png)<P>
<span id="subtitle">Step 2</span><P>
Use M4 screws and nuts to install the motor module on the opposite Wall<BR><P>
![pic](images/Case3/Case3_ass2.png)<P>

## Hardware connect
<HR>

1. Connect the Temperature and Humidity sensor (DHT11) to P0
2. Connect the extended OLED display to I2C Port 
3. Connect the Motor module to P1
4. Pull up the Buzzer switch to disconnect the Buzzer

![pic](images/Case3/Case3_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED display</span><P>
* In `on start`, put `initialize OLED with width 128 height 64` to initialize the OLED display
![auto_fit](images/Case3/Case3_p1.png)<P>

<span id="subtitle">Step 2. Create variable</span><P>
* Create a variable called `temperature`
![pic_90](images/Case3/Case3_p2.png)<P>

<span id="subtitle">Step 3. Read and show the reading from DHT11</span><P>
* In `Forever`, put (set temperature to `DHT11 Read temperature at pin p0`)
* Before update the screen infomation, suggest clear up the OLED display each time
* Use `clear OLED display` to clear the display
* Then use `show string join Temp: temperature` to show the temperature value with formatted text on display
![pic_90](images/Case3/Case3_p3.png)<P>

<span id="subtitle">Step 4. Examine the temperature</span><P>
* In `Forever`, put a nested `if-else` statement
* Use the `temperature < 22` as first condition
* In the first `if` segment, turn off the fan by `Set Motor fan with speed 0 at P1`
* Use the `temperature < 26` as second condition
* In the second `if` segment, turn on the fan with half speed by `Set Motor fan with speed 600 at P1`
* Use the `temperature >= 26` as third condition
* In the third `if` segment, turn on the fan with full speed by `Set Motor fan with speed 1023 at P1`
![pic_90](images/Case3/Case3_p4.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_2fMJtCPdCP6L](https://makecode.microbit.org/_2fMJtCPdCP6L)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_2fMJtCPdCP6L" width="100%" height="500" frameborder="0"></iframe>


## Result
<HR>

When the room temperature changing, it will match either one of the condition, and the fans will turn on or off with different speed according to the room temperature.<BR><P>
![pic](images/Case3/Case3_result.gif)<P>

## Think
<HR>

Q1. Apart from open the fans, any other method to reduce the temperature?<BR><P>