# PH Sensor (E-201-C)

![](images/PH_sensor/PH_sensor_1.png)

## Introduction

PH sensor is a commonly used sensor to detect the PH value of a solution. It can be used in aquariums, hydroponics, laboratories etc. It consists of a PH probe and a Signal Condition Board.<p>

## The principle

The PH probe can be used to measure the acidic intensity of liquid solution, as it turns a voltage proportional to the PH value of the solution, which means the PH value can be determined by the number of output voltages. <p>

A PH meter uses a PH probe to measure the acidity or alkalinity (hydrogen-ion activity) of a solution, expressed as pH. The pH value of a solution is related to the hydrogen ion ratio inside the pH probe and the solution being tested.<p>

![](images/PH_sensor/PH_sensor_2.png)<br>
![](images/PH_sensor/PH_sensor_3.png)<p>

Depend on the model of different PH sensor, the output voltage value and curves have difference, but all follow the principle:<br>
When the value of output voltage increases, the PH value will decrease.<br>
When the value of output voltage decreases, the PH value will increase.<br>

### <u>Important Notice:</u>

Because the measuring electrode is usually glass and quite fragile, there are some cleaning guideline you need to follow in order to protect the PH electrode:<br>
1. Do not “wipe” or rub the electrode.
2. Swirl the electrode gently in the cleaning solution.
3. Gently rinse with deionized or distilled water.
4. Store in a storage solution.
5. When possible, use a specialized electrode.

For a cleaning solution, please use the appropriate solution depending on your particular process and the residues you are trying to remove. There are a wide range of pre-mixed cleaning solutions available online or you can make your own. Make sure you take care when handling any cleaning solution, as some can be hazardous so make sure you follow all safety instructions and wear appropriate protective equipment.<p>

## The Ph scale for common items

![](images/PH_sensor/PH_sensor_4.png)<br>

## Specification
- Supply Voltage: 5V
- Interface: Analog
- Working Current: 5-10mA
- Working Temperature: -10-50 °C
- Working Humidity: 95%RH (nominal humidity 65%RH)
- Detection Range of Temperature: 5-60 °C
- Internal Resistance: <250 MΩ (When 25°C)
- Response Time:: ≤ 5S
- Stability Time: ≤ 60S
- Power Consumption: ≤ 0.5W

The relationship between ph value and voltage:<br>
![](images/PH_sensor/PH_sensor_5.png)<p>

| Voltage | PH value |
| -- | -- |
| 2.272487971 | 1 |
| 2.394921459 | 2 |
| 2.517354947 | 3 |
| 2.639788435 | 4 |
| 2.762221923 | 5 |
| 2.884655411 | 6 |
| 3.007088899 | 7 |
| 3.129522387 | 8 |
| 3.251955875 | 9 |
| 3.374389363| 10 |
| 3.496822851| 11 |
| 3.619256339| 12 |
| 3.741689827| 13 |

## Pinout Diagram

| Pin | Function|
|--|--|
| G | Ground|
| V | Voltage Supply|
| S | PH Value Output|

## Outlook and Dimension

**Signal Conditioning Board**<br>
![](images/PH_sensor/PH_sensor_6.png)<br>
Size: 62mm * 40mm * 14mm<br>

**PH Probe**<br>
![](images/PH_sensor/PH_sensor_7.png)<br>

Size: 166mm * 20mm * 20mm (with 80cm cable)<br>

## Quick to Start/Sample

**<u> Best Practice </u>**
- Connect the signal condition board to the development board. (direct plugin or using wire)<br>
- Connect the PH Probe to the signal condition board.<br>

![](images/PH_sensor/PH_sensor_8.png)<br>
- Add the smart city extension first
- Open MakeCode, using the [https://github.com/SMARTHON/pxt-smartscience](https://github.com/SMARTHON/pxt-smartscience) PXT<br>

![](images/PH_sensor/PH_sensor_9.png)<br>

- Inside on start, initialize the OLED.
- Inside forever, show the reading of PH value output, and also the voltage if you want.<br>

![](images/PH_sensor/PH_sensor_13.png)<p>

### <u>Calibration:</u>

If the value of ph value is strongly violate its expected result, there are three measures you can do :<br>
- You can clean the probe first by using the cleaning solution. (Soaking it into KCl solution for about 8-12 hours can help the probe calibration)<br>
![](images/PH_sensor/PH_sensor_14.jpg)<p>

- You can adjust the screw on the signal board and check the newest data.(For slightly adjustment)<br>
![pic_70](images/PH_sensor/PH_sensor_15.png)<p>

- If you have done the first two methods and the data is still not correct, you can simply add some offset to the pH value to make it back to a normal value range, setting offset is normal as different conditions can affect the result strongly such as the temperature or concentration of the liquid. We suggest setting the offset to -1.9 but adjustment may be needed as mentioned above.<br>
![](images/PH_sensor/PH_sensor_16.png)<p>

## Result

 The PH value of the solution is showing on the OLED screen. If you move the probe from one solution to another, it may need some time to adjust its ph value.<br>
![](images/PH_sensor/PH_sensor_17.jpg)<p>

## FAQ

Q: What is the value shown if the probe is placed in the air?<br>
A: The PH value of air should be around 5.7.<p>

Q: What is the value shown if the probe is placed in tap water?<br>
A: The PH value of air should be around 7.5.<p>

Q: Why is there a slight difference in Ph value when I transfer the sensor from one solution to the other?<br>
A: The sensor may still contain some solution from the previous container, make sure you wash with tap water to reduce the amount of different solutions on the sensor.<p>

## Datasheet
[E-201-C Data sheet](https://www.e-gizmo.net/oc/kits%20documents/PH%20Sensor%20E-201-C/PH%20Sensor%20E-201-C.pdf)