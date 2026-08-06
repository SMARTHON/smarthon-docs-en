# Case 2: Smart Shade Automation

![pic](images/case14/1.png)

## Goal

Create a smart shade system that automatically operates based on detected sunlight intensity.

## Background

<span id="subtitle">What is Smart Shade Automation?</span><P>

A Smart Shade Automation system helps maintain optimal light and temperature conditions during sunny days while retaining heat at night. By regulating sunlight exposure and temperature, the system creates a more stable environment for plants, which supports healthier growth and higher yields. This precise control ensures plants thrive in consistent and favorable conditions, boosting overall productivity and sustainability.

<span id="subtitle">Smart Shade Automation System Operation</span><P>

The digital light sensor continuously monitors the sunlight intensity. When the detected light intensity (in lux) exceeds the threshold, the 180° Servo will close the shade. Otherwise, the shade will remain open.  
Real-Life Application

Real-life greenhouses typically use polycarbonate or glass coverings for high light transmission. Retractable shade screens made of thermal or net fabrics are also installed to prevent leaf burn during intense sunlight.

Some greenhouses are installed with semi-transparent solar panels on roofs to generate solar power while providing shade.

In our greenhouse model, the shade is simulated by a roof vent. The vent provides shade during excessive sunlight.

## Part List

![auto_fit](images/case14/2.png)

## Assembly Steps
<span id="subtitle">Step 1</span><BR><P>
To start with, build the plant pot model with soil and seedling.<BR><P>
![pic](images/case14/3.png)<p>

<span id="subtitle">Step 2</span><BR><P>
Build the greenhouse model.<BR><P>
![pic](images/case14/4.png)<p>

<span id="subtitle">Step 3</span><BR><P>
Install the Digital Light Sensor on the rooftop of the greenhouse model.<BR><P>
![pic](images/case14/5.png)<p>

<span id="subtitle">Step 4</span><BR><P>
Install the LCD Display on the wall of the greenhouse model.<BR><P>
![pic](images/case14/6.png)<p>

<span id="subtitle">Step 5</span><BR><P>
Install the upper window in the cover of the greenhouse model.<BR><P>
![pic](images/case14/6_1.png)<p>

<span id="subtitle">Step 6</span><BR><P>
Install the 180° Servo and C1 with the upper window on the rooftop window of the greenhouse model.<BR><P>
![pic](images/case14/7_1.png)
![pic](images/case14/7_1_1.png)<p>

<span id="subtitle">Step 7</span><BR><P>
Put the pot tray into the greenhouse model, then put the pot model onto the tray. Completed!<BR><P>
![pic](images/case14/8.png)<p>

## Hardware Connection

1. Connect the 180° Servo to P0.  
2. Connect the LCD Display to the I2C.  
3. Connect the Digital Light Sensor to the I2C.

![pic](images/case14/9.png)<p>

## Programming (MakeCode)

MakeCode: [https://makecode.microbit.org/\_1u9EYcP4yhv6](https://makecode.microbit.org/_1u9EYcP4yhv6)   
![pic](images/case14/10.png)<p>

## Result

![pic](images/case14/11.gif)<p>
