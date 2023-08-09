# :loudspeaker: Dear people, it is still under construction :hammer:

# YoloIP
![output image]( https://qengineering.eu/github/YoloIPAdGitAd.webp )
## A Raspberry Pi 4, with stand-alone AI, supports multiple IP surveillance cameras. With live feed, email notification and event-triggered GPIO/URL.<br>

[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)<br/>

## Introduction.
YoloIP is a software package running on a Raspberry Pi 4.<br>
It transforms the Rpi into a stand-alone AI-powered monitor.<br>
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
- An SD-card (min 16 GB) holding all the software.

Obviously, you have some IP camera which you want to monitor.

------------

## Software.
For now there is only one version of the YoloIP software, the _**GPIO**_ version.<br> 
This version activates the GPIO output pins when a recognized object triggers an event. The GPIO outputs act in real-time.<br> 
At the same time it triggers an email to let you know which object is detected.<br>
There are live feeds to your browser. Finally, the GPIO version has the possibility to trigger URLs.<br>
![output image]( https://qengineering.eu/images/EmailExampleYoloCam2.png )

------------

## Downloading.
Select the desired version from the matrix below.

| Model  |  GPIO |
| ------------- | :-----:  |
| Raspberry Pi 4 | image | 

username: **pi**<br>
password: **3.14**

------------

## Flashing.
Once the file has been downloaded, you need to flash it to an SD card. Use a good quality SD with a minimum size of 16 GByte for this.<br>
On the [Raspberry Pi website](https://www.raspberrypi.com/documentation/computers/getting-started.html), you can follow the instructions on how to flash an image.<br><br>
Obvious, don't select a standard OS, but the file you just downloaded. For instance' `YoloIP_Rpi4_GPIO.img.xz`.<br><br>
![output image]( https://qengineering.eu/images/FlashShopRpi.webp )<br><br>
Instead of the [Raspberry Pi Imager](https://downloads.raspberrypi.org/imager/imager_latest.exe), some people prefer [balenaEtcher](https://www.balena.io/etcher/). It doesn't matter, they all do a perfect job.

------------

## First boot.
Insert your fresh SD card into the slot and powerup your Raspberry Pi.<br>
Because you don't have a license yet, the YoloIP comes with a unique ID to buy the key.<br><br>
![output image]( https://qengineering.eu/github/YoloIPNoKey.png )<br><br>
At the same time it shows a most valuable tip; check your cameras!<br>
Not all the surveillance cameras support the used ONVIF protocol.<br>
Best to **check on forehand** if your camera works. It would be a pity if you paid and then your camera turns out to be unusable.<br>
On the desktop you see a README.pdf with all the instructions on how to setup a camera connection.<br>

Follow the instructions and visit the [check out](https://qengineering.eu/checkout.php) site.<br><br>
![output image]( https://qengineering.eu/images/YoloCheckOut.webp )<br><br>
After a successful payment, you receive an email with the 8-digit key.<br>
The instructions on how to unlock the app are shown on the [congratulations page](https://qengineering.eu/congratulations.html).<br>
It is all very simple and self explanatory.


------------

## Preparations.
Now that you have your license key, a few settings are required for YoloIP to work properly.<br/>
First of all, you need an internet connection. [This page](https://github.com/Qengineering/RPi-image#wifi) explains how to set up the WiFi connection on your Raspberry Pi.<br><br>
Only if you like to use the email option, you need the following things to do.
+ You need a Google account to redirect emails and save recorded clips. Since your personal login details are stored in the Raspberry Pi, we recommend a separate Google account for this application. Just for safety reasons.
+ Register your app with Google to get your email password. Follow the instructions on the Wiki page [Email notification](https://github.com/Qengineering/YoloIP/wiki/Email-notification) on how to set email traffic from your Raspberry Pi.
+ Alter the settings to your personal Google account. See for extra information the Wiki page [Settings](https://github.com/Qengineering/YoloIP/wiki/Settings#settings).
  + `cam_name` Give a name to your YoloIP. Especially useful if you have more than one YoloIP working.
  + `email` The email address that receives the notifications. Note, `none` will block the mail traffic, but not the recording
  + `gmail` The gmail address associated with the Google account above.


------------

## Triggers.
The real beauty of YoloIP lies in its ability to generate triggers when objects are detected.<br><br>
Each recognized object is tested to see if it should trigger an event.<br>
The event can set or reset an output pin and send you an email.<br><br>
The Wiki page [Triggers](https://github.com/Qengineering/YoloIP/wiki/Triggers) gives you all the instructions you need to set the most sophisticated trigger events.<br><br>

------------

## Overlay.
A less-known fact about SD cards is that they only support a limited number of write cycles. Intense writing wears them out, for example, recording video clips. That's why we enabled recordings on an external USB stick. Or on your Google drive. Everything to limit writing to the SD card.<br><br>
The best way to protect your SD card from wear and tear is to use the Raspberry Pi overlay feature.<br>
With the overlay active, no writing to the SD takes place, only to RAM.<br>
Another advantage of the overlay is the protection of the SD card against sudden power cuts.<br>
If a power cut happens during a write cycle, it can corrupt the SD card. Worst case scenario, your Raspberry Pi stops functioning.<br><br>
All the more reasons to install an overlay. Please follow the instructions on the [Wiki page](https://github.com/Qengineering/YoloIP/wiki/Overlay).<br>
You might also read the [Wiki page](https://github.com/Qengineering/YoloIP/wiki/Recording) on recordings.<br>

------------

## Specs.

**Rpi 4 and 3B+** OS: Linux raspberrypi 5.15.84-v8+ #1613 Debian GNU/Linux 11 (bullseye) aarch64 GNU/Linux<br>
**Rpi Zero 2W** &ensp; OS: Linux raspberrypi 5.15.56-v7+ #1575 Debian GNU/Linux 11 (bullseye) armv7l GNU/Linux<br><br>

**AP (Average Precision) : 25.8 %**<br><br>
Keep in mind that no deep learning model is perfect. Given the limited computing power of the Raspberry PI, we had to make a compromise.<br>
Our network works amazingly well in everyday use. Even small objects in the background are recognized correctly. Likewise, half-cut objects that are on the edge of the image. Yet it sometimes makes mistakes. For example, misinterpreting a truck for a car or bus. An understandable error.<br><br>

| Model  | email | GPIO |  Load (Amp) |
| ------ | :--:  |  :--: | :--: |
| Raspberry Pi 4 | 3.7 FPS |  6.0 FPS  | 1.1 |
| Raspberry Pi 3B+ | 2.5 FPS | 3.15 FPS | 1.2 |
| Raspberry Pi Zero 2W | 2.25 FPS | 0.91 FPS  | 0.6 |
