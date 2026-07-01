# ESP32KMUTNB_V2.0

A comprehensive ESP32-based embedded system design featuring multiple sensors, display interfaces, and USB connectivity for IoT and wearable applications.

## Overview

This project is a hardware design for an ESP32 microcontroller-based system that integrates:
- **Microcontroller**: ESP32 with USB-to-UART bridge
- **Sensors**: ADXL345 accelerometer, MAX30102 heart rate sensor, LPS22H barometric pressure sensor, HDC1080 humidity/temperature sensor
- **Display Interfaces**: TFT LCD display (3.5" 480×320 SPI) and I²C LCD module
- **Connectivity**: USB Type-C for programming and power, I²C and SPI communication buses
- **I/O**: Push buttons, RGB LED, buzzer, and GPIO headers

## Project Structure

```
ESP32KMUTNB_V2.0/
├── ESP32KMUTNB_V2.0.kicad_pro          # KiCad project file
├── ESP32KMUTNB_V2.0.kicad_sch          # Main schematic
├── ESP32KMUTNB_V2.0.kicad_pcb          # PCB layout
├── Microcontroller.kicad_sch           # Microcontroller subsystem
├── Sensor.kicad_sch                    # Sensor subsystem
├── TFT_Display.kicad_sch               # TFT display connections
├── LCD_Display.kicad_sch               # LCD display connections
├── Header.kicad_sch                    # GPIO header configuration
├── USB-to-UART Bridge.kicad_sch        # USB communication module
├── Bottons.kicad_sch                   # Button configuration
├── hardware_libs/                      # Custom libraries
│   ├── ADXL345BCCZ-RL.kicad_sym       # ADXL345 symbol
│   ├── MAX30102_Module.kicad_sym      # MAX30102 symbol
│   ├── TFT_LCD_Display.kicad_sym      # Display symbol
│   ├── footprints.pretty/             # Custom footprints
│   └── 3d_model/                      # 3D models for components
└── fp-lib-table                        # Footprint library table
```

## Key Components

| Component | Part Number | Function |
|-----------|------------|----------|
| Microcontroller | ESP32-S3 | Main processing unit |
| USB Bridge | CH340/CH341 | USB-to-UART conversion |
| Accelerometer | ADXL345BCCZ-RL | 3-axis acceleration sensing |
| Heart Rate Sensor | MAX30102 | PPG heart rate and SpO₂ measurement |
| Pressure Sensor | LPS22H | Barometric pressure and altitude |
| Humidity/Temp | HDC1080 | Temperature and humidity measurement |
| Display | ILI9488 | 3.5" TFT LCD interface |
| LED Indicators | WS2812B | RGB addressable LED |

## Schematic Organization

The design is organized into functional subsystems:

1. **Microcontroller** - ESP32 core with reset, boot circuitry, and power management
2. **USB Bridge** - CH340 UART-to-USB converter with ESD protection
3. **Sensors** - I²C sensor array with pull-up resistors and decoupling capacitors
4. **Display** - SPI TFT display interface with control signals
5. **Headers** - GPIO breakout connectors for expansion
6. **Power** - +5V input, +3.3V regulation with decoupling

## Pin Configuration

### I²C Sensors (I2C0/I2C1)
- SENSOR_SDA / SENSOR_SCL
- Connected to: ADXL345, MAX30102, LPS22H, HDC1080

### SPI Displays
- TFT LCD uses standard SPI interface
- CLK, MOSI, CS, DC, RESET signals

### GPIO Headers (J5)
- 32-pin connector with labeled I/O signals
- Supports additional peripherals and debugging

## Manufacturing Notes

- **PCB Layers**: 4-layer board
- **Design Date**: May 30, 2026
- **Revision**: A
- **3D Models**: Available for ADXL345 and MSP3520 components

## Design Files

- **KiCad Version**: 8.0.3 or later
- **Library Dependencies**: Custom symbols and footprints included
- **DXF Files**: MAX30102 module reference drawing included

## Usage

1. Open `ESP32KMUTNB_V2.0.kicad_pro` in KiCad
2. Review subsystem schematics for specific circuit details
3. Edit PCB layout in `ESP32KMUTNB_V2.0.kicad_pcb`
4. Generate production files (Gerbers, drill files) as needed

## Documentation

Refer to the individual schematic sheets for detailed circuit descriptions:
- Microcontroller configuration and boot circuitry
- Sensor connectivity and addressing
- Display interface pinout
- Power distribution and grounding strategy

## Author

Design by Surasak M. (Mark)
KMTUNB

## License

[Specify your license here]

## Contact

For questions or modifications, please contact the design team.
