# YoloIP
![output image]( https://qengineering.eu/github/YoloIPAdGitAd.webp )
## A RPi 4 supporting multiple IP surveillance cameras with stand-alone AI.<br>
**With live feed, email notification and event-triggered GPIO/URL**.<br>

[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)<br/>

## Introduction.
YoloIP is a software package running on a Raspberry Pi 4.<br>
It transforms the RPi into a stand-alone AI-powered monitor.<br>
You can connect multiple commercial surveillance IP cameras to the Raspberry Pi.<br> 
A deep learning model detects objects in the camera scene.<br><br>
You can define what actions YoloIP performs when it recognizes an object.<br>
For instance, send you an email. Or activate one of its GPIO pins.<br>
At the same time, you can view your footage in any browser.<br><br>
Installation is simple. Just download the software and flash it to an SD card.<br>
Once inserted into your Raspberry Pi, everything works right away.<br>
The software comes with the latest Raspberry Pi Bullseye operating system.<br>
You don't need to be able to program. However, the used C++ source code is available on the image.<br><br>
Given the many hours of work, we ask you for a small one-time fee for the license (€ 17,50).<br>
See our [shop](https://qengineering.eu/shop.html) where we explain how the license works.<br><br> 
![output image]( https://qengineering.eu/github/YoloIPoverview2.webp )
> A red box is a recognized moving object. Blue boxes are recognized stationary objects.

------------

## Hardware.
To get the YoloIP working, you need the following hardware:
- A Raspberry Pi 4.
- An SD card (min 16 GB) holding all the software.

Obviously, you have some IP camera which you want to monitor.

------------

## Software.
For now, there is only one version of the YoloIP software, the _**GPIO**_ version.<br> 
This version activates the GPIO output pins when a recognized object triggers an event. The GPIO outputs act in real time.<br> 
At the same time it triggers an email to let you know which object is detected.<br>
There are live feeds in your browser. Finally, it has the possibility to trigger URLs.<br>
![output image]( https://qengineering.eu/images/EmailExampleYoloCam2.png )
> An example of a received email.

------------

## Downloading.
Select the desired version from the matrix below.

| Model  |  GPIO |
| ------------- | :-----:  |
| Raspberry Pi 4 | [image](https://ln5.sync.com/dl/b61741fd0/ac3uaijn-ic72agn8-65zi3b2u-9x7v63sg) | 

username: **pi**<br>
password: **3.14**

------------

## Flashing.
Once the file has been downloaded, you need to flash it to an SD card. Use a good quality SD with a minimum size of 16 GByte for this.<br>
On the [Raspberry Pi website](https://www.raspberrypi.com/documentation/computers/getting-started.html), you can follow the instructions on how to flash an image.<br><br>
Obviously, don't select a standard OS, but the file you just downloaded. For instance `YoloIP_Rpi4_GPIO.img.xz`.<br><br>
![output image]( https://qengineering.eu/images/FlashShopRpi.webp )<br><br>
Instead of the [Raspberry Pi Imager](https://downloads.raspberrypi.org/imager/imager_latest.exe), some people prefer [balenaEtcher](https://www.balena.io/etcher/). It doesn't matter, they all do a perfect job.

------------

## First boot.
Insert your fresh SD card into the slot and powerup your Raspberry Pi.<br>
Because you don't have a license yet, the YoloIP comes with a unique ID to buy the key.<br><br>
![output image]( https://qengineering.eu/github/YoloIPNoKey.png )<br><br>

------------

## Camera check.
At the same time it shows a most valuable tip; check your cameras!<br>
Not all the surveillance cameras support the used ONVIF protocol.<br>
Best to **check on the forehand** if your camera works. It would be a pity if you paid and then your camera turns out to be unusable.<br>
Our Wiki page [_connecting the camera_](https://github.com/Qengineering/YoloIP/wiki/Connect-the-camera) explains the procedure of how to get the footage from a surveillance camera in your Raspberry Pi.<br>
On the desktop, you find a README.pdf with the same instructions.<br><br>
![output image](https://qengineering.eu/github/TestIPcam2.webp)

------------

## License.
Follow the instructions and visit the [check out](https://qengineering.eu/checkout.php) site.<br><br>
![output image]( https://qengineering.eu/images/YoloCheckOut.webp )<br><br>
After a successful payment, you receive an email with the 8-digit key.<br>
The instructions on how to unlock the app are shown on the [congratulations page](https://qengineering.eu/congratulations.html).<br>
It is all very simple and self-explanatory.


------------

## Preparations.
Now that you have your license key, a few settings are required for YoloIP to work properly.<br/>
First of all, you need an internet connection. This [Wiki page](https://github.com/Qengineering/YoloIP/wiki/WiFi) explains how to set up the WiFi connection on your Raspberry Pi.<br><br>
Only if you like to use the email option you have to follow the next steps.
+ You need a Google account to redirect emails and save recorded clips. Since your personal login details are stored in the Raspberry Pi, we recommend a separate Google account for this application. Just for safety reasons.
+ Register your app with Google to get your email password. Follow the instructions on the Wiki page [Email notification](https://github.com/Qengineering/YoloIP/wiki/Email-notification) on how to set email traffic from your Raspberry Pi.
+ Alter the settings to your personal Google account. See for extra information on the Wiki page [Settings](https://github.com/Qengineering/YoloIP/wiki/Settings#settings).
  + `cam_name` Give a name to your YoloIP. Especially useful if you have more than one YoloIP working.
  + `email` The email address that receives the notifications. Note, `none` will block the mail traffic, but not the recording
  + `gmail` The Gmail address associated with the Google account above.


------------

## Triggers.
The real beauty of YoloIP lies in its ability to generate triggers when objects are detected.<br><br>
Each recognized object is tested to see if it should trigger an event.<br>
The event can set or reset an output pin and send you an email. It can even activate a user-defined URL.<br><br>
The Wiki page [Triggers](https://github.com/Qengineering/YoloIP/wiki/Triggers) gives you all the instructions you need to set the most sophisticated trigger events.<br><br>

------------

## Specs.

**Rpi 4** OS: Linux raspberrypi 6.1.21-v8+ #1642 Debian GNU/Linux 11 (bullseye) aarch64 GNU/Linux<br>

**AP (Average Precision)  - slow : 25.8 %**<br><br>
**AP (Average Precision)  - fast : 24.1 %**<br><br>
Keep in mind that no deep learning model is perfect. Given the limited computing power of the Raspberry PI, we had to make a compromise.<br>
Our network works amazingly well in everyday use. Even small objects in the background are recognized correctly. Likewise, half-cut objects at the edge of the image. Yet it sometimes makes mistakes. For example, misinterpreting a truck for a car or bus. An understandable error.<br><br>

| Resolution | Nr of cams | slow | fast | comment |
| ---------- | :-------:  | --: | --: | ---- |
| 1920x1080 | 1 | 2.0 FPS | 4.0 FPS  | |
| 1920x1080 | 2 | 0.75 FPS | 1.4 FPS  | POC errors |
| 640x480 | 1 | 6.0 FPS | 13.0 FPS | |
| 640x480 | 2 | 2.9 FPS |  6.2 FPS | |
| 640x480 | 3 | 1.7 FPS | 4.17 FPS | |
| 640x480 | 4 | 1.2 FPS | 2.9 FPS | |
| 640x480 | 5 | 0.9 FPS | 1.92 FPS | |
| 640x480 | 6 | 0.68 FPS | 1.52 FPS | |
| 640x480 | 7 | 0.45 FPS | 1.05 FPS | |
| 640x480 | 8 | 0.35 FPS | 0.82 FPS | |

The load will be approximately 1.1 Ampere

------------

## Final remarks.

- You can use slow and fast modes interchangeably. One camera in fast mode, the other in slow is therefore perfectly fine.
- Use small camera resolutions. Keep the amount of transferred memory from GPU to CPU for analysis as low as possible. The higher your FPS will be. 
- If possible, use an ethernet cable instead of a WiFi connection. A cable is more robust and much more reliable. 
