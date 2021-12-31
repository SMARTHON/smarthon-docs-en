# Case 04: Toilet Water Leakage Detection System

Level: ![level](images/level2.png)
![auto_fit](images/Case4/blank.png)<P>

## Goal
<HR>

Make a toilet water leakage detection system by checking the conductivity of device connected.<BR><P>

## Background
<HR>

<span id="subtitle">What is a toilet water leakage detection system?</span><P>
Toilet water leakage detection system is a system that can trigger alert upon unwanted water leakage situations.<BR><P>

<span id="subtitle">What is an Electrical circuit?</span><P>
Electrical Circuit is one of basic concepts in electronic engineering, when something can let electric current pass through, it builds up a circuit.<P>
Generally, a circuit will have two states, if the circuit is complete, able to let the current pass, it is called closed circuit. If the circuit has a breakpoint, and cannot let the current pass, it becomes an open circuit.<p>
However, how to let the current pass through? It is related to the material of the circuit. All the materials have their own physical property, one of property is conductivity. If the conductivity is high enough, it is called a conductor and able to let the current pass through easier, in opposite, if the conductivity is low, it is called an insulator which will stop the current pass through.<P>
In daily life, metal usually has a high conductivity, so the electric wires are made of copper. In addition, some ionic material such as tap water also takes the same property, able to become a conductor to build a circuit.
<BR><P>

<span id="subtitle">Toilet water leakage detection system principle</span><P>

The system will consist of two crocodile clips each with one side connected to the board, one installed to the place of detection, with two clips physically disconnected. Air is an excellent insulator, so the circuit will become open circuit.  When water is leaked around that area, the water will replace the air between two clips, thus becoming a closed circuit, electricity will flow between the Board's detection Pin and ground Pin. It will trigger the detection to make the water leakage be detected and the system will send an alert.
<BR><P>

![pic_70](images/Case4/Blank.png)<P>


## Part List
<HR>

![pic](images/Case4/Blank.png)<P>

## Assembly step
<HR>

<span id="subtitle">Step 1</span><P>
Connect the crocodile clip to P1 and GND.<BR><P>
![pic](images/Case4/Case4_ass1.png)<P>
<span id="subtitle">Step 2</span><P>
Put the clip to the level which need to detect water<BR><P>
![pic](images/Case4/Case4_ass2.png)<P>

## Hardware connect
<HR>

1. Connect the two crocodile clip cables to P1 and GND
2. Put the two clip at the detection level on sink
3. Pull down the buzzer switch to connect the buzzer


![pic](images/Case4/Case4_hardware.png)<P>

## Programming (MakeCode)
<HR>

<span id="subtitle">Step 1</span><P>
<span id="subtitle">Step 1. Check the Pin state</span>
* In `Forever`, put a `if` statement
* Put `pin P1 is pressed = true` as condition
![auto_fit](images/Case4/Case4_p1.png)<P>

<span id="subtitle">Step 2. Alert warning</span><P>
* If in `if` segment, that's means the water was connected two clips
* Use `play tone High A for 2 beat` to play warning sound
![auto_fit](images/Case4/Case4_p2.png)<P>


<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/_bPw0ViLrR6Jm](https://makecode.microbit.org/_bPw0ViLrR6Jm)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/#pub:_bPw0ViLrR6Jm" width="100%" height="500" frameborder="0"></iframe>


## Results
<HR>

When the water level rises to the crocodile clip’s position, the warning sound is triggered to warn the user.<BR><P>
![pic](images/Case4/Case4_result.png)<P>

## Think
<HR>

Q1. Apart from the warning by buzzer, any other method can be used to notify the house owner? i.e. showing red LED<BR><P>
