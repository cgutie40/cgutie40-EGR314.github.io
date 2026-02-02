---
title: Module's Requirements
---

## Wireless Communication Subsystem Module Requirements

The Wireless Communication Subsystem provides the link between the Human-Machine Interface (HMI) and the rover’s other subsystems, enabling user control, system monitoring, and data transfer. To perform this role, the subsystem must include a surface-mounted microcontroller with a reliable onboard power solution and support bidirectional Wi-Fi communication for sending commands and receiving rover data. Support for advanced messaging protocols such as MQTT is considered a stretch goal.

The subsystem must interface with sensors, motor controllers, and actuators using standard serial protocols (UART, I²C, and SPI). Basic human-machine interaction through a display or input device is required, with more advanced graphical or web-based interfaces considered optional. The system must also support reliable communication with motion-related subsystems, provide status feedback where possible, and meet power, thermal, and size constraints suitable for integration on the rover PCB.

The following table defines measurable requirements used to verify subsystem success.

#### Wireless Communication Subsystem Requirements 

| **Requirement Description** | **Measure of<br> Threshold** | **Target<br>Measure** | **Stretch<br>Requirement<br>(Y-N)** |
|-----------------------------|------------------------------|-----------------------|:----------------------------------:|
| Surface-mounted 3.3 V switching power regulator | Output ≥ 3.2 V under load | Regulated 3.3 V ±5% | No |
| Surface-mounted microcontroller | One microcontroller present | ESP32 (32-bit) | No |
| Microcontroller power source | Powered from onboard regulator | Powered from 3.3 V switching regulator | No |
| Wireless communication capability | Able to send OR receive Wi-Fi data | Send AND receive Wi-Fi data using MQTT | Yes |
| UART communication support | At least one UART link | Multiple UART links to subsystems | No |
| I²C sensor interface | One I²C bus operational | Shared I²C bus for multiple sensors | No |
| SPI interface support | One SPI device supported | SPI support for HMI display and peripherals | No |
| Human-Machine Interface support | Basic user input or display | Graphical display or web-based HMI | Yes |
| Communication with motor subsystem | Send commands OR receive feedback | Bidirectional command and feedback control | No |
| Communication with arm subsystem | One-way control communication | Bidirectional control and status feedback | No |
| System status monitoring | Able to detect subsystem presence | Heartbeat/status reporting for all subsystems | Yes |
| Power consumption | Operates without overheating | Efficient operation < specified power budget | No |



