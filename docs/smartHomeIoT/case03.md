# Case 03: Environmental Motor Fan

Level: ![level](images/level2.png)
![auto_fit](images/Case3/intro.png)<P>


## Goal
<HR>

Make an environmentally friendly automated motor fan by detecting the surrounding temperature.<BR><P>

## Background
<HR>

<span id="subtitle">What is an Environmental Motor Fan??</span><P>
Smart motor fan is a fan that can adjust the power, turn on and off automatically to save electricity when not needed. Nowadays, for example, the temperature in the room is very low and cold, the air-conditioner also keeps turned on at high intensity. If there is a temperature sensor to detect surrounding parameters and change the power automatically, it can save much energy.<BR><P>

<span id="subtitle">Environmental Motor Fan Principle</span><P>
The temperature and humidity sensor installed in the house will scan for surrounding conditions continuously. When the temperature is too low or at average, the fan will change the intensity to off or low. When the temperature is high the fan will adjust to max power.<BR><P>

![pic_90](images/Case3/Case3_flowchart.png)<P>


## Part List
<HR>

![pic_90](images/Case3/Case3_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step1</span><P>
To start with, build the Big House Model. <BR><P>
![pic_90](images/Case3/Case3_ass1.png)<P>
<span id="subtitle">Step 2</span><P>
To build a small living room at the right side in the home, put Model E4 onto A model as a wall.
<BR><P>
![pic](images/Case3/Case3_ass2.png)<P>
<span id="subtitle">Step 3</span><P>
Attach the Temperature and humidity sensor to Model E4 using M4 * 10mm screws and nuts.
<BR><P>
![pic](images/Case3/Case3_ass3.png)<P>
<span id="subtitle">Step 4</span><P>
Attach OLED Display to the Model E4 using M2 * 10mm screws and nuts.
<BR><P>
![pic](images/Case3/Case3_ass4.png)<P>

<span id="subtitle">Step 5</span><P>
Attach motor fan to the Model F using M4 * 10mm screws and nuts. And the connecting wire could be bended to the hole next to it.
<BR><P>
![pic](images/Case3/Case3_ass5.png)<P>
<span id="subtitle">Step 6</span><P>
To build a fan stand, put Model F into the B3, B4 model.
<BR><P>
![pic](images/Case3/Case3_ass6.png)<P>

<span id="subtitle">Step 7</span><P>
To build a table, put the Model I1 onto the model I2.
<BR><P>
![pic](images/Case3/Case3_ass7.png)<P>

<span id="subtitle">Step 8</span><P>
The table completed!
<BR><P>
![pic](images/Case3/Case3_ass8.png)<P>

<span id="subtitle">Step 9</span><P>
Place the table at the living room.
<BR><P>
![pic](images/Case3/Case3_ass9.png)<P>

<span id="subtitle">Step 10</span><P>
Assembly Completed!
<BR><P>
![pic](images/Case3/Case3_ass10.png)<P>





## Hardware connect
<HR>

1. Connect the Temperature and Humidity sensor (DHT11) to P2
2. Connect the extended OLED display to I2C Port 
3. Connect the Motor module to P1
![pic_80](images/Case3/Case3_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED display</span><P>
* In `on start`, put `initialize OLED with width 128 height 64` to initialize the OLED display
![pic_70](images/Case3/Case3_p1.png)<P>

<span id="subtitle">Step 2. Create variable</span><P>
* Create a variable called `temperature`
![pic_50](images/Case3/Case3_p2.png)<P>

<span id="subtitle">Step 3. Read and show the reading from DHT11</span><P>
* In `Forever`, read the data by `Read Temperature & Humidity Sensor at pin P2`
* Get the temperature value from data, and save it to variable by `(set temperature to Get Temperature °C`)
* Before update the screen infomation, suggest clear up the OLED display each time
* Use `clear OLED display` to clear the display
* Then use `show string join Temperature: temperature` to show the temperature value with formatted text on display
![pic_80](images/Case3/Case3_p3.png)<P>

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
MakeCode: [https://makecode.microbit.org/_c2637VXcbfHP](https://makecode.microbit.org/_c2637VXcbfHP)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_c2637VXcbfHP" width="100%" height="500" frameborder="0"></iframe>


## Result
<HR>

When the room temperature changing, it will match either one of the condition, and the fans will turn on or off with different speed according to the room temperature.<BR><P>
![pic](images/Case3/Case3_result.gif)<P>

## Think
<HR>

Q1. Apart from open the fans, any other method to reduce the temperature?<BR><P>
