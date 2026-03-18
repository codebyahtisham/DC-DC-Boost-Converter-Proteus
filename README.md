<div align="center">

# ⚡ DC-DC Boost Converter Using MOSFET (IRFZ44N)

![Proteus](https://img.shields.io/badge/Proteus-Simulation-1C79B3?style=for-the-badge&logo=proteus&logoColor=white)
![MOSFET](https://img.shields.io/badge/MOSFET-IRFZ44N-orange?style=for-the-badge)
![Course](https://img.shields.io/badge/Course-Electronic%20Devices%20%26%20Circuits-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![University](https://img.shields.io/badge/Namal%20University-Mianwali-teal?style=for-the-badge)

**Course Project — Electronic Devices and Circuits**

*Design and simulation of a switched-mode DC-DC boost converter using IRFZ44N MOSFET in Proteus, stepping up 12V DC input to 48V DC output at 75% duty cycle.*

---

</div>

## 📋 Overview

This project implements a **DC-DC Boost Converter** — a switched-mode power supply (SMPS) that converts a low DC input voltage to a higher DC output voltage using a **MOSFET switching element**. The design uses the **IRFZ44N N-channel MOSFET** as the switching device, with an inductor for energy storage and a diode-capacitor network for output rectification and smoothing.

The converter steps up a **12V DC input to 48V DC output** at a switching frequency of 50 kHz with a 75% duty cycle, and was designed and verified through **Proteus simulation**.

## 🎯 Objectives

- Design a boost converter circuit using **IRFZ44N MOSFET** as the switching element
- Calculate optimal **inductor and capacitor values** for target specifications
- Achieve a **4× voltage boost** (12V → 48V) at 75% duty cycle
- Simulate and verify the circuit in **Proteus**

## 🏗️ Circuit Architecture

```
┌──────────────────────────────────────────────────────────────────┐
│              DC-DC BOOST CONVERTER TOPOLOGY                      │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│                  L1 (≥225 μH)        D1                          │
│   Vin ──┬──────┤ŻŻŻŻŻŻŻŻŻŻ├────┬──►|──┬──────┬── Vout        │
│   12V   │      Inductor      │        │      │  (48V)          │
│         │                    │       ┌┴┐    ─┬─                 │
│         │               ┌────┘       │R│    ─┴─ C1              │
│         │               │            │ │     │  (≥36 μF)        │
│         │          ┌────┴────┐       │ │     │                  │
│         │          │ IRFZ44N │       └┬┘     │                  │
│         │          │ (MOSFET)│        │      │                  │
│         │          └────┬────┘       │      │                  │
│         │               │            │      │                  │
│         └───────────────┴────────────┴──────┘                  │
│                         GND                                     │
│                                                                  │
│   PWM Signal ──► Gate (D = 75%, fsw = 50 kHz)                   │
│                                                                  │
│   ┌─────────────────────────────────────────┐                   │
│   │ Switch ON:  Inductor stores energy      │                   │
│   │ Switch OFF: Inductor releases → boosts  │                   │
│   └─────────────────────────────────────────┘                   │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

## 🔧 Design Specifications

| Parameter | Value |
|-----------|-------|
| **Input Voltage (Vin)** | 12V DC |
| **Output Voltage (Vout)** | 48V DC |
| **MOSFET** | IRFZ44N (N-channel) |
| **Duty Cycle (D)** | 75% (0.75) |
| **Switching Frequency (fsw)** | 50 kHz |
| **Inductor (L1)** | ≥ 225 μH |
| **Capacitor (C1)** | ≥ 36 μF |
| **Load Resistance** | 100 Ω |
| **Output Current (Iout)** | 0.48 A |
| **Converter Type** | Switched-Mode Power Supply (SMPS) |

## 🧮 Design Calculations

### Duty Cycle
```
Vout = Vin / (1 - D)
1 - D = 12V / 48V = 0.25
D = 0.75 (75%)
```

### Inductor Value
```
L1 ≥ (Vin × D) / (2 × fsw × ΔIL)
L1 ≥ (12V × 0.75) / (2 × 50kHz × 0.2A)
L1 ≥ 225 μH
```

### Capacitor Value
```
Iout = Vout / Rload = 48V / 100Ω = 0.48A
C1 ≥ (Iout × D) / (2 × fsw × ΔVout)
C1 ≥ (0.48A × 0.75) / (2 × 50kHz × 0.1V)
C1 ≥ 36 μF
```

## ✨ Key Features

- **4× Voltage Boost** — Steps up 12V DC input to 48V DC output
- **MOSFET Switching** — Uses IRFZ44N for efficient high-frequency switching at 50 kHz
- **Analytical Design** — All component values derived from boost converter equations
- **Energy Storage Mechanism** — Inductor stores energy during switch-ON, releases during switch-OFF to boost output
- **Proteus Verified** — Complete circuit simulated and validated in Proteus

## ⚙️ Working Principle

The boost converter operates in two phases controlled by the MOSFET gate signal:

**Switch ON (MOSFET conducting):** The inductor is connected across the input supply. Current flows through the inductor, storing energy in its magnetic field. The capacitor maintains the output voltage during this phase.

**Switch OFF (MOSFET not conducting):** The inductor opposes the change in current and releases its stored energy. This energy adds to the input voltage, producing a higher output voltage across the load through the diode-capacitor network.

## 📁 Repository Structure

```
DC-DC-Boost-Converter-Proteus/
│
├── 📄 README.md                                  # Project documentation
└── 📑 Boost_Converter_Presentation.pptx          # Project presentation slides
```

> **Note:** The presentation includes the circuit diagram, working principle, design calculations, and Proteus simulation results.

## 📑 Documentation

| Document | Description |
|----------|-------------|
| [📄 Presentation (PPTX)](Boost_Converter_Presentation.pptx) | Project slides — introduction, circuit diagram, working principle, calculations, simulation results |

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| **Proteus** | Circuit simulation and verification |
| **IRFZ44N MOSFET** | N-channel MOSFET as switching element |


## 📬 Contact

**Ahtisham Saleem**

[![Email](https://img.shields.io/badge/Email-engr.ahtishamsaleem%40gmail.com-red?style=flat-square&logo=gmail)](mailto:engr.ahtishamsaleem@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Ahtisham%20Salim-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/ahtisham-salim)
[![GitHub](https://img.shields.io/badge/GitHub-codebyahtisham-181717?style=flat-square&logo=github)](https://github.com/codebyahtisham)

---

<div align="center">

⭐ **If you found this project useful, consider giving it a star!** ⭐

</div>
