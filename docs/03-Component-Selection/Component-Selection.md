---
title: Module's Selected Major Components
---

## Module's Selected Major Components

The following sections are the selected major components necessary for  .....

>**For each of the following sections, use <ins>one of the two styles</ins> given near the end. *REMOVE THIS NOTE***

### Power Management

(**remove this note/placeholder**: this is where your 3.3 volt switching regulator, any other needed power regulator, and power source {if applicable} **THAT WERE SELECTED**)

For more details, review the ["Appendix - Component Selection Process - Power Mangement"](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#power-management) selection.

### Sensor

(**remove this note/placeholder**: if applicable, this is where your  **SELECTED** sensor is shown. Otherwise, remove this section.)

For more details, review the ["Appendix - Component Selection Process - Sensor"](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#sensor) selection.

### Actuator

(**remove this note/placeholder**: if applicable, this is where your **Selected** the actuator items go, which includes both the driver and motor. Otherwise, remove this section.)

For more details, review the ["Appendix - Component Selection Process - Actuator"](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#actuator) selection.

-----------
> Remove the following before submitting! Use them to present the selected components

### Style 1

> This is the example found in the assignment, uses more html

*Table 1: Example component selection*

**External Clock Module**

| **Component**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br> XC1259TR-ND surface mount crystal<br>$1/each<br>[link to product](http://www.digikey.com/product-detail/en/ECS-40.3-S-5PX-TR/XC1259TR-ND/827366)                 | \* Inexpensive[^1]<br>\* Compatible with PSoC<br>\* Meets surface mount constraint of project                                               | \* Requires external components and support circuitry for interface<br>\* Needs special PCB layout. |

**Rationale:** A clock oscillator is easier ....

### Style 2

> Also acceptable, more markdown friendly

**External Clock Module**

1. XC1259TR-ND surface mount crystal

    ![](image1.png)

    * $1/each
    * [link to product](http://www.digikey.com/product-detail/en/ECS-40.3-S-5PX-TR/XC1259TR-ND/827366)

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Inexpensive                               | Requires external components and support circuitry for interface |
    | Compatible with PSoC                      | Needs special PCB layout.                                        |
    | Meets surface mount constraint of project |

**Rationale:** A clock oscillator is easier ...



## Microcontroller Selection




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
Supply Voltage Range | 3.0 – 3.6 V (Nominal 3.3 V), Absolute Max 3.6 V
Maximum GPIO current (per pin) | 40 mA source, 28 mA sink
Absolute Maximum Current (entire IC) | Not explicitly specified; external supply up to 0.5 A (recommended)|
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
 



