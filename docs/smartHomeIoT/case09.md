# IoT Case 09: Smart Digital Morning Clock

Level: ![level](images/level4.png)
![auto_fit](images/Case9/intro.png)<P>

## Goal
<HR>

Make a digital clock that performs a normal clock function with auto-synchronizing Internet time, and alert at specific time.<BR><P>

## Background
<HR>

<span id="subtitle">What is Smart Digital Clock?</span><BR><P>
Smart digital clock is a clock that shows time as accurate as to atomic clock by connecting to the Internet.<BR><P>
<span id="subtitle">Smart Digital Clock Principle</span><BR><P>
NTP protocol ensures devices synchronize their time with an accurate time internet provider. With connecting to the Internet, the digital clock can show the time close to atomic clock in millisecond .<BR><P>
In the program, it will get the internet time every 0.5 second to show the time on the OLED. When the time is arrived to specific time (e.g. 06:00:00), it will turn on the alert. Otherwise, it will turn of the buzzer. When the user pressed the button A, the alarm can be closed.
![pic](images/Case9/Case9_flowchart.png)<P>

## Part List
<HR>

![pic_90](images/Case9/Case9_parts1.png)<P>

## Assembly step
<HR>
<span id="subtitle">Step 1</span><BR><P>
In this case, build the “Big Style Model” as a home base.<BR><P>

![pic_90](images/Case9/Case9_ass1.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Let’s build a bed room to install a digital clock. Put the model E3 onto cardboard A, align with the holes at model A and B3.<BR><P>
	
![pic_90](images/Case9/Case9_ass2.png)<P>
<span id="subtitle">Step 3</span><BR><P>
Attach the OLED display as a digital clock to the model E3 using M2 \* 10mm screws and nuts.
<BR><P>
	
![pic_90](images/Case9/Case9_ass3.png)<P>	


<span id="subtitle">Step 4</span><BR><P>
Put the model E4 onto cardboard A, align with the holes at model A and B4.
<BR><P>
	
![auto_fit](images/Case9/Case9_ass4.png)<P>

<span id="subtitle">Step 5</span><BR><P>
To build a bed. Put model J2 onto the model J1, then put together all the cardboard parts (J1-J3).<BR><P>
	
![pic_90](images/Case9/Case9_ass5.png)<P>

<span id="subtitle">Step 6</span><BR><P>
The bed completed!<BR><P>
	
![pic_90](images/Case9/Case9_ass6.png)<P>


<span id="subtitle">Step 7</span><BR><P>
Place the bed next to the digital clock at the room.<BR><P>
	
![pic_90](images/Case9/Case9_ass7.png)<P>

<span id="subtitle">Step 8</span><BR><P>
Assembly Completed!<BR><P>
	
![pic_90](images/Case9/Case9_ass8.png)<P>


## Hardware connect
<HR>

1. Connect OLED to I2C port
2. Pull down the buzzer switch to connect the buzzer


![pic_80](images/Case9/Case9_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED, IoT:bit and connect to WiFi, create the variable
* Snap `Initialize OLED with width 128, height 64` to `on start`
* Snap `Initialize IoT:bit TX P16 RX P8` to `on start`
* Snap `Set Wi-Fi to ssid pwd` to `on start` and enter the SSID and password
* Create the variable `alarmTrig`
* Set the `alarmTrig` variable to `false`
![auto_fit](images/Case9/Case9_p1.png)<P>

<span id="subtitle">Step 2. Check Wi-Fi connection state</span><BR><P>
* Snap the `On WiFi connected` block to editor
* Put a `show icon tick` inside the block to show tick icon after connected

![auto_fit](images/Case9/Case9_p2.png)<P>

<span id="subtitle">Step 3. Get the NTP time</span><BR><P>
* Put a `if` statement in `Forever`
* Use `WiFi connected?` as condition
* In `if` segment, put `Get NTP Current Time at city HongKong(UTC+8)` to get NTP time
* `Pause 500ms` to get the NTP time with each 0.5 second

![pic_90](images/Case9/Case9_p3.png)<P>

<span id="subtitle">Step 4. Show the NTP time on display</span><BR><P>
* Put `On NTP received` to editor
* When get the NTP time, the program in this block will running
* Clear the display before each update by `Clear OLED display`
* Show the formatted time string with `show string join Date: day.Month.Year`
*  Show the formatted time string with `show string join Time: Hour:Minute:Second`
![auto_fit](images/Case9/Case9_p4.png)<P>

<span id="subtitle">Step 5. Set the alarm</span><BR><P>
* Put a `if` statement with multiple conditions `Hour = 6` and `Minute = 0` and `Second = 6`
* Put `set alarmTrig to true` in `if` segment
![auto_fit](images/Case9/Case9_p5.png)<P>

<span id="subtitle">Step 6. Set up the sound</span><BR><P>
* Put another `Forever` to editor
* Put a `if-else` statement inside the `Forever`
* Use `alarmTrig = true` as condition
* Play the alarm by melody at tempo 500 bpm
* Otherwise, stop the alarm
![auto_fit](images/Case9/Case9_p6.png)<P>

<span id="subtitle">Step 7. Turn off alarm</span><BR><P>
* Put `on Button A pressed` to editor
* Put `set alarmTrig to false` into the block
![auto_fit](images/Case9/Case9_p7.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/S77738-06496-37751-47481](https://makecode.microbit.org/S77738-06496-37751-47481)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/S77738-06496-37751-47481
" width="100%" height="500" frameborder="0"></iframe>

## Result
After you connected to the Internet, the tick will open an start getting NTP time.<BR><P>
![auto_fit](images/Case9/Case9_result.gif)<P>

 

## Think
<HR>

Q1. Apart from showing the time and alarm, any other tasks can be done when we know the time?<BR><P>
