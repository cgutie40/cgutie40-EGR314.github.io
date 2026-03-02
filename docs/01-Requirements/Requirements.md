---
title: Module's Requirements
---

## Wireless Communication Subsystem Module Requirements

The Wireless Communication Subsystem provides the link between the Human-Machine Interface (HMI) and the rover’s onboard ESP32 communication module. The subsystem enables bidirectional command and status data transfer using Bluetooth Classic communication via the Serial Port Profile (SPP).

The subsystem must include a surface-mounted microcontroller with a reliable onboard 3.3 V power solution and support bidirectional Bluetooth communication for sending HMI commands to the rover and receiving rover status data. The Bluetooth link shall function as a wireless serial bridge between the HMI and rover ESP32 modules.

The subsystem must interface with sensors, motor controllers, and actuators using standard serial protocols (UART, I²C, and SPI). Basic human-machine interaction through a display or input device is required. The system must also support reliable communication with motion-related subsystems, provide status feedback where possible, and meet power, thermal, and size constraints suitable for integration on the rover PCB.

The following table defines measurable requirements used to verify subsystem success.

#### Wireless Communication Subsystem Requirements 

#### Wireless Communication Subsystem Requirements 

| **Requirement Description** | **Measure of Threshold** | **Target Measure** | **Stretch Requirement (Y-N)** |
|-----------------------------|--------------------------|-------------------|:-----------------------------:|
| Surface-mounted 3.3 V switching power regulator | Output ≥ 3.2 V under load | Regulated 3.3 V ±5% | No |
| Surface-mounted microcontroller | One microcontroller present | ESP32 (32-bit) | No |
| Microcontroller power source | Powered from onboard regulator | Powered from 3.3 V switching regulator | No |
| Bluetooth communication capability | Able to send OR receive Bluetooth data | Bidirectional Bluetooth Classic communication using SPP | No |
| Bluetooth communication range | Minimum 2 meters reliable link | ≥ 5 meters reliable link | Yes |
| UART communication support | At least one UART link | Multiple UART links to subsystems | No |
| I²C sensor interface | One I²C bus operational | Shared I²C bus for multiple sensors | No |
| SPI interface support | One SPI device supported | SPI support for HMI display and peripherals | No |
| Human-Machine Interface support | Basic user input or display | Graphical display interface | Yes |
| Communication with rover ESP32 | One-way command transmission | Bidirectional command and status exchange | No |
| System status monitoring | Able to detect Bluetooth connection state | Heartbeat/status reporting over Bluetooth | Yes |
| Power consumption | Operates without overheating | Operates within defined power budget | No |



