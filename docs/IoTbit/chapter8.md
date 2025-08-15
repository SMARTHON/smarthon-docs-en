# Chapter 8: HTTP Function

HTTP stands for Hypertext Transfer Protocol. It's the foundation of data communication for the World Wide Web. HTTP functions as a request-response protocol in the client-server computing model. It's used for transferring hypermedia documents, such as HTML pages, images, and other resources, between a web browser (client) and a web server. HTTP works by a client sending a request to a server, and then the server responding with the requested resource along with an HTTP status code that indicates the success or failure of the request. In this chapter, you will learn how to send a HTTP request and receive the response with Iot:bit.<br>

![](images/Ch8_new/HTTP_intro.png)<br>

| Method | With Body | Without Body |
| -- | -- | -- |
| Get | #Body will not be sent out and will be ignored finally | work properly |
| POST | work properly | *Empty string “” body will be sent out instead |

<b># The HTTP specification said that using HTTP GET to include the body is not a good idea.</b><br>
<b>* This will only be supported after firmware version 4.2 </b><br>

## Scenario Example
<HR>

<span id="subtitle">Goal:<BR><P>
This example is to obtain string content from the server via HTTP.<br>

<span id="subtitle">Description:<BR><P>
In this example, there are 2 parts involved.<br>

- In part 1, we need to create a HTTP server that carries strings.<br>
- In part 2, we program the micro:bit to send a HTTP request and receive the response from the server.<br>

![](images/Ch8_new/HTTP_scenario.png)<br>

## Part 1: Create HTTP API Server
<HR>

<span id="subtitle">Goal:<BR><P>
We use a free server service to set up a server containing string content for testing.<br>

<span id="subtitle">Step 1<BR><P>
Go to [https://ptsv3.com](https://ptsv3.com). Enter a unique ID to find an unclaimed toilet (access path), such as “smarthon”. <br>

![](images/Ch8_new/http_3.png)<br>

<span id="subtitle">Step 2<BR><P>
Modify the configuration so that the server returns a response in JSON format. After modification, click “Update Toilet Config” <br>

![](images/Ch8_new/http_4_1.png)<br>

Example JSON:<br>
{"server":"ptsv3","user":"smarthon","msg":{"date":"19/4/2024","time":"13:00","content":"hello"}}<br>

![](images/Ch8_new/http_14.png)<br>

## Part 2: Coding
<HR>

<span id="subtitle">Goal:<BR><P>
Send an HTTP request to the server and extract the content<br>

<span id="subtitle">Step 1: Connect WiFi<BR><P>
- Before we get the content, we need to connect to the network. We already know how to connect to the WiFi in the first chapter.<br>
![](images/Ch8_new/http_5.png)<br>

<span id="subtitle">Step 2: Copy URL<BR><P>
- Copy the Post URL by right clicking -> copy link
![](images/Ch8_new/http_6.png)<br>

<span id="subtitle">Step 3: Using POST method to update the Data<BR><P>
- Snap a `on button A pressed` to editor<br>
- Go to IoT:bit -> IoT Services and snap `Send HTTP Request`<br>
- Paste URL into the block<br>
- We use POST in this example<br>

**Put your data into the body**
- Example JSON:<br>
- {"server":"ptsv3","user":"smarthon","msg":{"date":"21/07/2025","time":"12:00","content":"hello"}}<br>
- The time and the day have been changed.<br>
![](images/Ch8_new/http_7.png)<br>

<span id="subtitle">Step 4: Using GET method to get the data<BR><P>
- Snap a `on button B pressed` to editor<br>
- Go to IoT:bit -> IoT Services and snap `Send HTTP Request`<br>
- Paste URL into the block<br>
- We use GET in this example, so leave the Body empty<br>
![](images/Ch8_new/http_8.png)<br>

<span id="subtitle">Step 5: Create a response handler<BR><P>
Go to IoT:bit -> IoT Services and snap `On HTTP received` to editor
Display `HTTP_Status_Code` on OLED<br>
![](images/Ch8_new/http_9.png)<br>

<span id="subtitle">Step 6: Setup a JSON extractor function<BR><P>
- Go to IoT:bit -> IoT Services and snap `Get value of Key`<br>
- Fill in the Key name according to the JSON <br>
- Draw the `Data` to `JSON String`<br>
![](images/Ch8_new/http_10.png)<br>

- When need to access the Multi-level JSON, nest the blocks until you access the target level<br>

![](images/Ch8_new/http_11.png)<br>

- Remark: The `HTTP_Status_Code` returns a code representing the sending result, such as 200(OK), 404(Not found), 502 (Bad Gateway), more information at [https://developer.mozilla.org/en-US/docs/Web/HTTP/Status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)<br>



## Full Solution
<HR>

MakeCode: [https://makecode.microbit.org/S67494-15951-48626-85113](https://makecode.microbit.org/S67494-15951-48626-85113)<br>
You could also download the program from the following website:<br>
<iframe src="https://makecode.microbit.org/S67494-15951-48626-85113" width="100%" height="500" frameborder="0"></iframe>

## Result
<HR>

After connecting to Wifi, press button A, it will POST the body information into the webserver, and change the body part. If the server body part has any changes, press the button B, it will GET the body information into the microbit.<br>
![](images/Ch8_new/http_13.png)<br>
![](images/Ch8_new/http_16.png)<br>
![](images/Ch8_new/http_14.jpg)<br>