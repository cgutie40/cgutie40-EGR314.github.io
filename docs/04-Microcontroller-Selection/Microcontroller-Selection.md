# Microcontroller Selection

## Project-Specific Peripheral and Pin Requirements

To determine hardware compatibility and confirm sufficient I/O availability, the required peripherals and total pin count for the Wireless Communication Subsystem were checked. The ESP32-S3-WROOM-1 module will serve as a communication bridge between the HMI (via UART) and the rover’s local communications ESP32 (via Bluetooth).

### Required Communication Interfaces

| Interface | Signals Required | Total Pins |
|------------|------------------|------------|
| UART (HMI) | TX, RX | 2 |
| Bluetooth | Internal (no external GPIO required) | 0 |
| Native USB Programming | D+, D− | 2 |

### Control and Support Signals

| Function | Signals Required | Total Pins |
|-----------|-----------------|------------|
| Status LEDs | 2 GPIO outputs | 2 |
| Enable / Reset | EN | 1 |
| Boot / Programming Mode | IO0 | 1 |

### Power and Ground

| Function | Signals Required | Total Pins |
|-----------|-----------------|------------|
| 3.3V Supply | VCC | 1 |
| Ground | GND (multiple recommended) | 3 |

---

### Pin Count Summary

### Mandatory Signals
- UART (HMI): 2  
- USB (Programming): 2  
- Status LEDs: 2  
- EN (Reset): 1  
- IO0 (Boot): 1  
- 3.3V: 1  
- Ground: 3  

**Total Mandatory Pins: 12**

---

### Recommended Additional Pins
- Optional Debug UART (TX/RX): 2  
- Spare GPIO for future expansion: 4  

**Total Including Optional/Reserve Pins: 18**

---

### Notes and Design Considerations

- The ESP32-S3 operates at 3.3V logic levels. All UART-connected devices must be 3.3V compatible or use level shifting.
- Bluetooth communication is internal to the module and does not require dedicated GPIO pins.
- Multiple ground pins are recommended for reliable external connections.
- Boot and reset pins must remain accessible to allow firmware flashing.
- Additional spare GPIO pins are reserved for future subsystem expansion or diagnostics.

This analysis confirms that the ESP32-S3-WROOM-1 module provides sufficient peripheral interfaces and GPIO availability to support the communications subsystem requirements.

## Microcontroller (ESP32)

| Parameter|Specification|
| --------------------------------------------- | -------------------------------------------- |
| Model | ESP32-S3-WROOM-1-N4 |
| Product Page URL | [ESP32-S3-WROOM-1 Product Page](https://www.espressif.com/en/products/modules/esp32-s3-wroom-1) |
| ESP32-S3-WROOM-1-N4 Datasheet URL | [ESP32-S3-WROOM-1 Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf) |
| ESP32 S3 Datasheet URL | [ESP32-S3 Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3_datasheet_en.pdf) |
| ESP32 S3 Technical Reference Manual URL | [ESP32-S3 Technical Reference Manual](https://www.espressif.com/sites/default/files/documentation/esp32-s3_technical_reference_manual_en.pdf) |
| Vendor link | [Digikey – ESP32-S3-WROOM-1-N4](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639) |
| Code Examples | [ESP-IDF Examples](https://github.com/espressif/esp-idf/tree/master/examples), [Arduino ESP32 Core](https://github.com/espressif/arduino-esp32) |
| External Resources URL(s) | [Random Nerd Tutorials – ESP32-S3](https://randomnerdtutorials.com/), [Espressif YouTube Channel](https://www.youtube.com/@EspressifSystems) |
| Unit cost | ~$5.06 USD (qty 1) |
|Supply Voltage Range | 3.0 – 3.6 V (Nominal 3.3 V), Absolute Max 3.6 V|
|Maximum GPIO current (per pin) | 40 mA source, 28 mA sink|
|Absolute Maximum Current (entire IC) | Not explicitly specified; external supply up to 0.5 A (recommended)|
| Supports External Interrupts? | Yes |
| Required Programming Hardware, Cost, URL | USB cable (native USB supported) or 3.3V USB-to-UART adapter (~$10) |

---

| Module | # Available | Needed | Associated Pins (or * for any) |
| -------------- | ----------- | ------ | ------------------------------ |
| UART | 3 | 1 | Any GPIO via matrix (TX/RX) |
| external SPI* | 2 (SPI2, SPI3) | 0 | * |
| I2C | 2 | 0 | * |
| GPIO | Up to 45 (module exposes fewer) | 2–4 | Status LEDs / control lines |
| ADC | 2 units | 0 | - |
| LED PWM | 8 channels (LEDC) | 0–1 | Status LED |
| Motor PWM | 2 MCPWM units | 0 | - |
| USB Programmer | 1 (native USB OTG) | 1 | USB D+ / D− |
| WiFi | 1 | 0 | Internal |
| Bluetooth LE | 1 | 1 | Internal |

---

\* The ESP32-S3 has multiple SPI interfaces, but one is used internally for flash.

## Subsystem Role and Responsibilities

As the Wireless Communication Subsystem lead, my primary role on the team is to design and implement the gateway interface between the Human-Machine Interface (HMI) and the rover’s distributed control architecture. My ESP32-S3 module serves as a communication bridge, receiving user commands from the HMI via UART and transmitting them wirelessly to the rover’s local communications ESP32 using Bluetooth. In the reverse direction, my subsystem receives telemetry data from the rover’s daisy-chained sensor network and forwards relevant information back to the HMI for display. While my subsystem does not directly perform sensing or actuation, it is responsible for reliable transport of sensor data and control signals between systems. My responsibilities include selecting and configuring UART and Bluetooth interfaces, defining packet structure and data framing, verifying signal integrity and voltage compatibility, managing power requirements for the communication hardware, and implementing error detection and recovery features. Overall, my role is to make sure my system is robust, low-latency, and a reliable bidirectional communication between the operator interface and the rover subsystems.

## Worked-Out Communication Examples

### 1. BLE GATT Communication (ESP32 ↔ ESP32)

A BLE GATT server/client example was reviewed to verify compatibility between two ESP32 devices using Bluetooth Low Energy. In this configuration, one ESP32 acts as a GATT server (advertising telemetry data), while the other acts as a GATT client (connecting, subscribing to notifications, and sending commands). This confirms bidirectional wireless communication using the ESP32-S3 BLE stack.

Reference:
[Example 1 Link](https://randomnerdtutorials.com/esp32-ble-server-client/)

---

### 2. Bluetooth Classic Serial Port Profile (SPP)

A Bluetooth Classic SPP example was reviewed to evaluate transparent serial communication between two ESP32 boards. This approach allows one ESP32 to function as a wireless serial bridge, replacing a physical UART connection. The example demonstrates reliable data transmission between devices using the ESP-IDF Bluetooth SPP API.

Reference:
[Example 2 Link](https://github.com/nopnop2002/esp-idf-Bluetooth-SPP)

 ## ESP32-S3-WROOM-1 / 1U Pin Allocation Tables
 
![ESP32-S3-WROOM-1 / 1U Pin Allocation Image](pinoutDiagram.png)

| Peripheral | Signal | ESP32 Pin # | GPIO | Notes |
|------------|--------|-------------|------|-------|
| Power | 3V3 | 2 | 3V3 | 3.3V supply |
| Power | GND | 1, 40, EPAD | GND | Tie all grounds |
| Enable | EN | 3 | EN | Pull-up required (10kΩ) |

### UART to HMI

| Peripheral | Signal | ESP32 Pin # | GPIO | Notes |
|------------|--------|-------------|------|-------|
| UART1 | TX → HMI RX | 15 | GPIO3 | Safe GPIO |
| UART1 | RX ← HMI TX | 16 | GPIO46 | Input-only pin (good for RX) |

### USB Programming (Native USB)

| Peripheral | Signal | ESP32 Pin # | GPIO | Notes |
|------------|--------|-------------|------|-------|
| USB | D+ | 14 | GPIO20 | Native USB function (D+)|
| USB | D− | 13 | GPIO19 | Native USB function (D-)|

### Status LEDs

| Peripheral | Signal | ESP32 Pin # | GPIO | Notes |
|------------|--------|-------------|------|-------|
| Status LED | TX Activity | 17 | GPIO9 | Output |
| Status LED | BLE Connected | 18 | GPIO10 | Output |

## Final Microcontroller Selection and Rationale

After evaluating project requirements and available microcontroller options, the **ESP32-S3-WROOM-1** was selected as the final microcontroller for the Wireless Communication Subsystem.

This subsystem requires reliable bidirectional communication between the HMI (via UART) and the rover’s local controller (via Bluetooth). The ESP32-S3 integrates both **Bluetooth (BLE and Classic)** and multiple hardware communication interfaces, including up to three UARTs and native USB support. This eliminates the need for external wireless modules and reduces overall system complexity.

The dual-core 240 MHz processor provides sufficient computational headroom to manage concurrent UART communication, Bluetooth stack operation, and packet parsing without risking latency or dropped data. Additionally, the flexible GPIO matrix simplifies peripheral routing and supports iterative hardware revisions.

Operating at 3.3 V, the ESP32-S3 is compatible with a switching buck regulator from the 9–12 V battery supply. Its cost-effective pricing and strong ecosystem support (ESP-IDF, Arduino core, extensive documentation) further reduce development risk.

Based on wireless integration, communication flexibility, processing capability, cost, and ecosystem maturity, the ESP32-S3-WROOM-1 represents the optimal balance of performance and simplicity for this communications-focused design.
