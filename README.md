
# Pixel clock for ESPhome

Simple ESPHome pixel clock based on WS2812b lightstrip with 17x5 display.
![front](https://github.com/justr0st/esphome-RGB-LED-pixel-clock/blob/main/Images/LED_Clock_front.jpg?raw=true)
![side](https://github.com/justr0st/esphome-RGB-LED-pixel-clock/blob/main/Images/LED_clock_side.jpg?raw=true)

## Preparation
Materials needed:
  * Wemos D1 Mini ([example](https://www.amazon.de/gp/product/B0754N794H/))
  * WS2812b LED strip IPx0 without protective coating (100 LEDs/m) ([example](https://www.amazon.de/gp/product/B088FJLRFP))
  * some wires and soldering iron
  * 6x M3x10 screws


  1. Print all three STL files. They could be printed completely using white plastic. Or change the material to black color after printing 1 mm of 'clock screen.STL' if you like it in such way, as i did it.
  2. Cut the WS2812b LED strip into 5 strips with 17 LEDs each and solder everything according to wiring diagram:
     ![wiring](https://github.com/justr0st/esphome-RGB-LED-pixel-clock/blob/main/Images/Wiring%20Sketch.svg?raw=true)

## Installation

Already installed and running ESPHome is needed. For more info see [Getting started with ESPHome](https://esphome.io/guides/getting_started_hassio.html).

Copy contents of ./esphome ('**led-clock.yaml**, '**secrets.yaml**' and '**animations**' directory) to ESPhome configurations location. 
For example it could be:
```bash
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

## Todo

- finish readme
