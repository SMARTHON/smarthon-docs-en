# Case 01: Grow Light Color Control LED

Level: ![pic](images/case01/image211.png)
   
![auto_fit](images/case01/image84.png)


## Goal
<HR>
Create a grow light that can be turned to different colors using the buttons on the micro:bit board.<P>

## Background

<HR>
<span id="subtitle">What is a Grow LED Light Color Control?</span><P>

Grow LED Light Color Control allows you to experiment and observe the effects of different colors of light on plant growth. With our multicolor LED, you can choose out of many different colors. By way of experimentation, you can determine a combination of blue and red lights which make purple, is the most efficient light for the plant. 

![auto_fit](images/case01/01concept.png)

<span id="subtitle">Know More: Effect on Plant with Different Light Color</span><P>

Light is one of the most important aspects of plant growth. The use of supplemental grow lights is essential when you are considering cultivating plants at home. However, what many do not realise is that different colors of light have different effects on the growth of the plant.

Light color affects plant growth because different wavelengths of light influence the rate of photosynthesis. Chlorophyll primarily absorbs blue (around 430-450 nm) and red (around 640-680 nm) light most efficiently, driving higher photosynthetic rates, while green light (500-600 nm) is less absorbed and results in lower efficiency.

As a result, plants exposed to red or blue light typically grow faster and produce more glucose, while those under green light show slower growth. Therefore, by adjusting light colours through LED grow lights, growers can effectively influence plant growth rate.

![auto_fit](images/case01/image91.png)


## Part List

![auto_fit](images/case01/Case1.jpg)<P>

## Assembly Steps

<span id="subtitle">Step 1</span><BR><P>
To start with, build the plant pot model with soil and seedling.<BR><P>
![pic](images/case01/image14.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Connect the Module Stand with the Pot base.<BR><P>

![pic](images/case01/Step2.jpg)

![pic](images/case01/Step2a.png)

<span id="subtitle">Step 3</span><BR><P>
Insert screw with grow light led to part C1.<BR><P>

![pic](images/case01/Step3.png)

<span id="subtitle">Step 4</span><BR><P>
Complete!<BR><P>

![pic](images/case01/Step4.jpg)

## Hardware Connection
<HR>
1. Connect LED Grow Light to P1.

![pic](images/case01/image73.png)

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Program Startup</span><BR><P>

* Snap `set strip to NeoPixel at pin P1 with 10 leds as RGB (GRB format)`
* Set Brightness: `strip set brightness 255`

![pic](images/case01/1.png)

<span id="subtitle">Step 2: Pressing Button A </span><BR><P>

* Snap `on button A pressed`
* Snap `strip show color red`
* Instantly updates all 10 LEDs on the strip to solid Red.

![pic](images/case01/2.png)

<span id="subtitle">Step 3: Pressing Button B </span><BR><P>

* Snap `on button B pressed`
* Snap `strip show color green`
* Instantly updates all 10 LEDs on the strip to solid Green.

![pic](images/case01/3.png)

<span id="subtitle">Step 4:  Pressing Buttons A + B Together </span><BR><P>

* Snap `on button A+B pressed`
* Snap `strip set pixel color`
* Assign Individual Pixel Colors in Memory:
    Pixel 0: Red
    Pixel 1: Red
    Pixel 2: Blue
    Pixel 3: Red
    Pixel 4: Red
    Pixel 5: Blue
    Pixel 6: Red
    Pixel 7: Red
    Pixel 8: Blue
    Pixel 9: Red
* Render to the Hardware with `strip show` and send all stored color values from memory out to the physical LEDs at once.

![pic](images/case01/4.png)


MakeCode: [https://makecode.microbit.org/\_Rkv31xWpm3ae](https://makecode.microbit.org/_Rkv31xWpm3ae) 
![pic](images/case01/image124.png)<P>

## Result
<HR>

![pic](images/case01/image238.gif)<P>

## Think
<HR>
Q1. How do you mix the color to get the best effect for plant growth?