# ESP32 Relay Panel with MQTT, IR, PIR, NTP, and OTA for Home Assistant

## Project Overview

This project demonstrates a fully-featured **ESP32 relay panel** with:

* 4 relays controllable via **wall switches, IR remote, MQTT (Home Assistant)**.
* PIR motion sensor with adaptive cooldown and time-based relay activation:

  * Day (09:00–18:00): Relay1
  * Evening (18:00–23:00): Relay1 + Relay2
  * Night (23:00–09:00): Relay3
  * Relay4 always triggered by PIR if all relays are OFF
* **WiFi LED** indicator: solid when online, blinks on IR press
* **MQTT Home Assistant Discovery** for all 4 relays
* **OTA updates** via ArduinoOTA
* **NTP synchronization** with persistent time storage in Preferences/NVS

## Hardware Requirements

* ESP32 DevKit (DOIT ESP32 DEVKIT V1 recommended)
* 4-channel relay module (active LOW)
* 4 wall switches (momentary, INPUT\_PULLUP)
* PIR sensor
* IR receiver
* LED for WiFi status (optional)

### Pin Mapping

| Function    | Pin |
| ----------- | --- |
| Relay 1     | 23  |
| Relay 2     | 19  |
| Relay 3     | 18  |
| Relay 4     | 5   |
| Switch 1    | 13  |
| Switch 2    | 12  |
| Switch 3    | 14  |
| Switch 4    | 27  |
| PIR         | 34  |
| IR Receiver | 35  |
| WiFi LED    | 2   |

## Software Dependencies

* Arduino IDE or PlatformIO
* Libraries:

  * `WiFi.h`
  * `PubSubClient`
  * `IRremote` (v4.x)
  * `Preferences`
  * `ArduinoOTA`
  * `time.h` (built-in)



