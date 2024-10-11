Seeed Studio XIAO ESP32S Sense and https://github.com/s60sc/ESP32-CAM_MJPEG2SD/ based backpack for pigeon tracking.

This uses an XIAO ESP32S Sense as the controller with an OV2640 camera module. To log GPS location an ATGM336H based module is connected to the serial port and for altitude a BMP280 is used connected to the I2C port. For power a single LiPo cell (around 400mAh to 1000mAh) is attached to the battery terminals on the bottom of the board. A heatsink is needed on the thermal pad on the bottom on the XIAO board as the ESP32 gets a bit toasty. A second heatsink on the camera is also worth while.


TODO draw diagram

If you have VSCode installed with PlatformIO, you can download this repo and import it put it in you PlatformIO projects folder and build and programme it with PIO.

Once the hardware is built and programmed put in an SD card and supply power (this can be through the USB port). Now it will write most of the necessary files to the SD card on first boot. It will not however write the html file you need for the web interface. There are 2 ways to get this onto theSD card. 
1. write the file yourself, (good if you are going to use this in standalone mode)
2. let it download it from the internet. (if you plan on using many of these and want to talk to them through a router)

Method 1.
After first boot there should be a folder called "data" on the SD card, into this folder add the file "MJPEG2SD.htm" which can be obtained from the "data" folder in this repo.

Method 2.
Once powered up a WiFi access point will appear with a name of the form "ESP-CAM_MJPEG_XXXXXXXXXXXX" where XXXXXXXXXXXX is a hex number. Connect to this with a device and navigate to http://192.168.4.1 - you will see a screen to input your credentials for your main wireless network. Enter these here and restart it. On next power cycle you can connect to it and interact with it.


If you have set it up to connect to the same network as you can connect to it by typing in http://ESP-CAM_MJPEG_X.local (where X is the first digit of the long number from before) into your browser or go to your router and find the IP address it has served it and connect to it that way.
If you are just connecting to it directly you can now simply go to http://192.168.4.1 in a browser.


 TODO write about setting up telemetry

 Logging of the atmospheric pressure is not enabled by default at the moment (must fix that). so to enable it go to Edit Config -> Peripherals and switch the "Use telemetry recording " switch. then click "Save". now power cycle the board.
