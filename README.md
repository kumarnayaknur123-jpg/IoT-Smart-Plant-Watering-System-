# IoT Smart Plant Watering System

An ESP8266-based soil moisture monitoring and automatic watering project. The controller reads a soil moisture sensor and switches a relay-controlled DC water pump when the soil is dry.

> **Hardware note:** Sensor output direction, relay trigger level, and ESP8266 board pin mapping can vary. Calibrate the sensor and verify wiring before connecting the pump.

## Features
- Reads soil moisture through the sensor's analog output.
- Automatically switches a relay-controlled pump on when the soil is dry.
- Stops watering when the soil reaches the configured threshold.
- Prints sensor readings and pump state to the Serial Monitor.

## Hardware
- ESP8266 NodeMCU development board
- Soil moisture sensor with analog output (AO)
- Relay module compatible with the control voltage and logic used
- DC water pump and suitable external power supply
- Water container and tubing
- Breadboard and jumper wires

## Repository contents
```text
iot-smart-plant-watering-system/
├── README.md
├── src/
│   └── automatic_watering.ino
├── docs/
│   └── circuit-connections.md
├── images/
│   └── project-setup.jpg
└── .gitignore
```

## Wiring reference
See [`docs/circuit-connections.md`](docs/circuit-connections.md). The listed pins are a starting point—change the constants in the sketch to match your actual wiring.

## Software setup
1. Install the Arduino IDE.
2. In Boards Manager, install the ESP8266 board package.
3. Select the correct NodeMCU/ESP8266 board and COM port.
4. Open `src/automatic_watering.ino`.
5. Confirm the pin assignments and calibrate the moisture threshold in the sketch.
6. Upload the sketch, then open Serial Monitor at **115200 baud**.
7. Test the sensor with the pump disconnected first. Confirm the readings for dry and wet soil before enabling the pump.

## Calibration
The code prints a raw analog reading. Record the value with dry soil and with wet soil. Set `DRY_READING_IS_HIGH` and `MOISTURE_THRESHOLD` in the sketch based on your sensor's observed readings. If the pump runs in the wrong condition, re-check the threshold and sensor direction.

## Safety
- Do not power a pump directly from an ESP8266 GPIO pin.
- Use a suitable separate supply for the pump and a relay/driver rated for the pump's voltage and current.
- Check relay input voltage compatibility. Do not apply 5 V to an ESP8266 GPIO.
- Keep water away from exposed electronics and power connections.
- This repository provides a configurable starter implementation; verify it against your actual hardware before use.

## Project image
The `images` folder contains the project setup photograph, if provided with this package.

## Future improvements
- Wi-Fi dashboard and remote status monitoring
- Water-tank level sensor
- Moisture history logging
- Alerts when the tank is empty

## Author
Add your name, department, institution, and team members here.
