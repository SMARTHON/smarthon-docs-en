# Water quality ( TDS Sensor )

![](images/water_quality/water_quality_1.jpg)

## Introduction

The TDS (Total Dissolved Solids) sensor measures the concentration of dissolved solids in water, providing an indicator of water quality the unit is ppm (mg/L). It is widely used by hobbyists, engineers, and researchers to assess the purity of water for various applications. *** But it does not show how dirty the water is. ***

![](images/water_quality/water_quality_2.png)<br>

## The principle

The TDS sensor operates by measuring the electrical conductivity of water, which correlates with the concentration of dissolved ions. Higher conductivity indicates a higher TDS level, reflecting increased dissolved solids such as salts, minerals, and metals.<br>

![](images/water_quality/water_quality_3.png)<br>

## Specification

- Input Voltage: DC 3.3 ~ 5.5V
- Output Voltage: 0 ~ 2.3V
- Working Current: 3 ~ 6mA
- TDS Measurement Range: 0 ~ 1000ppm
- TDS Measurement Accuracy: ± 10% F.S. (25 ℃)
- Module Interface: XH2.54-3P
- Electrode Interface: XH2.54-2P

## Pinout Diagram

| Pin | Function |
| -- | -- |
| G | Ground |
| V | Vlotage Supply |
| S | Signal (Analog) |

## Outlook and Dimension

![](images/water_quality/water_quality_4.png)<br>
Size: 40mm X 25mm<br>

![](images/water_quality/water_quality_5.png)<br>
Long: 600mm<br>

## Quick to Start/Sample

- Connect the module to development board (direct plugin or using wire)
![](images/water_quality/water_quality_6.png)<br>

- Open Makecode, using the [https://github.com/SMARTHON/pxt-smartcity-extension](https://github.com/SMARTHON/pxt-smartcity-extension) PXT
![](images/water_quality/water_quality_7.png)<p>

- Initialize the OLED and show the concentration of different dust value on the OLED screen
![](images/water_quality/water_quality_8.png)<br>

## Result
![](images/water_quality/water_quality_9.jpg)<br>

## FAQ

**Q: Why are my readings unstable or does the value look unnormal?**<br>
A: Ensure the probe is clean and submerged properly; temperature changes can also affect accuracy.

## Datasheet
[TDS sensor](https://www.bestmodulescorp.com/tc/amfile/file/download/file/1732/product/1134/?srsltid=AfmBOorN766C6i9UkKeyPAsylm0YU3SbT_JzhDmmNrRAFrksDbRt0jWI)