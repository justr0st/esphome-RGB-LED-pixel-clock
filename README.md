
# Pixel clock for ESPhome

Simple ESPHome pixel clock based on WS2812b lightstrip with 17x5 display. [![YouTube](https://img.shields.io/badge/YOUTUBE-VIDEO-red)](https://youtube.com/shorts/Wsp6U6bym74)
![front](https://github.com/justr0st/esphome-RGB-LED-pixel-clock/blob/main/Images/LED_Clock_front.jpg?raw=true)
![side](https://github.com/justr0st/esphome-RGB-LED-pixel-clock/blob/main/Images/LED_clock_side.jpg?raw=true)


## Preparation
Materials needed:
  * Wemos D1 Mini ([example](https://www.amazon.de/gp/product/B0754N794H/))
  * WS2812b LED strip IPx0 without protective coating (100 LEDs/m) ([example](https://www.amazon.de/gp/product/B088FJLRFP))
  * 1x resistor from 220 Ω to 470 Ω
  * some wires and soldering iron
  * 6x M3x10 screws


  1. Print all three STL files. They could be printed completely using white plastic. Or change the material to black color after printing 1 mm of 'clock screen.STL' if you like it in such way, as i did it.
  2. Cut the WS2812b LED strip into 5 strips with 17 LEDs each and solder everything according to wiring diagram:
     ![wiring](https://github.com/justr0st/esphome-RGB-LED-pixel-clock/blob/main/Images/Wiring%20Sketch.svg?raw=true)
  3. Put the strips into the sockets into printed display and pull the wire through the hole in the middle frame. Connect the board, bend the wires and close the case.
  
## Installation

Already installed and running ESPHome is needed. For more info see [Getting started with ESPHome](https://esphome.io/guides/getting_started_hassio.html).

Copy contents of ./esphome ('**led-clock.yaml**, '**secrets.yaml**' and '**animations**' directory) to ESPhome configurations location. If you already have '**secrets.yaml**', then just edit it accordingly.

Usually esphome path is:
```
/usr/share/hassio/homeassistant/esphome
```
Edit '**secrets.yaml**' by entering your **wifi_ssid**, **wifi_password**. **ota_password** is just a key that will be needed to be able to update the clock device wirelessly over the air afterwards.

Edit **manual_ip:** subsection of **wifi:** section in 'led-clock.yaml' and enter the IP configuration for your clock.
If you prefer dynamic IP assigned by your router, you can just comment those lines out using '#' symbol:
```yaml
#      static_ip: 192.168.1.222
#      gateway: 192.168.1.1
#      subnet: 255.255.255.0
```

After opening ESPHome user interface you will a new device called "led-clock" will be available:
![image](https://user-images.githubusercontent.com/50486502/199477793-32966969-0e1a-44d9-b9d8-8dc3f1274d86.png)

After pressing "EDIT" button you will be able to see the yaml code.
Connect the board to your PC using USB and install the firmware:

**INSTALL > Plug into this computer**

Wait untill firmware will be prepared and follow the on-screen instructions.

Afterwards it will be able to update the firmware wirelessly via OTA.
