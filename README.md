# Moisture Sensor Hardware

KiCad hardware design for ESP32-based soil moisture monitoring system.

## Overview

This repository contains the PCB design and schematics for a garden irrigation moisture sensor system. The board interfaces with frequency-based moisture sensors, DS18B20 temperature sensors, and provides relay control for power management.

## Firmware

Firmware for this hardware is available in a separate repository:
**[moisture-sensor-esp32](https://github.com/IMHarris/moisture-sensor-esp32)**

## Design Files

- **`MoistureSensor1.kicad_pro`**: KiCad project file
- **`MoistureSensor1.kicad_sch`**: Schematic design
- **`MoistureSensor1.kicad_pcb`**: PCB layout
- **`MoistureSensor1BOM.csv`**: Bill of Materials
- **`gerber/`**: Production files for PCB fabrication
- **`parts/`**: Custom component footprints and symbols

## Features

### Microcontroller
- ESP32 DevKit-compatible footprint
- WiFi connectivity for MQTT publishing
- 3.3V logic level

### Sensor Interfaces
- **6x Moisture Sensor Channels**: Relay-controlled power, frequency input
- **2x OneWire Buses**: For DS18B20 temperature sensors (long/short)
- **Bus Relay Control**: Programmable power management for OneWire buses

### I/O
- **Moisture Sensors**: 6 channels with relay control
- **Frequency Input**: GPIO 21 (shared)
- **OneWire Buses**: GPIO 13 (short), GPIO 14 (long)
- **OneWire Relay Control**: GPIO 12 (short), GPIO 26 (long)
- **Status LED**: GPIO 2

### Power
- 5V input via barrel jack or USB
- 3.3V regulation for ESP32
- Relay-switched 5V for sensors

## Bill of Materials

See `MoistureSensor1BOM.csv` for complete component list.

Key components:
- ESP32 DevKit module
- Relay modules (6x for sensor/bus control)
- DS18B20 temperature sensors
- Frequency-based moisture sensors (external)
- 5V power supply

## PCB Specifications

- **Layers**: 2-layer PCB
- **Dimensions**: [Add dimensions]
- **Connectors**: Screw terminals for sensors, barrel jack for power

## Manufacturing

Gerber files for PCB fabrication are included in the `gerber/` directory. These can be uploaded to PCB manufacturers like:
- JLCPCB
- PCBWay
- OSH Park

## Assembly Notes

1. Solder ESP32 DevKit module (or use pin headers for socketing)
2. Install relay modules
3. Connect screw terminals for sensor interfaces
4. Verify 3.3V and 5V power rails before powering ESP32
5. Flash firmware from [moisture-sensor-esp32](https://github.com/IMHarris/moisture-sensor-esp32)

## Design Software

- **KiCad**: Version 7.0 or later recommended
- Open `MoistureSensor1.kicad_pro` to view/edit the design

## License

[Specify your license here]

## Author

Ian Harris - [GitHub](https://github.com/IMHarris)

## Related Projects

- **Firmware**: [moisture-sensor-esp32](https://github.com/IMHarris/moisture-sensor-esp32)