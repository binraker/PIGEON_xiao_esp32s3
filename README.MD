Seeed Studio XIAO ESP32S Sense based backpack for pigeon tracking.

This uses an XIAO ESP32S Sense as the controller with an OV2640 camera module. To log GPS location an ATGM336H based module is connected to the serial port and for altitude a BMP280 is used connected to the I2C port. For power a single LiPo cell (around 400mAh to 1000mAh) is attached to the battery terminals on the bottom of the board. A heatsink is needed on the thermal pad on the bottom on the XIAO board as the ESP32 gets a bit toasty. A second heatsink on the camera is also worth while.


TODO draw diagram

If you have VSCode installed with PlatformIO, you can download this repo and import it put it in you PlatformIO projects folder and build and programme it with PIO.

Once the hardware is built and programmed put in an SD card and supply power (this can be through the USB port). Now we need to let it get to the internet to download the latest version of the user web page you need to control it.

 Once powered up a WiFi access point will appear with a name of the form "ESP-CAM_MJPEG_XXXXXXXXXXXX" where XXXXXXXXXXXX is a hex number. Connect to this with a device and navigate to http://192.168.4.1 - you will see a screen to input your credentials for your main wireless network. Enter these here and restart it. Now if both you and the camera are on the same WiFi network you can connect to it by typing in http://ESP-CAM_MJPEG_X.local (where X is the first digit of the long number from before) into your browser.

 TODO write about setting up telemetry
 