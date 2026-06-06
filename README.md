# ESPHome BTHome Component

> **Personal fork.** This is a personal fork of [dz0ny/esphome-bthome](https://github.com/dz0ny/esphome-bthome), trimmed to just the BTHome receiver + transmitter components for my own use. All credit for the original work goes to [dz0ny](https://github.com/dz0ny). **For updates, the full project, and documentation, please see [dz0ny's repository](https://github.com/dz0ny/esphome-bthome).**

A custom ESPHome component that broadcasts sensor data using the [BTHome v2](https://bthome.io/) BLE protocol for seamless Home Assistant integration.

## Features

- **BTHome v2 Protocol** - Full compliance with the BTHome specification
- **Multi-Platform** - ESP32 (ESP-IDF) and nRF52 (Zephyr)
- **60+ Sensor Types** - Temperature, humidity, pressure, power, and more
- **28 Binary Sensor Types** - Motion, door, window, smoke, etc.
- **AES-CCM Encryption** - Optional 128-bit encryption
- **Home Assistant Auto-Discovery** - Devices appear automatically

## Quick Start

```yaml
external_components:
  - source: github://srnoth/esphome-bthome@main
    refresh: 1s
    components: [bthome]

sensor:
  - platform: bme280_i2c
    temperature:
      id: temperature
    humidity:
      id: humidity

bthome:
  sensors:
    - type: temperature
      id: temperature
    - type: humidity
      id: humidity
```

## Supported Platforms

| Platform | Board Example | Framework |
|----------|---------------|-----------|
| ESP32 | esp32dev, XIAO ESP32-C3 | ESP-IDF |
| nRF52840 | Seeed XIAO BLE | Zephyr |

## License

MIT License - See [bthome.io](https://bthome.io/) for protocol specification.
