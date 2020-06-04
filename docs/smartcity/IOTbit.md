# Smarthon IoT:bit Introduction

## Introduction

![pic](images/Intro_01.jpg)

Smarthon IoT:bit is an WiFi extension board for micro:bit. With input/output ports, we can obtain information from different sensors for IoT and control the actuator (such as LED lights and servo)

## Structure Diagram
![pic_structure](images/structure_diagram.png)

## Pinout Table

|Module | Pin | Remark|
|:-- | :-- | :--|
|General|6V(battery holder)/ 5V(USB power supply)|-|
|-|GND|-|
|Buzzer|P0|-|
I/O (For Input and Output)|P0|-|
|-|P1|-|
|-|P2|-|
|-|P3| Also used by micro:bit LED|
|-|P4|Also used by micro:bit LED|
|-|P10|Also used by micro:bit LED|
|I/O (For Output only)|P6|Also used by micro:bit LED|
|-|P7|Also used by micro:bit LED|
|-|P9|Also used by micro:bit LED|
|-|P12|-|
|-|P13|-|
|-|P14|-|
|-|P15|-|
|Distance Sensor|P14 (TRIG)|-|
|-|P15 (ECHO)|-|
|Servo|S1|-|
|-|S2|-|
|-|S3|-|
|-|S4|-|
|WiFi|P16 (RX)|-|
|-|P8 (TX)|-|
|I2C|P19 (SCK)|-|
|-|P20 (SDA)|-|

## Getting Started: Add the extension
To Program Smarthon modules with micro:bit, you need to add the Smarthon IoT packages to the BBC micro:bit makecode platform and initialize it first. 

### Steps
1. Find the “Extensions” block at the bottom
![pic](images/ext_01.png)
&nbsp;
2. Search “https://github.com/gisellechan/test_wifi”
![pic](images/ext_02.png)
&nbsp;
3. Clicked “wifi-test” and you can see “IoT” package has been successfully.
![pic](images/ext_03.png)


<table id="cus_table">
  <tr>
    <th>Month</th>
    <th>Savings</th>
    <th>Savings for holiday!</th>
  </tr>
  <tr>
    <td rowspan="2">January</td>
    <td>$100</td>
    <td>$50</td>
  </tr>
  <tr>
    <td>February</td>
    <td>$80</td>
  </tr>
</table>
