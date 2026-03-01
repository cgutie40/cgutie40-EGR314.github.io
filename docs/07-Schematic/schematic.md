---
title: Module Schematic
---

## Overview

The Wireless Communication Subsystem functions as a  communication gateway between the rover and the Human-Machine Interface (HMI). It is built around the ESP32-S3-WROOM-1 module, which establishes a Bluetooth link with a secondary ESP32 located on the rover, enabling bidirectional wireless data exchange.

All control commands originating from the HMI are transmitted via UART to the local ESP32-S3-WROOM-1, which forwards the data over Bluetooth to the rover subsystems. Sensor data collected on the Rover is transmitted wirelessly back to this subsystem and relayed to the HMI through the UART interface. The subsystem performs no processing or decision-making logic; it operates strictly as a reliable communication bridge.

The board can be powered from either a 9–12V barrel jack input or an upstream  power connection from the HMI, with USB 5V available primarily for programming and development. LED indicators provide visual feedback for system power, UART activity, and Bluetooth connection status, and a dedicated GPIO signal communicates Bluetooth connection status to the HMI.

This architecture maintains clear separation between control, sensing, and user interface layers while providing a stable and efficient wireless communication pathway between the rover and HMI systems.


![Wireless Communication Subsystem](WCSV1P1.png){style width:"350" height:"300;"}
**Figure 01:** Wireless Communication Subsystem Schematic


## Resouces

The schematic as a PDF download is available [*here*](WCSV1.pdf), and the Zip folder of the project [*here*](Wireless%20Communication%20Subsystem%20V1.zip).
