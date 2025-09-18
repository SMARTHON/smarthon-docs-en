# Case 07: Smart Remote Control Musical Light

Level: ![level](images/level3.png)
![auto_fit](images/Case7/intro.png)<P>

## Sender

### Goal
<HR>

Create a remote controller to control the living room's musical light.<BR><P>

### Background
<HR>

<span id="subtitle">What is the Smart Remote Control Musical Light?
</span><P>
Nowadays, different electronic furniture can also be controlled remotely. In this case, it illustrates the concept of remote control in Smart Home. The home owner can control the room atmosphere in the living room by pressing the remote. (Change of music and light)
<BR><P>

<span id="subtitle">Principle of Remote (Sender)
</span><P>
-Micro:bit includes the radio function, allowing two or more Micro:bit to form a group and communicate in a small area. <BR> 
-In this case, this micro:bit sender (Remote) join group 1 with receiver. When we pressed the different button from micro:bit, it will send different message (mode) to another micro:bit so that the receiver will do the corresponding action. <BR>
-The message represent the mode which is "Funny", "Exciting" and "Stop Music".<BR><P>
![pic_90](images/Case7/Case7_flowchart1.png)<P>


<H3>Sender</H3>
### Part List
![pic_90](images/Case7/Case7_parts_2.png)<P>

### Assembly step
<HR>
N/A<P>

### Hardware connect
<HR>
N/A<P>

### Programming(Makecode)
<HR>

<span id="subtitle">Step 1. Connect to radio group</span><P>
* In `on Start`, put a `radio set group 1` to join the radio group 1
![auto_fit](images/Case7/Case7_p1.png)<P>

<span id="subtitle">Step 2. Send message to group</span><P>
* Snap `on button A pressed` to editor
* In `on button A pressed`, put a `radio send string funny` to send `funny` message to group 1 micro:bits
* Repeat the steps with minor changes on the trigger button and string to create other message sender for `excited` and `stop_music`
![auto_fit](images/Case7/Case7_p2.png)<P><P>

<HR>

<span id="subtitle">Full Solution<BR><P>

MakeCode: [https://makecode.microbit.org/S03594-89946-74148-89880](https://makecode.microbit.org/S03594-89946-74148-89880)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/S03594-89946-74148-89880" width="100%" height="500" frameborder="0"></iframe>

### Result
<HR>

After loaded program to micro:bit,<P>
When the press the button A, micro:bit sends the `funny` message to `group 1`.<P>
![auto_fit](images/Case7/case07_funny.png)<P>
When the press the button B, micro:bit sends the `excited` message to `group 1`.<P>
![auto_fit](images/Case7/case07_excited.png)<P>
When the press the button A and B, micro:bit sends the `stop_music` message to `group 1`.<P>
![auto_fit](images/Case7/case07_stop.png)<P>

### Think
<HR>
1. Other than press button, any other way to make the decision how to send the message?<P>

## Receiver

### Goal
<HR>

Create living room's musical light which controlled by remote.<BR><P>

### Background
<HR>

<span id="subtitle">Principle of Music and Light Player (Receiver) 
</span><P>
When this Micro:bit receives the message from the another Micro:bit (Remote), it will use the buzzer to play a different tone or music, at the same time, the multi-color LED will be changed to have better ambience. There are 3 modes, one is enjoyable mode, another is exciting mode, the last one is Stop Music.


![pic_100](images/Case7/Case7_flowchart2.png)<P>


### Part List
<HR>

![pic_90](images/Case7/Case7_parts_1.png)<P>



### Assembly step
<HR>

<span id="subtitle">Step 1</span><P>
In this case, build the “Big Style Model” as a home base.
<BR><P>
![pic_90](images/Case7/Case7_ass1.png)<P>

<span id="subtitle">Step 2</span><P>
To build a living room, put model E1 onto model A, align with the holes at model A and B3.
<BR><P>

![pic_90](images/Case7/Case7_ass2.png)<P>

<span id="subtitle">Step 3</span><P>
Attach the multi-color LED to the model B3 using M4\*10mm screws and nuts. And the connecting wire should be bended to the hole nearby.
<BR><P>

![pic_90](images/Case7/Case7_ass3.png)<P>

<span id="subtitle">Step 4</span><P>
To build a sofa model. Put the model K3 to the two sides of model K1.
<BR><P>

![pic_90](images/Case7/Case7_ass4.png)<P>

<span id="subtitle">Step 5</span><P>
Put model K2 all together to the cardboard parts (K1-K3).<BR><P>

![pic_90](images/Case7/Case7_ass5.png)<P>

<span id="subtitle">Step 6</span><P>
The sofa completed!<BR><P>

![pic_90](images/Case7/Case7_ass6.png)<P>

<span id="subtitle">Step 7</span><P>
Place the sofa at the living room.<BR><P>

![pic_90](images/Case7/Case7_ass7.png)<P>

<span id="subtitle">Step 8</span><P>
Put the model H as a decroration display on model B3.
<BR><P>

![pic_90](images/Case7/Case7_ass8.png)<P>

<span id="subtitle">Step 9</span><P>
Assembly completed!
<BR><P>

![pic_90](images/Case7/Case7_ass9.png)<P>

### Hardware connect
<HR>

1. Connect the Multi-Color LED to P1
2. Pull down the buzzer switch to bottom position

![pic_80](images/Case7/Case7_hardware.png)<P>

### Programming (MakeCode)

<HR>

<span id="subtitle">Step 1. Connect to radio group and initialize LED and music flag</span><P>
* Create a variable called `mode`
* In `on Start`, put a `radio set group 1` to join the radio group 1
* Initialize Multi-Color LED by `set strip to NeoPixel at pin P1 with 1 leds as RGB(GRB format)`
* Set the variable mode value to 0 by `set mode to 0`

![auto_fit](images/Case7/Case7_p3.png)<P>

<span id="subtitle">Step 2. Examine the radio message and take action</span><P>
* Snap `on radio received receivedstring` block to editor
* Put a nested `if-else` statement inside that block
* In the first condition, use `receivedstring = stop_music` to filter out the `stop_music` message, change the `mode` flag variable to `0`
* In the second condition, use `receivedstring = funny` to filter out the `funny` message, change the `mode` flag variable to `1`
* In the third condition, use `receivedstring = excited` to filter out the `excited` message, change the `mode` flag variable to `2`

![auto_fit](images/Case7/Case7_p4.png)<P>

<span id="subtitle">Step 3. Make the change color function</span><P>

* Create two function called `rainbow` and `flash`
* For each function, use `strip show color XXX` and `pause(ms) XXX` to fill in the pattern of color changes as you want

![pic_90](images/Case7/Case7_p5.png)<P>

<span id="subtitle">Step 4. Change LED color by the flag</span><P>

The color of LED should be change following by the flag

Flag | Meaning
 :| :  
0|stop_music
1|funny
2|excited

* Put a nested `if-else` statement inside the `Forever`
* Use `mode = 0` as the first condition
* In the first `if` segment, that's means `stop_music`, stop the playing sound by `stop all sounds`
* Turn off the LED by `strip show color black`
* Use `mode = 1` as the second condition
* In the second `if` segment, that's means `funny`, stop the playing sound by `stop all sounds`, then play a funny music with `start melody prelude repeating once`
* Execute the function to change to rainbow pattern by `call Rainbow`
* Use `mode = 2` as the third condition
* In the third `if` segement, that's means `excited`, stop the playing sound by `stop all sounds`, then play a excited music with `start melody chase repeating once`
* Execute the function to change to flash pattern by `call flash`

![auto_fit](images/Case7/Case7_p6.png)<P>


<HR>

<span id="subtitle">Full Solution<BR><P>


MakeCode: [https://makecode.microbit.org/_3PLEfo3pX5r4](https://makecode.microbit.org/_azUYbd8AuXY1)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_3PLEfo3pX5r4" width="100%" height="500" frameborder="0"></iframe><P>



### Results
<HR>

After loaded program to micro:bit,<BR>
When received the `funny` message, micro:bit will play the funny music and the light will show in rainbow mode.<BR>
When received the `excited` message, micro:bit will play the excited music and the light will show in flash mode.<BR>
When received the  the `stop_music` message, micro:bit will stop the music and turn off the light.
<BR><P>
![auto_fit](images/Case7/Case7_result.gif)<P>

### Think
<HR>

1. Apart from the built in melody, can you make your own music melody?
2. Can you control other hardware like a motor fan using radio control? 


