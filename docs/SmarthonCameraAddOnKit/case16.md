# Case 1: Plant Height Measurement
  
![auto_fit](images/case01/image01.png)

## Goal
<HR>

To design and implement an automated system that measures and monitors plant height in a greenhouse using an AI camera in colour recognition mode to detect the distance between a leaf-mounted marker and a soil-based reference point.<P>

## Background

<HR>

How can plant height be measured automatically with greater consistency and accuracy?

Plant height is a key indicator of plant growth and development, yet manual measurement is often time-consuming and may introduce human error. 

To address this limitation, this product employs HuskyLens 2 in colour recognition mode to detect two colour blocks, one attached to the leaf and the other used as a reference label. The system identifies the centre points of the two detected blocks, calculates the difference in their y-coordinates to determine the vertical distance, and then converts the pixel value to centimetres using a predefined pixel-to-centimetre ratio. 

By integrating image recognition and coordinate-based computation, the product provides a practical, efficient solution for automatic plant height measurement. 

## Huskylens 1

<span id="subtitle">Part 1: Part List </span><BR><P>

![auto_fit](images/case01/image02.png)<P>

<span id="subtitle">Part 2:Hardware Connection </span><BR><P>

- Connect the LCD Display to the I2C.<P>

- Connect the AI Camera to I2C.<P>

![auto_fit](images/case01/image03.png)<P>

<span id="subtitle">Part 3: Programming </span><BR><P>

MakeCode: [https://makecode.microbit.org/S67391-90165-86001-55733](https://makecode.microbit.org/S67391-90165-86001-55733)
![auto_fit](images/case01/image04.png)<P>

<span id="subtitle">Part 4: AI Camera (Pre-setup)</span><BR><P>

a.Assembly step on how to screw the camera onto the greenhouse box

<span id="subtitle">Step 1</span><P>
Screw the smaller component in the bracket pack onto the Huskylens 1
![auto_fit](images/case01/image05.png)<P>

<span id="subtitle">Step 2</span><P>
Screw the larger component in the bracket pack onto Huskylens 1.
![auto_fit](images/case01/image06.png)<P>

<span id="subtitle">Step 3<P>
Screw the Huskylens 1 onto the box. Complete!
![auto_fit](images/case01/image07.png)<P>


b.Before programming, follow clear steps to train the model, ensuring the camera learns leaf colour as ID1 and reference point colour as ID2, so you feel ready to proceed confidently.


<span id="subtitle">Step 1</span><BR><P>
Set the edge of the plant pot model as the reference point by sticking a label to it
![auto_fit](images/case01/image08.png)<P>

<span id="subtitle">Step 2</span><BR><P>
Connect the HuskyLens 2 to the I2C port on the IoT: bit as shown below.
![auto_fit](images/case01/image09.png)<P>

<span id="subtitle">Step 3</span><P>
The device will turn on automatically. Scroll the roller to switch into “Colour Recognition” mode. 
![auto_fit](images/case01/image10.png)<P>

<span id="subtitle">Step 4</span><BR><P>
Use the camera to focus on the leaf until a block appears around the plant, make sure the crosshair is pointing to that block, and click the learn button. After that, there will be a countdown. You need to click the learn button once again before the countdown finishes to confirm the learning action.
![auto_fit](images/case01/image11.png)<P>

<span id="subtitle">Step 5</span><BR><P>
Use the camera to focus on the red label until a block appears around it, make sure the crosshair is pointing to that block, and click the learn button. After that, there will be a countdown. You need to click the learn button once again before the countdown finishes to confirm the learning action.
![auto_fit](images/case01/image12.png)<P>


Remark: Because it assigns the ID number based on the order of learning, you may need to perform the following steps if you marked the wrong ID for either the leaf colour or the label colour. Click the learn button once, wait for the countdown to finish, then click it again. It will show another countdown for the forgotten ID. This time, click the learn button again before the countdown finishes. After that, repeat Step 3 and Step 4 to learn them again. 
![auto_fit](images/case01/image13.png)<P>


<span id="subtitle">Part 5: Final Result</span><BR><P>
![auto_fit](images/case01/image14.png)<P>


## Huskylens 2

<span id="subtitle">Part 1: Part List </span><BR><P>

![auto_fit](images/case01/image15.png)<P>

<span id="subtitle">Part 2:Hardware Connection </span><BR><P>

- Connect the LCD Display to the I2C.<P>

- Connect the AI Camera to I2C.<P>

![auto_fit](images/case01/image16.png)<P>

<span id="subtitle">Part 3: Programming </span><BR><P>

MakeCode: [ https://makecode.microbit.org/_XD0Jp68h13KK]( https://makecode.microbit.org/_XD0Jp68h13KK)
![auto_fit](images/case01/image17.png)<P>

<span id="subtitle">Part 4: AI Camera (Pre-setup)</span><BR><P>

a.Assembly step on how to screw the camera onto the greenhouse box

<span id="subtitle">Step 1</span><BR><P>
Screw the smaller component in the bracket pack onto the Huskylens 2
![auto_fit](images/case01/image18.png)<P>


<span id="subtitle">Step 2</span><BR><P>
Screw the larger component in the bracket pack onto Huskylens 2
![auto_fit](images/case01/image19.png)<P>


<span id="subtitle">Step 3</span><BR><P>
Screw the Huskylens 2 onto the box. Complete!
![auto_fit](images/case01/image20.png)<P>


b.Before programming, follow clear steps to train the model, ensuring the camera learns leaf colour as ID1 and reference point colour as ID2, so you feel ready to proceed confidently.


<span id="subtitle">Step 1</span><BR><P>
Set the edge of the plant pot model as the reference point by sticking a label to it
![auto_fit](images/case01/image08.png)<P>


<span id="subtitle">Step 2</span><BR><P>
Connect the HuskyLens 2 to the I2C port on the IoT: bit as shown below.
![auto_fit](images/case01/image21.png)<P>


<span id="subtitle">Step 3</span><BR><P>
The device will turn on automatically. Scroll the roller to switch into “Colour Recognition” mode. 
![auto_fit](images/case01/image22.png)<P>


<span id="subtitle">Step 4</span><BR><P>
Use the camera to focus on the leaf until there is a block around the plant, and make sure the crosshair is pointing to that block, and click the learn button, which is pointed by the arrow in the picture
![auto_fit](images/case01/image23.png)<P>


<span id="subtitle">Step 5</span><BR><P>
Use the camera to focus on the red label until there is a block around the red label, and make sure the crosshair is pointing to that block, and click the learn button, which is pointed by the arrow in the picture
![auto_fit](images/case01/image24.png)<P>


Remark:  Because it assigns the ID number based on the order of learning, you may need to click “Forget ID” and repeat Step 3 and Step 4 to learn them again if you got the wrong ID for either the leave colour or the label colour
![auto_fit](images/case01/image25.png)<P>


The leaf has to be at least 1.5 cm wide for detection. You may also add a label to the top of the plant and learn the label colour instead.

<span id="subtitle">Part 5: Final Result</span><BR><P>
![auto_fit](images/case01/image26.png)<P>

## Sentry

## KOI