# **buhPod**

<img src="./assets/buhcat.png" width="128">

A battery-powered music player that supports 3.5mm wired earphones, made under 25$.

## Bill Of Materials
\> View [bom.csv](./bom.csv) <br>
Total cost is **~25$**

## CAD Design
- WIP
- View [/CAD directoy](./cad/) for more information


## Schematics

The schematics are as follows:

<img src="./assets/schematics_pic.png" width="512">

- These can be opened using [KiCAD](https://www.kicad.org/) for proper viewing.
- The PCB part is blank as these are meant to be soldered together directly.
- View the [/PCB directory](./schematics/) for more information

### Micro SD card regulator bypass

The Micro SD card reader mentioned in the BOM requires **5V** input from **VCC**, but we can only supply **3.3V** from the MCU max as we are powering it via a 18650 3.7V battery and not USB.<br>

Hence, we need to bypass the voltage regulator present on board by powering the board from the following **3.3V pin**:

<img src="./assets/regBypassSdCard.webp">

This bypasses the onboard AMS1117 voltage regulator and is connected to MCU's `3V3_OUT` pin.<br>
This is also mentioned in the schematic for the Micro SD Card reader.

## References
- https://www.waveshare.com/rp2350-lcd-0.96.htm
- https://learn.adafruit.com/adafruit-pcm5122-i2s-dac/downloads
- https://www.instructables.com/Raspberry-Pi-Pico-Micro-SD-Card-Interface/  
- https://circuitdigest.com/microcontroller-projects/raspberry-pi-pico-interfacing-with-rotary-encoder
- https://www.instructables.com/Raspberry-Pi-Pico-and-Rotary-Encoder/