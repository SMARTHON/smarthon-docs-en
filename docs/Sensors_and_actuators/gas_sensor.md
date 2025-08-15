Town gas sensor
==========
![](images/gas_sensor/gas_1.jpg)<br><br>

## Introduction
<HR>

Town gas sensor can detect town gas in the air through measuring the conductivity of surrounding air.<br><br>

## The principle
<HR>

Town gas sensor has a gas-sensing filament made of tin dioxide (SnO2), which has a low conductivity in clean air. When there is flammable gas surrounding the sensor, the conductivity of the filament rises along with the flammable gas concentration increases. <br>

![](images/gas_sensor/gas_2_2.gif)<br>

In clean air, oxygen (O2) is adsorbed on the SnO2 surface. With its high electron affinity, the adsorbed O2 attracts free electrons inside the SnO2, forming a potential barrier at the grain boundaries. This potential barrier prevents electron flow, causing high resistance in the sensor.<br>

When the sensor is exposed to flammable gas, an oxidation reaction occurs between such gas and the adsorbed O2 on the SnO2 surface. As a result, the density of adsorbed O2 on the SnO2 surface decreases, as does the height of the potential barrier. Electrons can easily flow through the reduced height barrier, thereby increasing the sensor’s conductivity and output voltage.<br>

Therefore, measuring the output voltage of the filament provides an indication of the concentration of any flammable gas in the environment. The sensor can detect a variety of flammable gasses and has high sensitivity to butane, propane and methane, of which methane is one of the main components of town gas.<br>


## Specification
<HR>

- Model: MQ-5
- Circuit voltage: 5V
- Heating consumption: ≤ 800mw
- Oxygen concentration: 21% (standard condition) Oxygen concentration can affect sensitivity
- Using Temperature: -10℃ ~ 50℃
- Storage Temperature: -20℃ ~ 70℃
- Sensing Resistance: 10KΩ ~ 60KΩ (5000 ppm methane )
- Standard detecting condition: Temp: 20℃±2℃ Vc: 5V±0.1<br>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp; Humidity: 65%±5% Vh: 5V±0.1
- Detecting concentration scope: 200-10000 ppm (LPG,LNG, Natural gas, iso-butane, propane, Town gas)<br><br>

##  Pinout Diagram
<HR>

|Pin|Function|
|---|---|
|G|Ground|
|V|Voltage Supply|
|S|Signal Input (Analog)|



##  Outlook and Dimension
<HR>

![](images/gas_sensor/gas_3.png)<br>
Size: 25mm X 35mm<br><br>

![](images/gas_sensor/gas_4.png)<br>
Diameter: 9.5mm ~ 19mm<br><br>

##  Quick to Start/Sample
<HR>

- Connect the Town gas sensor to the development board (direct plugin or using wire)
![](images/gas_sensor/gas_5.png)<br><br>

- Open Makecode, using the https://github.com/SMARTHON/pxt-advancedSensor PXT
![](images/gas_sensor/gas_6.png)<br><br>

- Initialize the OLED and show the Town Gas value on the OLED screen
![](images/gas_sensor/gas_7.png)<br><br>

## Result
<HR>

When the air is clean<br>
![](images/gas_sensor/gas_8.jpg)<br>

When there is town gas in the air<br>
![](images/gas_sensor/gas_9.jpg)<br>

## FAQ
<HR>

Q: Why is the sensor reading not 0 when there is no town gas surrounding?<br>
A: The sensor can detect not only town gas but also other flammable gas, so other flammable gas may be present in the air.<br><br>

## Datasheet
<HR>

[MQ-5 Datasheet](https://files.seeedstudio.com/wiki/Grove-Gas_Sensor-MQ5/res/MQ-5.pdf)
