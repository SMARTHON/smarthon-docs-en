# Case 05: Smart Fridge Alert

Level: ![level](images/level2.png)
![auto_fit](images/Case5/intro.png)<P>

## Goal
<HR>

Create a fridge that can detect the door state, when the door was not in close state for a long time, warning the user.
<BR><P>

## Background
<HR>

<span id="subtitle">What is Smart Fridge Alert?</span><P>
Smart Fridge is a Fridge that has an extra sensor to help it determine the door close state, when the user forgets to close the door, it will warn the user to close it to reduce waste of energy and prevent food poisoning.<BR><P>

<span id="subtitle">Smart Fridge Alert Principle</span><P>
Firstly, we set the time counter variable as 0. When the door is closed, inside the fridge should be dark (light sensor value < 30), nothing happened;
When the door is opened, the room light will go into the fridge (light sensor value > 30), the counter will start counting the time every 1 second, if time counter > 60, the buzzer will be turned on to alert the user.<BR><P>


![pic_100](images/Case5/Case5_flowchart.png)<P>

## Part List
<HR>

![pic_90](images/Case5/Case5_parts.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><P>
In this case, “Big House Model” is used as a home base to start with.
<BR><P>
![pic](images/Case5/Case5_ass1.png)<P>

<span id="subtitle">Step 2</span><P>
Let’s build a kitchen. Put Model E3 onto the Model A and B4, align with the holes at it. Put Model E1 onto the Model A, align with the holes at Model A and B3.
<BR><P>
![pic](images/Case5/Case5_ass2.png)<P>

<span id="subtitle">Step 3</span><P>
Completed.
<BR><P>
![pic](images/Case5/Case5_ass3.png)<P>

<span id="subtitle">Step 4</span><P>
To build a fridge, attach light sensor onto model G1 using M4 * 10mm screws and nuts. And the connecting wire could be bended to the hole below it.
<BR><P>
![pic](images/Case5/Case5_ass4.png)<P>

<span id="subtitle">Step 5</span><P>
Fold and bend the Model G1 accordinglyand put Model G3 into the Model G1, align with the holes.
<BR><P>
![pic](images/Case5/Case5_ass5.png)<P>

<span id="subtitle">Step 6</span><P>
Put Model G2 onto the Model G1, align with the holes.
<BR><P>
![pic](images/Case5/Case5_ass6.png)<P>


<span id="subtitle">Step 7</span><P>
The fridge completed!
<BR><P>
![pic](images/Case5/Case5_ass7.png)<P>

<span id="subtitle">Step 8</span><P>
Place the fridge at the corner.
<BR><P>
![pic](images/Case5/Case5_ass8.png)<P>

<span id="subtitle">Step 9</span><P>
Assembly Completed!
![pic](images/Case5/Case5_ass9.png)<P>



## Hardware connect
<HR>

1. Connect the Light sensor to Pin P1
2. Pull down the Buzzer switch to connect buzzer

![pic_90](images/Case5/Case5_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize counter variable</span><P>
* On start, create a “counter” variable and set to 0

![auto_fit](images/Case5/Case5_p1.png)<P>
![auto_fit](images/Case5/Case5_p2.png)<P>

<span id="subtitle">Step 2. Examine the light intensity</span><P>
* In `Forever`, put a `if-else` statement
* Use `Get light value (percentage) at Pin P1 > 30` as condition
![auto_fit](images/Case5/Case5_p3.png)<P>

<span id="subtitle">Step 3. Warning counter</span><P>
* In the `if` segment, that's means the light intensity is strong, the door was opened
* Add the counter with 1 by `change counter by 1` to sum up the time of door opened
* Put the second `if` statement with `counter >= 60` condition to examine when should issue warning sound
* In the sencond `if` segment, put `start melody jump down repeating once` to issue the warning sound
* Back to the first `if-else` level, in the `else` segment, that's means light intensity is weak, door was closed, so reset the counter to 0 by `set counter to 0`
* Put a `pause (ms) 1000` to check the door each second
![auto_fit](images/Case5/Case5_p4.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/S58749-50803-30551-09828](https://makecode.microbit.org/S58749-50803-30551-09828)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/S58749-50803-30551-09828" width="100%" height="500" frameborder="0"></iframe>


## Results
<HR>
When the door is opened for more than 1 minute, the buzzer will play some sound to warn the user.
<BR><P>

![auto_fit](images/Case5/Case5_result.gif)<P>

## Think
<HR>

1. Apart from making the sound from the buzzer, another method to warn the user?
2. Can you make use of the fridge, to make a smart box to alert users?


