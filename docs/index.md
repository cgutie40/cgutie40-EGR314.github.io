---
title: Welcome
tags:
- tag1
- tag2
---
<center>
<font size= "6">Cristopher Gutierrez Datasheet</font><br>
as part of<br>
<font size= "8"> 
Exploration Device Project</font><br>
S.C.O.U.T.S<br>
<font size= "5"> Team 202 </font><br>

**Submission: January 18, 2026**
</center>

## Introduction

This document provides a detailed overview of the Wireless Communication Subsystem used in the rover system. It outlines the design, hardware selection, communication architecture, and implementation details of the subsystem. The purpose of this datasheet is to describe how reliable bidirectional communication is achieved between the Human-Machine Interface (HMI) and the rover using a WiFi-based MQTT communication framework.

---

### Project Summary

Team 202’s project focuses on the design and development of a modular rover system capable of remote operation, subsystem coordination, and real-time feedback to the user. The rover consists of multiple subsystems, including motion (wheels), sensing modules (temperature, pressure, metal detection), and a robotic arm, all coordinated through a distributed communication architecture.

The system is designed with clear separation between sensing, control, and user interface layers. The HMI allows an operator to send commands and receive telemetry, while onboard subsystems execute tasks and collect data. Communication between these components is critical to overall system performance.

The Wireless Communication Subsystem enables this interaction by acting as a gateway between the HMI and the rover. Instead of using a direct wireless link, the system uses a WiFi-based MQTT architecture, where both the controller and rover communicate through a centralized broker. This approach improves scalability, reliability, and flexibility in how subsystems exchange information.

---

### My Contribution

As the Wireless Communication Subsystem lead, my responsibility is to design and implement the communication bridge that connects the HMI to the rover’s distributed subsystems.

My work focuses on:

- Implementing a UART ↔ MQTT gateway using the ESP32-S3  
- Designing and validating the packet structure used for subsystem communication  
- Managing reliable message transfer between controller and rover  
- Handling connection verification and system status signaling  
- Integrating hardware interfaces including UART, GPIO status indicators, and power systems  

This subsystem does not perform sensing or actuation directly; instead, it enables reliable transport of commands and telemetry between systems. Its performance directly impacts system responsiveness, reliability, and overall usability.

This document is intended to provide a clear understanding of how the communication subsystem operates and how it supports the overall rover system.




