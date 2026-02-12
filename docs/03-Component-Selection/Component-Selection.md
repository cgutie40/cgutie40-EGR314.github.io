---
title: Module's Selected Major Components
---

# Major Component Selections

The following sections are the selected major components necessary for the Wireless Communication Subsystem

## Power Management

---

### 1. LMR50410Y3FQDBVRQ1 – 3.3V 1A Buck Regulator (SOT-23-6)

![](LMR504Bs.png)

* $1.76 / each  
* [Link to product](https://www.digikey.com/en/products/detail/texas-instruments/LMR50410Y3FQDBVRQ1/13562985)

| Pros                                                       | Cons                                                                 |
| ---------------------------------------------------------- | -------------------------------------------------------------------- |
| Small SOT-23 package                                      | Requires external inductor and capacitors per datasheet              |
| 1 A rating provides comfortable headroom for ESP32 bursts | More layout care than a prebuilt module                              |
| Automotive-grade (Q1) device                               | Limited to 1 A output current                                        |

---

### 2. BD9G341AEFJ-E2 – Adjustable 3A Buck Regulator (8-HTSOP-J)

![](BDG.png)

* $4.11 / each  
* [Link to product](https://www.digikey.com/en/products/detail/rohm-semiconductor/BD9G341AEFJ-E2/5409794)

| Pros                                            | Cons                                      |
| ----------------------------------------------- | ----------------------------------------- |
| Very wide input range (12 V – 76 V)             | Slightly larger 8-pin package             |
| High current capability (up to 3 A)             | Requires external inductor and capacitors |
| Integrated MOSFET                               | Higher cost compared to other options     |

---

### 3. AP63300WU-7 – Adjustable 3A Buck Regulator (TSOT-26)

![](AP6.png)

* $0.84 / each  
* [Link to product](https://www.digikey.com/en/products/detail/diodes-incorporated/AP63300WU-7/10491510)

| Pros                                   | Cons                                                     |
| -------------------------------------- | -------------------------------------------------------- |
| High current capability (up to 3 A)   | Lower switching frequency (~500 kHz) → larger inductors |
| Wide input range (3.8 V – 32 V)       | Requires external inductor and capacitors                |
| Compact thin SMD package              |                                                          |

---
---

## Final Choice and Rationale

### Selected Part: LMR50410Y3FQDBVRQ1 – 3.3V 1A Buck Regulator

The **LMR50410Y3FQDBVRQ1** was selected as the final voltage regulator for this design based on performance, size, cost, and suitability for the ESP32 system requirements.

This regulator provides a **regulated 3.3 V output at up to 1 A**, which offers sufficient headroom for ESP32 current bursts and additional peripherals. Its **wide input voltage range** comfortably supports a 9–12 V battery supply, making a stable operation even with battery voltage variation.

The **compact SOT-23-6 surface-mount package** meets the project's size constraints and supports a clean PCB layout. Compared to higher-current alternatives, this device provides adequate performance without unnecessary overdesign, keeping both cost and board space optimized.

For these reasons, the LMR50410Y3FQDBVRQ1 offers the best balance of:
- Electrical performance
- Physical footprint
- Cost efficiency
- Reliability
- Compatibility with project constraints

