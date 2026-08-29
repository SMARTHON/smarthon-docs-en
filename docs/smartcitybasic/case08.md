# IoT Case 08: Automated Traffic Light

Level: ![level](images/Case8/level5.png)

<span id="remarks">* For more details, please refer to “Chapter 5: Object to Object communication”</span>
![auto_fit](images/Case8/case-08_1.png)<P>

## Sender
<HR>

### Goal
<HR>

Make a sender to send signal to another micro:bit to show if there is traffic jam or not.<BR><P>

### Background
<HR>

<span id="subtitle">How to send signal to another micro:bit?</span><P>
Micro:bits can communicate with each other using their built-in Radio function. By setting both the sender and receiver to the same Radio Group, they can exchange messages instantly. When the sender detects a traffic jam (low light), it sends a radio string "trafficjam". When the road is clear, it sends "nojam".<BR><P>

<span id="subtitle">Sender micro:bit operation</span><P>
When the light value detected is low, it represents a traffic jam, and the sender sends a "trafficjam" radio message to the receiver. When the light value detected is high, it represents no traffic jam, and the sender sends a "nojam" radio message to another micro:bit.<BR><P>
![auto_fit](images/Case8/Concept-diagram-Case8_sender.png)<P>

### Part List
<HR>

![auto_fit](images/Case8/Case8a_parts.png)<P>

 
### Assembly step
<HR>

N/A

### Hardware connect
<HR>

Connect the Light Sensor to P0 port of Basic:bit<BR><P>
![auto_fit](images/Case8/Case8a_hardware.png)<P>

*Pull the buzzer switch 'up' to disconnect the buzzer in this execrise*

### Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize Radio Group and variable</span><P>
* Snap `Radio set group 1` from the `Radio` category to the `on start` block.
* Set `variable` `light2` to 0 from the `Variables` category. <P>
![auto_fit](images/Case8/Case8a_p3_1.png)<P>

<span id="subtitle">Step 2. Check traffic status</span><P>
* Set `variable` `light2` to `get light sensor value from pin P0`.
* Snap `show number` from the `Basic` category to display the value of `light2` on the micro:bit LED matrix.
* Set `pause (ms)` to `1000` for the next checking.
![auto_fit](images/Case8/Case8a_p3.png)<P>

<span id="subtitle">Step 3. Send notification based on traffic status</span><P>
* Snap an `if statement` into the `loop`.
* Set the condition to `light2` `<` `10` (to detect a traffic jam).
* `If true`: Snap Radio `send string "trafficjam"` from the `Radio` category.
* Set `else-condition` (traffic jam is not detected)
* Else: Snap Radio send string "nojam" from the `Radio` category.<p>
![auto_fit](images/Case8/14.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: <a href="https://makecode.microbit.org/_c47HLick1T6p" target="_blank">https://makecode.microbit.org/_c47HLick1T6p</a>

You could also download the program from the following website:<BR>
![auto_fit](images/Case8/Case8a_full_program.png)<P>

### Result
<HR>

The light sensor is used to detect the traffic status. When the light intensity is low (sensor is covered), it indicates a traffic jam, and a radio message "trafficjam" will be sent to the receiver micro:bit. When the light intensity is high, it indicates no traffic jam, and a radio message "nojam" will be sent.<BR><P>
 ![auto_fit](images/Case8/Case8a_result1.png)<P>
Once the light intensity is too low, it indicates that there is a traffic jam on the road. A radio message "trafficjam" will be sent to another micro:bit (receiver).<BR><P>
![auto_fit](images/Case8/Case8a_result2.png)<P>

### Think
<HR>

Q1. How can we use distance sensor to detect traffic status?<BR><P>

## Receiver
<HR>

### Goal
<HR>

<BR><P>

### Background
<HR>

<span id="subtitle">How to receive a signal from another micro:bit?</span><P>
Micro:bits (sender and receiver) are set to the same Radio Group so messages can be sent between them instantly. If the receiver micro:bit receives a radio message "trafficjam" from the sender, the connected traffic light will turn red.<BR><P>

<span id="subtitle">Receiver micro:bit operation</span><P>
When a radio message "trafficjam" is received, it means there is a traffic jam ahead. The traffic LED Module will turn red. When a radio message "nojam" is received, it means there is no traffic jam. The traffic LED Module will turn green. By using a smart traffic light, traffic congestion can be reduced through automatic traffic control.<BR><P>
![auto_fit](images/Case8/Concept-diagram-Case8_receiver.png)<P>

### Part List
<HR>

![auto_fit](images/Case8/Case8b_parts.png)<P>

## DIY Installation & Mounting

<span id="subtitle">1. Materials: Cardboard , scissors and tape.</span><BR><P>
![auto_fit](images/Case8/1.png)<P>

<span id="subtitle">2. Make the holes:</span><BR><P>
![auto_fit](images/Case8/2.png)

<span id="subtitle">3. Finished look:</span><BR><P>
![auto_fit](images/Case8/3.png)

*You can buy the material set from smarthon website.

### Hardware connect
<HR>

Connect the Traffic LED Module to P0 port of IoT:bit<BR><P>
![auto_fit](images/Case8/Case8b_hardware.png)<P>


### Programming (MakeCode)
<HR>

<span id="subtitle">Step 1. Initialize System (on start)</span><P>
* Snap `Radio set group 1` to `on start`.
* Set `variable` `oldmsg` to `"" (empty text)` from the `Variables` category. 
* Call `function` `TurnGreen` to set the initial state of the traffic light. 

![auto_fit](images/Case8/Case8a_p1.png)<P>

<span id="subtitle">Step 2. Set up Radio Receiver block</span><P>
* Snap the `event block` `on radio received` (receivedString) from the `Radio` category to the workspace.
* Snap `show icon (tick)` inside the block to provide visual feedback when a signal is received.

![auto_fit](images/Case8/Case8b_p2.png)<P>

<span id="subtitle">Step 3. Set up a new function (TurnRed)</span><P>
* `Control traffic light` at `P1` `green on` from SmartCity > Output
* `Pause for 2000ms` from `basic
* `Control traffic light` at `P1` `yellow on`, `pause for 2000ms`
* `Control traffic light` at `P1` `red on` and `pause for 2000ms`.

![pic_70](images/Case8/Case8b_p3.png)<P>
 
<span id="subtitle">Step 4. Set up a new function (TurnGreen)</span><P>
* `Control traffic light` at `P1` `red on` from SmartCity > Output
* `Pause for 2000ms` from `basic`
* `Control traffic light` at `P1` `red and yellow on`, `pause for 2000ms`
* `Control traffic light` at `P1` `green on` and `pause for 2000ms`.
![auto_fit](images/Case8/Case8b_p4.png)<P>

<span id="subtitle">Step 5. Change traffic light status with logic.</span><P>
* Snap an `if statement` into the `on radio received` block. Set the `condition` to `receivedString ≠ oldmsg`.
* Inside this block, set `oldmsg = receivedString` to update the latest traffic status.
* Snap a `nested if...else if statement` inside:
* If `receivedString == "trafficjam"`, call function `TurnRed`.
* `Else if receivedString == "nojam"`, call function `TurnGreen`.

![auto_fit](images/Case8/Case8b_p5.png)<P>

<span id="subtitle">Full Solution<BR><P>
MakeCode: <a href="https://makecode.microbit.org/_A4zCu0fuKY6f" target="_blank">https://makecode.microbit.org/_A4zCu0fuKY6f</a>

![auto_fit](images/Case8/Case8b_full_program.png)<P>


### Result
<HR>

By receiving radio messages, the traffic LED module will turn to the corresponding color automatically. If there is no traffic jam ahead (detected by the light sensor), the sender micro:bit will send the radio message "nojam" to the receiver, and the traffic light will turn green. If there is a traffic jam ahead, the sender will send the radio message "trafficjam", and the receiver will turn the traffic light red.
<BR><P>
![auto_fit](images/Case8/Case8b_result.gif)<P>

### Think
<HR>

Q1. How can we add sound effect to the traffic LED Module according to the corresponding color?<BR><P>
