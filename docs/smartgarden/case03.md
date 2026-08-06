# Case 03: Intelligent Garden Lighting System

![pic](images/case03/image170.png)

## Goal
<HR>
Create an automatic grow light that will turn on when the light sensor detects the lack of appropriate amount of light.
<P>

## Background
<HR>
<b>What is Smart LED Grow Light?</b><P>

Smart LED grow light helps the plant by tracking the lighting conditions and turning on whenever the plant needs more light. This type of system is incredibly useful in growing a plant in indoor conditions. 

<b>Smart LED Grow Light Operation</b>

We will use a light sensor to track the light intensity near the plant. Whenever the light intensity falls under a specific number, the board enables the LED to grow light that will shine on the plant. When we have enough light in the system, the LED will turn off. 

![pic](images/case03/flowchart.png)

<b>Know More: Why Is Light Important for Plant Growth?</b>

Light drives photosynthesis, converting CO₂ and water into energy-rich sugars that provide nutrients for plant growth. It also regulates the growth of plants by influencing leaf expansion, root development and chlorophyll production through its intensity, duration and spectrum. Moreover, plants rely on daylight length to trigger key stages such as flowering, seed formation and dormancy. The existence of light ensures they grow in harmony with seasonal changes.

  ![alt="auto_fit"](images/case03/image104.png)

## Part List
<HR>

![alt="auto_fit"](images/case03/Case3.jpg)<P>

## Assembly Steps

<span id="subtitle">Step 1</span><BR><P>
To start with, build the plant pot model with soil and seedling. Install the LCD Display during the build.<BR><P>
![pic](images/case02/image14.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Connect the Module Stand with the Pot base.<BR><P>

![auto_fit](images/case03/Step2a.png)

![auto_fit](images/case03/Step2.jpg)

<span id="subtitle">Step 3</span><BR><P>
Connect the Digital Light Sensor with a 4-pin module wire and install it above part C1.<BR><P>

![auto_fit](images/case03/Step3.png)

<span id="subtitle">Step 4</span><BR><P>
Connect the Digital Light Sensor with a 4-pin module wire and install it above part C1.<BR><P>

![auto_fit](images/case03/Step4.png)

<span id="subtitle">Step 5</span><BR><P>
Put the model onto the pot tray and plastic mat. Completed!<BR><P>

![auto_fit](images/case03/Step5.jpg)

## Hardware Connection
<HR>

1. Connect LED Grow Light to P2.  
2. Connect LCD Display to I2C.  
3. Connect Digital Light Sensor to I2C.

![pic](images/case03/image108.png)

## Programming (MakeCode)
<HR>

MakeCode: [https://makecode.microbit.org/_9Pc5t3HVYXzy](https://makecode.microbit.org/_9Pc5t3HVYXzy)   
  ![alt="auto_fit"](images/case03/image46.png)<P>

Optional: Turn on the light at least 12 hours every day

If every day at 6 am to 7 pm, it will check whether light intensity is high enough. If low, turn on the light. In the program below, please set your current hour to the variable in on start.

![alt="auto_fit"](images/case03/image130.png)<P>

Makecode: [https://makecode.microbit.org/_2wDYCrAyVAsH](https://makecode.microbit.org/_2wDYCrAyVAsH)

## Result
<HR>

  ![alt="auto_fit"](images/case03/image158.gif)<P>
