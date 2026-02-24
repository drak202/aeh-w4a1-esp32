# esphome compensation for AEH-W4A1 local 

This ESPHome component provides full control and monitoring of my clima HOME
## About the Hisense AEH-W4A1 Controller

This component directly replaces the Hisense AEH-W4A1 .

The dongle plugs into a dedicated 4-pin port on the indoor unit's control board with the following pinout:
1. GND (black wire)
2. RS485 B-
3. RS485 A+
4. +5V (red wire)
<img width="541" height="398" alt="image" src="https://github.com/user-attachments/assets/f6f8c7b5-ff01-4907-986d-f90b150f92e4" />



This ESPHome component plugs into the same 4-pin port, uses the same RS485 communication and 5V power, and speaks the identical Hisense protocol, but provides full local control through Home Assistant, WEB Iterfaces without any cloud dependency.

## Features

- **Climate Control**: Full temperature control only Celsius, with support for heating, cooling, fan-only, and dry modes.
- **Fan Modes**: Auto, low, medium, high, and quiet fan speeds.
- **Swing Control**: Horizontal and vertical swing options, including combined swing.
- **Presets**: Turbo (boost) and energy-saving modes.
- **Sensor Monitoring**: Real-time data from compressor frequency, outdoor/indoor temperatures, humidity, and more.
- **RS485 Communication**:Serial communication with automatic RE/DE pin control for half-duplex operation.
## Installation

The code is written in an older version of esphome, it does not work in the new one. Therefore, you need to use VENV and install in it: Python 3.10.19
and esphome Version: 2023.3.2.
Edit room_ac.yaml according to your own needs.




## Hardware Setup

- **Microcontroller**: ESP32 WEMOS D1
- **Communication**: Bidirectional converter TTL (USART) to RS485
- I tried connecting the ESP directly to the air conditioner without a converter. The control worked but it couldn't read data from the unit.



## Credits

I referenced the work of several others to make this happen:
* https://github.com/pslawinski/esphome_airconintl

The code is modified, it only supports degrees Celsius, it does not control RS485 switching, the checksum is corrected.
I used ESP32 wemos D1 and Bidirectional converter TTL (USART) to RS485. Power supply is 5V directly from the air conditioning unit without any convector.
![Obrázok](IMG_20260121_162134798.jpg)
