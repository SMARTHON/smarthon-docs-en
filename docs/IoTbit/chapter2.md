# Chapter 2: Send Email by IFTTT


IFTTT is the way to connect hundreds of the apps and devices, including Twitter, Dropbox, Email, Google Assistant, etc. By the basic programming logic "if this then that", it connects IoT services through their API (application programming interface).<P> In IFTTT, you can make your own applet and link services together by "if this(trigger) then that(action)". For example, if we select webhooks (micro:bit button A) as trigger, Email (send email to your mailbox) as action. When micro:bit button A is pressed, it triggers (webhooks) and implement the action (send email) in IFTTT.<BR><P>
![auto_fit](images/Ch2/Ch2_des1.png)<P>
In this chapter, you will learn using micro:bit to activate trigger (webhooks). After that, it can implement other services (e.g. email)<BR><P>
![auto_fit](images/Ch2-Fix/Ch2-Fix_p8.png)<P>


## Coding (Makecode)
<HR>

<span id="subtitle" >Step 1: Connect WiFI</span><BR><P>
Before we try to use WiFi Control function, we need to connect to the network, we have already know how to connect to the WiFi on the first chapter. <BR><P>
![auto_fit](images/Ch2-Fix/Ch2-Fix_p1.png)<P>

<span id="subtitle" >Step 2: Get Device ID</span><BR><P>
`On WiFi connected` is an event handler. It will be triggered once after connected with WiFi. The handler will provide the `Device ID` variable which used to identify and control the Microbit. <P>
* Go to OLED Tab
* Snap `initialize OLED with width…height..` to `on start`
* Snap the `show string` inside the `On WiFi connected`
* Draw the `Device ID` variable from `On WiFi connected` to the `show string` block placeholder <BR><P>
![auto_fit](images/Ch2-Fix/Ch2-Fix_p1-1.png) <BR><P>

\*If you worried about forget the `Device ID` during program running, you may access it by the variable under Control tab
* Go to Control tab
* Snap the `Device ID` variable to the placeholder
![auto_fit](images/Ch2-Fix/Ch2-Fix_p3.png)<P>



<span id="subtitle" >Step 3: Send IFTTT request</span><BR><P>
When need to send IFTTT request, if `WiFi connected`, send data to IFTTT.
Input the following data of the IFTTT Application to the `Send IFTTT event name…` block <BR><P>

* `event_name`: event name to trigger in Webhooks (eg. SendEmail)
* `value 1-3`: if user want to add the value inside the email, click the add button and input value1, value2, value3 <BR>
<BR>

![auto_fit](images/Ch2-Fix/Ch2-Fix_p2.png)<P>




<span id="subtitle" >Step 4: Check IFTTT upload status</span><BR><P>
If you want to show the IFTTT upload status, you can use the “on IFTTT Uploaded” handler to check the variable. You may use the OLED to display the status and error code.<BR><P>
* Snap the `show string` inside the `On IFTTT Uploaded`
* Draw the variable from `On IFTTT Uploaded` to the `show string` block placeholder<P>

![auto_fit](images/Ch2/Ch2_p6.png)<P>



<span id="subtitle">Full Solution<BR><P>
MakeCode: [https://makecode.microbit.org/S72229-35443-84797-10160](https://makecode.microbit.org/S72229-35443-84797-10160)<BR><P>
You could also download the program from the following website:<BR>
<iframe src="https://makecode.microbit.org/S72229-35443-84797-10160" width="100%" height="500" frameborder="0"></iframe>

## IFTTT Configuration
<HR>
<H3>Goal:</H3>
Create applet<P>


<span id="subtitle" >Step 1</span><BR><P>
Go to [http://www.ifttt.com](http://www.ifttt.com), register an account and login to the platform<BR><P>
![auto_fit](images/Ch2-Fix/Ch2_ifttt1.png)<P>
<span id="subtitle" >Step 2</span><BR><P>
On the top right menu, click “Create” > “Applets”<BR><P>
![auto_fit](images/Ch2-Fix/Ch2_ifttt2.png)<P>
<span id="subtitle" >Step 3</span><BR><P>
* Select this
* Select Smarthon IoT 
* Input Device ID and Event Name. (eg. Device ID: 0x55a842e3477a, Event Name: SendEmail)
* Click “Create trigger” <BR><P>

![auto_fit](images/Ch2-Fix/Ch2-Fix_p5.png)<P>
<span id="subtitle" >Step 4</span><BR><P>
Select “That” > Email > Email<BR><P>
![auto_fit](images/Ch2-Fix/Ch2-Fix_p6.png)<P>
<span id="subtitle" >Step 5</span><BR><P>
Select “Send me an email” , Input email title and body, then click “Create action” <BR><P>
![auto_fit](images/Ch2-Fix/Ch2-Fix_p7.png)<P>




## Result
<HR>

After micro:bit is connected to WiFi and click button A, it will upload data to IFTTT.<BR><P>
If the upload is success, it will show `OK` with error code `0`<P>

![auto_fit](images/Ch2/Ch2_result1.png)<P>

If the upload is fail (such input wrong API key in this case), it will show `FAIL` with `error code`.<BR>
For the error 401, the user inputted the wrong API Key. For the error code -28674, there is no internet connection.<P>

![auto_fit](images/Ch2/Ch2_result1_1.png)<P>

When success, email will be sent to your mailbox by IFTTT.<BR><P>
![auto_fit](images/Ch2/Ch2_result2.png)<P>
