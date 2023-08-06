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
You can find the tool on our SD card.<br>
![output image]( https://qengineering.eu/github/ONVIF_menu.png )<br>
Or run:
```
$ flatpak run net.meijn.onvifviewer
```
![output image]( https://qengineering.eu/github/ONVIF_add.png )<br>
![output image]( https://qengineering.eu/github/ONVIF_view.png )<br>

