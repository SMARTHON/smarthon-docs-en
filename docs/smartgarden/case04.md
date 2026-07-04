# Case 04: Smart Humidity Regulation

![pic](images/case04/image18.png)


## Goal
<HR>

Create an automatic system that humidifies the air whenever there is lack of it in the environment.


## Background
<HR>

<b>What is an Automatic Humidity Control?</b><P>

The Automatic Humidity Control system measures humidity levels and efficiently adjusts the environment to the most favorable state for plant growth.

<b>Automatic Humidity Control Operation</b>

The LCD screen displays the humidity in the room. Whenever the humidity sensor detects the lack of humidity in the room the fog modules turn on. The led lights on microbit correspond to the operation of the fog module, starlike pattern when module is on, a single dot when the module is off. Whenever the humidity in the room rises to the appropriate level, the fog module turns off. 

<b>Know More: Why is Humidity Control Important for Plant Growth?</b>

Humidity control is crucial for plant growth because it directly affects transpiration, nutrient uptake and disease prevention.

Plants lose water through tiny leaf pores called stomata. Optimal humidity (typically 40-70%) keeps these pores open for efficient gas exchange and photosynthesis while preventing excessive water loss that stresses the plant. 

Too high humidity promotes fungal diseases like mold, while too low causes wilting and stunted growth by limiting cell expansion. By maintaining ideal levels, growers ensure healthy development, faster growth rates and higher yields in controlled environments like greenhouses.

![pic](images/case04/image189.png)

## Part List
<HR>

![alt="auto_fit"](images/case04/case04_parts.png)<P>

## Assembly Steps

<span id="subtitle">Step 1</span><BR><P>
To start with, build the plant pot model with soil and seedling. Install the LCD Display during the build.<BR><P>
![pic](images/case04/image14.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Connect the Module Stand with the Pot base.<BR><P>

![pic](images/case04/Step2.jpg)

![pic](images/case04/Step2a.png)

<span id="subtitle">Step 3</span><BR><P>
Connect the Temperature and Humidity Sensor with a 3-pin module wire and install it under part C1.<BR><P>
![pic](images/case04/Step3.png)

<span id="subtitle">Step 4</span><BR><P>
Install the Fog Module and Fog Accessories as shown in the pictures.<BR><P>
![pic](images/case04/Step4_combined.jpg)


<span id="subtitle">Step 5</span><BR><P>
Put the Fog Module and Fog Accessories components into the Humidifier Cup.<BR><P>

![pic](images/case04/Step5.jpg)

![pic](images/case04/Step5a.png)

<span id="subtitle">Step 6</span><BR><P>
Put the model onto the pot tray and plastic mat. Completed!<BR><P>

![pic](images/case04/Step6.jpg)

## Hardware Connection
<HR>

1. Connect Fog Module to P0.  
2. Connect Temperature and Humidity Sensor to P1.  
3. Connect LCD Display to I2C.

![pic](images/case04/image145.png)<P>

## Programming (MakeCode)
<HR>

MakeCode: [https://makecode.microbit.org/\_1hKYuFTH7Rri](https://makecode.microbit.org/_1hKYuFTH7Rri)   
![pic](images/case04/image88.png)<P>

## Result
<HR>

![pic](images/case04/image163.jpg)
<P>