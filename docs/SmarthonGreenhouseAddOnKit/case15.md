# Case 3: CO2 Ventilation Control

![pic](images/case15/1.png)

## Goal

Create an air quality ventilation control system that automatically operates the greenhouse window based on the detected air quality and carbon dioxide levels.

## Background

<span id="subtitle">What are Total Volatile Organic Compounds (TVOC)?</span><P>

TVOC refers to the combined concentration of various volatile organic compounds present in the air. VOCs are organic chemicals that easily evaporate at room temperature and are commonly emitted from building materials, cleaning products, paints and other household items. TVOC is used as an overall indicator of indoor air quality because it represents the total amount of these airborne pollutants, providing a general measure of air contamination levels.

<span id="subtitle">What is Air Quality Ventilation Control?</span><P>

Ventilation is essential in greenhouses for regulating temperature, humidity and carbon dioxide levels. Carbon dioxide is vital for photosynthesis and plant growth, and a deficiency can hinder or even stop plant development. The Ventilation Control System ensures a continuous supply of fresh carbon dioxide by exchanging the air inside the greenhouse, which supports healthy plant activity. 

<span id="subtitle">Air Quality Ventilation Control System Operation</span><P>

The CO2 and TVOC sensor continuously monitors the levels of carbon dioxide and TVOC. When the TVOC concentration exceeds a predefined threshold or the CO2 level falls below a specified value, the 180° Servo will open the window. Otherwise, the window will remain closed.

<span id="subtitle">Real-Life Application</span><P>

In real-life greenhouses, sophisticated air quality ventilation control systems are used to precisely balance CO₂ enrichment and pollutant management.

Environmental CO2 levels are only around 400 ppm. To boost photosynthesis rates, greenhouses use CO₂ generators or compressed CO₂ systems to actively supplement CO2 to 800-1200 ppm during daytime.

On the other hand, automated vents and fans are used to regulate TVOC and other pollutants. They open when VOCs exceed safe thresholds, and close otherwise to maintain beneficial CO₂ levels.

In our greenhouse model, an automated window is used to regulate pollutant levels while gaining CO₂ supply from outdoor air.

## Part List

![auto_fit](images/case15/2.png)

## Assembly Steps
<span id="subtitle">Step 1</span><BR><P>
To start with, build the plant pot model with soil and seedlings.<BR><P>
![pic](images/case15/3.png)<p>

<span id="subtitle">Step 2</span><BR><P>
Build the greenhouse model. The 180° Servo should be installed onto the model during the build.<BR><P>
![pic](images/case15/4.png)<p>

<span id="subtitle">Step 3</span><BR><P>
Install the CO2 and TVOC Sensor on the wall of the greenhouse model.<BR><P>
![pic](images/case15/5.png)<p>

<span id="subtitle">Step 4</span><BR><P>
Install the LCD Display on the wall of the greenhouse model.<BR><P>
![pic](images/case15/6.png)<p>

<span id="subtitle">Step 5</span><BR><P>
Install the upper window on the cover of the greenhouse model.<BR><P>
![pic](images/case15/7.png)
![pic](images/case15/7_1.png)<p>

<span id="subtitle">Step 6</span><BR><P>
Install B2 inside the model on the RHS wall of the greenhouse model.<BR><P>
![pic](images/case15/7_2.png)<p>

<span id="subtitle">Step 7</span><BR><P>
Assemble B1 with the 180° Servo and install it with B2 on the LHS wall of the greenhouse model.<BR><P>
![pic](images/case15/7_3.png)
![pic](images/case15/7_4.png)<p>

<span id="subtitle">Step 8</span><BR><P>
Put the pot tray into the greenhouse model, then put the pot model onto the tray. Completed!<BR><P>
![pic](images/case15/7_5.png)<p>

## Hardware Connection

1. Connect 180° Servo to P0.  
2. Connect LCD Display to I2C.  
3. Connect CO2 and TVOC sensor to I2C.

![pic](images/case15/8.png)<p>

## Programming (MakeCode)

MakeCode: [https://makecode.microbit.org/\_dcMdr0P8EVxi](https://makecode.microbit.org/_dcMdr0P8EVxi)   
![pic](images/case15/9.png)<p>

## Result

![pic](images/case15/10.png)<p>
