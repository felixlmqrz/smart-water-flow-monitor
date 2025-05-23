# Water Flow Monitor with ESP32 and MQTT

This project monitors water flow using an ESP32 and a YF-S201 sensor. It calculates real-time water usage and publishes the data to an MQTT broker. An LED is used to indicate when a defined water limit is exceeded.

## Description

- Flow is measured in mL and L/min.
- Values are sent to the MQTT broker every second.
- Limit value is received from MQTT and controls the LED.
- Uses standard MQTT protocol over Wi-Fi.

## Hardware

- **ESP32 Dev Kit** — microcontroller with Wi-Fi
- **YF-S201 water flow sensor** — flow measurement
- **LED** — alert output
- **Jumper wires** and optional breadboard or enclosure

## Software

- Code: `main.ino` written in Arduino C++
- Libraries: `ESP8266WiFi.h`, `PubSubClient.h`
- MQTT topics:
  - Subscribe: `waterFlowMonitor/limit`
  - Publish: `waterFlowMonitor/flowRate`, `flowML`, `totalML`

## Communication

- Wi-Fi TCP/IP connection
- MQTT protocol for data transmission
- Tested with public broker: `iot.eclipse.org` (port 1883)

## Getting Started

1. Upload the code with Arduino IDE.
2. Connect the sensor to GPIO 27 and LED to GPIO 17 (default).
3. Configure Wi-Fi and MQTT broker in the code.
4. Monitor flow and send limit via MQTT.

## License

This is an open project for learning and prototype use.
