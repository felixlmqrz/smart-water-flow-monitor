# Water Flow Monitor with ESP32 and MQTT

This project monitors water flow using an ESP32 and a YF-S201 sensor. It calculates real-time water usage and publishes the data to an MQTT broker. An LED is used to indicate when a defined water limit is exceeded.

## Features

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
- Tested with public broker: `mqtt.eclipseprojects.io` (port 1883)
- Local testing also done using Mosquitto

## Getting Started

1. Clone this repository.
2. Open `main.ino` using the Arduino IDE.
3. Configure your Wi-Fi credentials and MQTT broker address in the code.
4. Connect the **YF-S201 sensor** to GPIO 27 and **LED** to GPIO 17 (default).
5. Upload the code to your ESP32 board.
6. Monitor published flow data and send limit values via MQTT.

## License

This is an open project for learning and prototype use.
