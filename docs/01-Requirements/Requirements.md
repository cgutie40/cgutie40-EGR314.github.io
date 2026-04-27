---
title: Module's Requirements
---

## Wireless Communication Subsystem Module Requirements

The Wireless Communication Subsystem provides a bidirectional communication bridge between the Human-Machine Interface (HMI) and the rover’s onboard ESP32 communication module. The subsystem enables wireless transmission of user commands from the HMI to the rover and returns rover status and telemetry data back to the HMI.

The subsystem shall use WiFi-based MQTT communication to establish a reliable wireless link through a centralized broker. Over this link, command and telemetry data shall be transmitted between the HMI and the rover’s ESP32 modules. The subsystem functions as a communication gateway and does not directly control motors, sensors, or actuators.

On the controller side, the subsystem interfaces with the HMI via UART and forwards data to the MQTT broker. On the rover side, subsystem data is received from the MQTT broker and transmitted via UART to the rover’s local ESP32. The Wireless Communication Subsystem bridges data between the UART interface and the MQTT communication link.

The subsystem shall include a surface-mounted ESP32 microcontroller powered by a regulated 3.3 V onboard switching power supply. It shall support reliable bidirectional communication, maintain connection status awareness, and maintain a reliable connection to the MQTT broker.

#### Wireless Communication Subsystem Requirements 

| **Requirement Description** | **Measure of Threshold** | **Target Measure** | **Stretch Requirement (Y-N)** |
|-----------------------------|--------------------------|-------------------|:-----------------------------:|
| Surface-mounted 3.3 V switching power regulator | Output ≥ 3.2 V under load | Regulated 3.3 V ±5% | No |
| Surface-mounted microcontroller | One microcontroller present | ESP32 (32-bit) | No |
| Microcontroller power source | Powered from onboard regulator | Powered from 3.3 V switching regulator | No |
| MQTT communication capability | Able to send OR receive MQTT data | Bidirectional MQTT communication over WiFi | No |
| Wireless communication range | Minimum 2 meters reliable link | Limited by WiFi network coverage (≥ 10 meters typical) | Yes |
| UART communication support | At least one UART link to rover ESP32 | Reliable UART communication at ≥9600 baud | No |
| Communication with rover ESP32 | One-way command transmission | Bidirectional command and status exchange | No |
| System status monitoring | Able to detect MQTT/WiFi connection state | Heartbeat/status reporting over MQTT | Yes |
| End-to-end command latency | Response within 500 ms | Response within 200 ms typical | No |
| Power consumption | Operates without overheating | Operates within defined rover power budget | No |
