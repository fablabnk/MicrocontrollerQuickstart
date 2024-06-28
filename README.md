# Quickstart Guide

With microcontrollers, it's easy to get stuck setting up your board and uploading your first piece of code to it. This process is still not quite 'plug and play'. This repo is designed to speed things up by providing a guide and tips for the main boards we have in the lab, both Arduinos and ESP32's.

Note: We recommended installing version 2 of the Arduino IDE. The guides below are written as if you are using that :)

A couple of general tips:
- USB cable-type matters: some cables only provide power, some power and data
- sometimes problems can be identified resolved in `File -> Preferences` by ticking  the `Show verbose output during upload` option

Once you have your board working, see the tutorials and examples section below for some starting points.

## Arduino Uno

- Disconnect your board from your PC
- Choose `Tools -> Boards -> Arduino AVR Boards -> Arduino Uno`
- First look in `Tools -> Ports` to see which items are already there
- Now connect it (I used one of the short blue USB cables)
- Then in `Tools -> Ports` select the item that appeared (in newer ArduinoIDE the item is also named after the board)
- Open the onboard LED Blink example from `File -> Examples -> 01.Basics -> Blink`
- If the blink example is already loaded on the board, modify the code slightly to change blink range i.e. `delay(100)` instead of `delay(1000)`
- Click the upload (`->`) button, code should flash, `Done Uploading` message should appear and onboard LED should blink

## Arduino Nano

- Disconnect your board from your PC
- Choose `Tools -> Boards -> Arduino AVR Boards -> Arduino Nano`
- First look in `Tools -> Ports` to see which items are already there
- Now connect it (I used one of the short blue USB cables)
- Then in `Tools -> Ports` select the item that appeared (in newer ArduinoIDE the item is also named after the board)
- In `Tools -> Processor` for older Nano's (our mini-USB ones) you will need to choose `ATmega328P (Old Bootloader)`. This can vary, so try both the new and old bootloader to be sure
- Open the onboard LED Blink example from `File -> Examples -> 01.Basics -> Blink`
- If the blink example is already loaded on the board, modify the code slightly to change blink range i.e. `delay(100)` instead of `delay(1000)`
- Click the upload (`->`) button, code should flash, `Done Uploading` message should appear and onboard LED should blink
- Finally, uploads can sometimes be magically made to work by ticking the `Show verbose output during upload` option in `File -> Preferences` 

## Arduino Uno Wifi (Rev 2)

Basic info about the board [here](https://docs.arduino.cc/retired/getting-started-guides/ArduinoUnoWiFi/)

Note: Do not be tempted to select `Arduino Uno Wifi` in the boards list, this is for the older revision of the board!

Instead:
- Disconnect your board from your PC
- In `Tools -> Boards -> Board Manager` search `Arduino megaAVR Boards` and click install
- Then choose `Tools -> Boards -> Arduino megaAVR Boards -> Arduino Uno Wifi Rev2`
- First look in `Tools -> Ports` to see which items are already there
- Now connect the Arduino to your PC (I used one of the short blue USB cables)
- Then in `Tools -> Ports` select the item that appeared (in newer ArduinoIDE the item is also named after the board)
- Open the onboard LED Blink example from `File -> Examples -> 01.Basics -> Blink`
- If the blink example is already loaded on the board, modify the code slightly to change blink range i.e. `delay(100)` instead of `delay(1000)`
- Click the upload (`->`) button, code should flash, `Done Uploading` message should appear and onboard LED should blink

Note, I got the warning `avrdude: usbdev_open(): WARNING: failed to set configuration 1: Device or resource busy`, but it still flashed :)

## Arduino MKR Wifi 1010

Follow [this tutorial](https://www.arduino.cc/en/Guide/MKRWiFi1010) or in brief:
- Disconnect your board from your PC
- In `Tools -> Boards -> Board Manager` choose `Arduino SAMD Boards (32-bits ARM Cortex-M0+)` and wait for install
- No wifi driver installation is necessary for Linux
- First look in `Tools -> Ports` to see which items are already there
- Then connect the Arduino with a microUSB cable 
- Then in `Tools -> Ports` select the item that appeared (in newer ArduinoIDE the item is also named after the board)
- If no extra entry appears, it could be a cable issue (I switched to another)
- Open the onboard LED Blink example from `File -> Examples -> 01.Basics -> Blink`
- Code should flash and onboard LED should start blinking. Successful upload message looks like this: 

```
Write 12312 bytes to flash (193 pages)

[=========                     ] 33% (64/193 pages)
[===================           ] 66% (128/193 pages)
[============================= ] 99% (192/193 pages)
[==============================] 100% (193/193 pages)
done in 0.080 seconds

Verify 12312 bytes of flash with checksum.
Verify successful
done in 0.011 seconds
CPU reset.
```

## ESP32

1. **Install ESP32 Board Package**:
  - Open Arduino IDE.
  - Go to `Tools > Board > Board Manager`.
  - Search for and install `esp32`.

2. **Install Audio Tools Library**:
  - Go to `Sketch > Include Library > Manage Libraries`.
  - Add the [Arduino Audio Driver Library](https://github.com/pschatzmann/arduino-audio-driver/tree/main) by Peter Schatzmann.
  - you have to download the zip btw

3. **Connect ESP32 to Computer**:
  - Use a USB cable to connect your ESP32 to the computer.

4. **Select Board and Port**:
  - Go to `Tools > Board` and select your ESP32 board (e.g., "ESP32 Dev Module").
  - Go to `Tools > Port` and select the appropriate COM port (this might be automatic).

5. **Write and Upload Sketch**:
  - Write your sketch in the Arduino IDE.
  - Click the upload button to transfer the sketch to the ESP32.

6. **Open Serial Monitor**:
  - Go to `Tools > Serial Monitor`.
  - Set baud rate to `115200` (or the baud rate specified in your sketch).
  - The Serial Monitor will display messages from your ESP32, including IP addresses and debug information.

## ESP8266

1. **Install ESP8266 Board Package**:
   - Open Arduino IDE.
   - Go to `File > Preferences`.
   - Add `http://arduino.esp8266.com/stable/package_esp8266com_index.json` to "Additional Board Manager URLs".
   - Go to `Tools > Board > Board Manager`.
   - Search for and install `esp8266`.

2. **Connect ESP8266 to Computer**:
   - Use a USB cable to connect your ESP8266 to the computer.

3. **Select Board and Port**:
   - Go to `Tools > Board` and select your ESP8266 board 
   - (e.g., "NodeMCU 1.0" or generic) 
   - Go to `Tools > Port` and select the appropriate COM port. (might be automatic)

4. **Write and Upload Sketch**:
   - Write your sketch in the Arduino IDE.
   - Click the upload button to transfer the sketch to the ESP8266.

# Tutorials and examples

Here are some resources to practice on a smaller scale using Tinkercad, microcontrollers and individual components, before 'scaling up'. Tinkercad can be nice for simple simulation and troubleshooting, to verify your circuit works before trying it on the real hardware.

## Basics

- Introducing the Breadboard(https://www.tinkercad.com/learn/overview/OPRHCXXL20FZS3N?collectionId=O0K87SQL1W5N4P2&type=circuits)
- Wiring Components(https://www.tinkercad.com/learn/overview/OLORCO6L20FZRZ7?collectionId=O0K87SQL1W5N4P2&type=circuits)
- Start Simulating(https://www.tinkercad.com/learn/overview/OT2JZ1PL20FZRMO?collectionId=O0K87SQL1W5N4P2&type=circuits)
- Using the Serial Monitor(https://www.tinkercad.com/learn/overview/OZ3W85UL26F9GZH?collectionId=O0K87SQL1W5N4P2&type=circuits)

## Key Components
Light:
	- [Fading LED With Analog Output](https://tinkercad.com/learn/overview/ORHT6NFL26F9GSW?collectionId=O0K87SQL1W5N4P2&type=circuits)
Sensors:
	- [Light Dependent Resistors](https://www.tinkercad.com/learn/overview/OXQL7IEL26F9H0U?type=circuits)
	- [Distance sensor](https://www.tinkercad.com/projects/Ultrasonic-Distance-Sensor-Arduino-Tinkercad)
Motors:
	- [Using Servos](https://www.tinkercad.com/things/eqQfhbhZPNa-arduino-uno-tutorial-3-servo-motor-project)
	- be aware that there are different types of servos e.g
	 	- standard servos which have a limited range of motion
		- continuous rotation servos which can rotate continuously in either direction
Sound:
	- [Super-Mario Buzzer](https://www.tinkercad.com/things/81sIEGzvYqU-super-mario-theme)