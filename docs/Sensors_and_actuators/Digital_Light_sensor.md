# Digital Light Sensor (BH1750)

![pic_40](images/digital_light/Digital_Light_Sensor_0_1.jpg)


## Introduction

Digital Light Sensor (BH1750) uses a photodiode to measure ambient light. The photodiode consumes light energy to produce an electric current. The electricity produced by photodiodes is proportional to the intensity of light. The illuminance values are in LUX. <P>


## The principle

A photodiode is a PN-junction diode. There is a region called depletion region at the interface between P-type and N-type. <P>
![auto_fit](images/digital_light/Digital_Light_Sensor_1.jpg)

Light carries energy in the form of small energy packets called Photons. When the depletion region is illuminated by photons of energy enough to break covalent interatomic bonds, it creates a pair – an electron(black spots in figure), and a hole(white spots in figure). Electrons continue flowing down the wire to the voltage source, and to the P-type. The holes cannot move in wires, so they recombine with incoming electrons at the P-type. The photocurrent generated will be converted into voltage, then from analog values into digital values, finally output illuminance in LUX. <P>


## Specification

* Name: BH1750FVI-TR
* Peak Wavelength: 560 nm
* Operating Temperature: - 40℃ ~ 80℃
* Operating Supply Voltage: 3V (3-3.6V)
* Supply Current: 120μA (max: 190μA) when Ev = 100 lx
* Powerdown Current: 0.01μA (max:1.0μA) when no input Light
* Power Dissipation: 260 mW
* Output: Digital 16bit


## Pinout Diagram

|Pin|Function|
|--|--|
|G|Ground|
|V|Voltage Supply|
|SDA|Data|
|SDL|Clock|


## Outlook and Dimension

![pic_40](images/digital_light/Digital_Light_Sensor_2_1.png)


Size: 25mm X 25mm

## Quick to Start/Sample

* Connect the digital light sensor to development board (using wire) <P>
![pic_60](images/digital_light/Digital_Light_Sensor_3_1.png) <P>

* Open Makecode, using the [https://github.com/SMARTHON/pxt-smartplant](https://github.com/SMARTHON/pxt-smartplant) PXT <P>
![pic_80](images/digital_light/Digital_Light_Sensor_4.png) <P>

* Show the light intensity on the OLED <P>
![auto_fit](images/digital_light/Digital_Light_Sensor_5.png) <P>


## Result

The light intensity showing on the OLED screen <P>
![auto_fit](images/digital_light/Digital_Light_Sensor_6.png)


## FAQ

Q: What is the difference between digital light sensor(BH1750) and light dependent resistor(LDR)? <BR>
A: BH1750 has high accuracy and precision; LDR has less precision. <BR>
The output unit of BH1750 is lux(lx). LDR output in the form of change of resistance value(ohms). <BR>
LDR is cheaper than BH1750.

Q: What is the output range of a digital light sensor(BH1750)? <BR>
A: The output range is 1 - 65535 lx.


## Datasheet

[BH1750FVI-datasheet](https://www.mouser.com/datasheet/2/348/Rohm_11162017_ROHMS34826-1-1279292.pdf)
