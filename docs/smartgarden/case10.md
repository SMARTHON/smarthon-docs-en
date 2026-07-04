# AIoT Case 10:  Generating growth AI report

![pic](images/case10/image192.png)

## Goal
<HR>

By using n8n, we can connect to AI Agents to analyze plant growth status, generate corresponding reports, and send them to users via email.

## Background
<HR>

<b>How to Use n8n to Access AI Model for Plant Growth Monitoring</b><P>

n8n is an automation tool designed for connecting AI models and IoT devices, enabling users to monitor plant growth status and generate analysis reports automatically. With n8n, users can easily build automation workflows by utilizing a drag-and-drop interface to customize the process. Users can employ built-in nodes to access AI models, collect plant data and generate structured reports automatically.

<b>N8n AI Plant Monitoring and Report Generation Operation</b>

After setting up the workflow with the data collection node and AI model node, it will connect to the internet and communicate with the AI model via an API key. The plant growth data collected by the node will be sent to the AI model, while the AI model will return the analysis result to n8n for generating a growth report.

## Part List
<HR>

![pic](images/case10/case10-parts.png)<P>

## Assembly Steps
<!-- 
6. To start with, build the plant pot model with soil and seedling. Install the LCD Display during the build.

![pic](images/case10/imagepng)

7. Connect the Module Stand with the Pot base.

![pic](images/case10/imagepng)

8. Connect the Temperature and Humidity Sensor and Digital Light Sensor with a 3-pin and 4-pin module wire respectively. Install them on part C1, with the Digital Light Sensor above and the Temperature Humidity Sensor below the part.
![pic](images/case10/imagepng)
![pic](images/case10/imagepng)
![pic](images/case10/imagepng)

9. Connect the soil moisture sensor with a 3-pin module wire and put it into the soil.

![pic](images/case10/imagepng)

10. Put the model onto the pot tray and plastic mat. Completed\!

![pic](images/case10/imagepng) -->


## Hardware Connection
<HR>

<P>
1. Connect Temperature and Humidity Sensor to P1.  
<BR>
2. Connect Soil Moisture Sensor to P2.  
<BR>
3. Connect LCD Display to I2C.  
<BR>
4. Connect Digital Light Sensor to I2C.

![pic](images/case10/image28.png)


## Programming (MakeCode)
<HR>

MakeCode: [https://makecode.microbit.org/_UAWUtJhhTRkX ](https://makecode.microbit.org/_UAWUtJhhTRkX)   

![pic](images/case10/image126.png)<P>

## IoT (n8n)
<HR>

1. Go to [https://n8n.io/](https://n8n.io/)  register an account and login to the platform.

![pic](images/case10/image3.png)

<P>
2. Click “Create workflow”.

![pic](images/case10/image206.png)

<P>
3. Create first step by:  

* Select “add first step”.  

* Search “webhook”  

* Click it  

![pic](images/case10/image63.png)

<P>
4. Configure parameters:  

* HTTP METHOD:POST

* PATH:PlantGrowthStatusReport

Remember to paste the URL enter the makecode block.

![pic](images/case10/image40.png)

<P>
5. Configure AI Agent

![pic](images/case10/image111.png)

<P>
6. Configure AI Agent Parameters  

* Source for Prompt(user Message): Click “ Define below ”  

* Prompt ( user Message ): Paste the prompt:

![pic](images/case10/image185.png)

<P>
7. Then choose the LLM (Choose Deepseek as an exemple)  

* Click “Chat Model”

![pic](images/case10/image171.png)
![pic](images/case10/image86.png)

<P>
8. Configure LLM  

* Paste the API key here, you will see Connection tested successfully

![pic](images/case10/image120.png)

<P>
9. Configure Gmail message  

* Choose “send a message” ,then follow the steps:  

* Credential:login the email  

* Operation:Send  

* To:choose you Email  

* Subject:micro:bit IoT Bit 

![pic](images/case10/image21.png)
![pic](images/case10/image75.png)

<P>
10. Completed

![pic](images/case10/image209.png)

## Result
<HR>

Download the program to the micro:bit. Click “Execute workflow” in n8n. Press Button A on the micro:bit. After data is uploaded to the webhook, AI analysis will be completed automatically, and a growth report will be sent to your email.  
![pic](images/case10/image1.png)<P>

![pic](images/case10/image41.png)<P>