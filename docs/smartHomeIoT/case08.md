# Case 08: Automatic Sunlight Detecting Curtain
Level: ![level](images/level3.png)

![auto_fit](images/Case8/intro.png)<P>

## Goal
<HR>

Make a smart curtain that operates automatically by detecting the sunlight around the house to save energy.<BR><P>

## Background
<HR>

<span id="subtitle">What is Automatic Sunlight Detecting Curtain </span><P>
Automatic Sunlight Detecting Curtain is a curtain that scrolls up or down automatically according to the detection of sunlight.<BR><P>

<span id="subtitle">Automatic Sunlight Detecting Curtain Principle</span><P>
The light sensor is installed outside of the house. When it detects strong light (Light > 70), it indicates that there is sunlight that can reach the house. The curtain in this case should scroll down to prevent heat energy transfer into the house. It can reduce energy loss and can save the energy of air conditioner.
<BR><P>

![pic_100](images/Case8/Case8_flowchart.png)<P>

## Key knowledge
<HR>

In programming part, there is a "flag" concept to be used in this case. It can check whether the curtain is pulled down or not and prevent from keeping pull down the curtain.


## Part List
<HR>

![pic_90](images/Case8/Case8_parts.png)<P>

 
## Assembly step
<HR>
<span id="subtitle">Step 1</span><P>
In this case, build the “Big Style Model” as a home base.<BR><P>

![auto_fit](images/Case8/Case8_ass1.png)<P>

<span id="subtitle">Step 2</span><P>
To make a curtain. Attach the curtain rod to 360ᵒ servo by using the screwdriver to assist.
<BR><P>

![pic_90](images/Case8/Case8_ass2.png)<P>

<span id="subtitle">Step 3</span><P>
Cut the curtain paper into a 8cm\*8cm square.<BR><P>

![pic_90](images/Case8/Case8_ass3.png)<P>

<span id="subtitle">Step 4</span><P>
Stick the cutted paper on the curtain rod by glue.
<BR><P>

![pic_90](images/Case8/Case8_ass4.png)<P>


<span id="subtitle">Step 5</span><P>
Shape the blu tack into a recteangle by hand.<BR><P>

![pic_90](images/Case8/Case8_ass5.png)<P>

<span id="subtitle">Step 6</span><P>

Stick the shaped blu tack at the bottom of the paper curtain.
<BR><P>

![pic_90](images/Case8/Case8_ass6.png)<P>

<span id="subtitle">Step 7</span><P>

Attach the completed curtain (servo) onto Model B1 using M2 \* 10mm screws and nuts.
<BR><P>

![pic_90](images/Case8/Case8_ass7.png)<P>


<span id="subtitle">Step 8</span><P>
Close the house by model C1 and C2.<BR><P>

![pic_90](images/Case8/Case8_ass8.png)<P>

<span id="subtitle">Step 9</span><P>

Attach the light sensor onto model C2 using M4 \* 10mm screws and nuts.<BR><P>

![pic_90](images/Case8/Case8_ass9.png)<P>

<span id="subtitle">Step 10</span><P>
Assembly Completed!
<BR><P>

![pic_90](images/Case8/Case8_ass10.png)<P>


	
## Hardware connect
<HR>

1. Connect the light sensor to P1
2. Connect the 360 degree servo to P2
![pic_80](images/Case8/Case8_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize OLED and create the variable</span><P>
* On start, initialize the OLED display by `initialize OLED with width 128 height 64` 
* Create the `curtainOn` variable and set it to `false`

![auto_fit](images/Case8/Case8_p1.png)<P>

<span id="subtitle">Step 2. Create curtain control function "openCurtain"</span><P>
* Create function `openCurtain` 
* Inside the function, control the speed and direction of the 360 degree servo at connected pins, such as `Turn 360 Servo with clockwise direction speed level 3 at P2`
* Add pause to wait it rotate for few second (depend on your model setup)
* Stop the 360 servo with same method, such as `Turn 360 Servo with clockwise direction speed level 0 at P2`
* set the `curtainOn` variable to `true`

![auto_fit](images/Case8/Case8_p2.png)<P>

<span id="subtitle">Step 3. Create curtain control function "closeCurtain"</span><P>
* Create function `closeCurtain` 
* Inside the function, following the previous function, but in reversed direction and state
* control the speed and direction of the 360 degree servo at connected pins, such as `Turn 360 Servo with anti-clockwise direction speed level 3 at P2`
* Add pause to wait it rotate for few second (depend on your model setup)
* Stop the 360 servo with same method, such as `Turn 360 Servo with anti-clockwise direction speed level 0 at P2`
* set the `curtainOn` variable to `false`
![auto_fit](images/Case8/Case8_p3.png)<P>

<span id="subtitle">Step 4. Get the light intensity value</span><P>
* In `Forever`, reading the value by `set light to Get light value (percentage) at Pin P1`
* Clear the OLED display before each update by `clear OLED display`
* Show the number of value on display by `show number light`

![auto_fit](images/Case8/Case8_p4.png)<P>

<span id="subtitle">Step 5. Examine the light intensity value and reaction</span><P>

* Snap a nested `if statement` to `Forever`
* Set `light2 >= 70 ` and `curtainOn =  true` as first condition
* In the `if` segment, that's means the sunlight is strong, need to close the curtain, `call closeCurtain`
* In the second condition, use `light2 < 40` and `curtainOn = false` 
* In the second `if` segment, that's means the sunlight is weak, need to open the curtain, `call openCurtain`

![auto_fit](images/Case8/Case8_p5.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_6sm7bVe3AP2T](https://makecode.microbit.org/_ieEiYx8qffxJ)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_6sm7bVe3AP2T" width="100%" height="500" frameborder="0"></iframe>


## Result
<HR>

When the light sensor detects the light value outside the house is strong, the servo will rotate to scroll down the curtain. When the light is not strong, the servo will rotate in anti direction to scroll up the curtain

![auto_fit](images/Case8/Case8_result.gif)<P>

## Think
<HR>

Q1. Apart from the sunlight value, any other condition can be used to determine the curtain state? <BR><P>
