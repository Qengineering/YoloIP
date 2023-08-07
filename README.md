### How to connect your camera.
YoloIP works with IP cameras, which send their footage over ethernet via the RTSP protocol (Real Time Streaming Protocol).
Connecting the camera boils down to two questions: what is the IP address, and does it use a suitable RTSP protocol?
##### Preformance.
The GPU hardware process the H264/H265 video stremas. It frees up your CPU to do the AI tasks.<br>
At some point, however, frames must be transferred to the CPU domain to be processed. The larger your resolution, the more time-consuming the memory transfers from GPU to CPU are. The neural network only works with 416 x 416 images. The CPU reduces larger images to this size.<br>
In practice, a 640x480 stream requires only 4% CPU overhead, while a 1920x1080 consumes 30%. Needless to say, you can't expect to handle many cameras at this resolution.
On the other hand, with small 640 x 480 images, up to eight cameras still deliver acceptable performance. (~1FPS for each camera).<br><br>
Tip.<br>
Some IP cameras have two streams: high resolution and low resolution. If possible, connect the low resolution. It has a huge positive impact on the overall performance of the YoloIP app.
##### Find the IP address.
If you have a home brewed RTSP camera, for instance, a [Raspberry Pi streaming RTSP](https://qengineering.eu/install-gstreamer-1.18-on-raspberry-pi-4.html), you know the address in the network.<br>
To obtain the IP address of commercial surveillance cameras, is more difficult.<br>
We need the camera to support the ONVIF standard. Most popular cameras, like IMOU or Hikvision, do nowadays.
To get the IP address you need to connect the camera to your home network and start the ONVIFViewer tool.<br>
You can find the tool on our SD card.<br><br>
![output image]( https://qengineering.eu/github/ONVIF_menu.png )<br><br>
Or run:
```
$ flatpak run net.meijn.onvifviewer
```
Use the 'add' button (_**+**_) and let the program automatically scan the network for ONVIF cameras.<br><br>
![output image]( https://qengineering.eu/github/ONVIF_add.png )<br><br>
Once found, enter your username and password. It should show you a preview of when it succeeded.<br>
If no camera is listed then start to worry as it looks like you don't have an ONVIF compliant camera on your network. (Obviously if you have a Raspberry Pi streaming it will not be recognized as an ONVIF camera).<br><br>
![output image]( https://qengineering.eu/github/ONVIF_view.png )<br><br>
Now you have the IP address of the camera. The next step is to determine the pipeline giving you access to the video stream. A pipeline is a command line used by GStreamer or FFmpeg software to configure the connection to the camera. Usually, the camera manufacturer's service page or Google is the source used to get the information.
You can also use a Windows PC tool, the ONVIF Device Manager.<br><br>
![output image](https://qengineering.eu/github/ONVIF_device_manager.png)<br><br>
It works almost identically to the previous ONVIFViewer. This time you can see the used pipeline command in the status bar.<br>
Don't forget to log in with your username and password n the top left corner before scanning for devices.<br><br>
The last step is connecting to the camera with the found RTSP pipeline. We use the VLC payer as it's already on the Raspberry Pi.<br>
Go to the menu option `Open Network Stream...`<br><br>
![output image](https://qengineering.eu/github/VLC_stream_menu.png)<br><br>
Here, enters the pipeline proceed by the user name and password, as shown below.<br><br>
![output image](https://qengineering.eu/github/VLC_stream_address.png)<br><br>
Our IMOU camera also supports low-resolution streams. Instead of `subtype=0`, you can define `subtype=1`. Downscaling to 640 x 480 gives you 12 FPS when analyzed by YoloIP. Hence the comment that you can connect up to 8 cameras.<br><br>
![output image](https://qengineering.eu/github/IMOU_cropped.png)<br><br>


