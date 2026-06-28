# ⚡ Electric Go-Kart — HV & LV Electrical System

Designed and built the complete High Voltage (HV) and Low Voltage (LV) electrical systems for an electric go-kart as **Electrical Lead** of Team MITS Motorsports. The team achieved **1st place in Kerala** and **13th place All India** at the 13th Go Kart Design Challenge (GKDC 2026) — EV Category, held at Kari Motor Speedway, Coimbatore.

---

## 🏆 Competition Result

| Field | Details |
|---|---|
| **Competition** | 13th Go Kart Design Challenge (GKDC) — EV Category |
| **Organizer** | ISNEE Motorsports Private Limited |
| **Venue** | Kari Motor Speedway, Coimbatore |
| **Date** | 20–24 February 2026 |
| **Team** | MITS Motorsports |
| **Result** | 🥇 1st in Kerala — 13th All India |

---

## 📌 System Overview

| Parameter | Specification |
|---|---|
| **Motor** | PMSM (Permanent Magnet Synchronous Motor) |
| **System Voltage** | 72V |
| **Battery** | LiFePO4 — 72V, 60Ah |
| **Motor Controller** | CL350 |
| **LV Microcontroller** | Arduino |

---

## 🔴 High Voltage (HV) System

### Components

| Component | Details |
|---|---|
| **Main Fuse** | Cartridge fuse — main overcurrent protection |
| **Accumulator Isolation Relays** | Two relays — one on positive rail, one on negative rail |
| **Motor Controller** | CL350 controller |
| **Battery Pack** | LiFePO4 72V 60Ah |
| **Motor** | PMSM motor |

### HV System Logic

```
Battery Pack (LiFePO4 72V 60Ah)
    → Cartridge Fuse (overcurrent protection)
        → AIR+ (Accumulator Isolation Relay — Positive)
        → AIR- (Accumulator Isolation Relay — Negative)
            → CL350 Motor Controller
                → PMSM Motor
```

### Safety Features
- Cartridge fuse protects against short circuit and overcurrent
- Dual accumulator isolation relays on both positive and negative rails — fully isolates battery from rest of system
- MOSFET discharge circuit bleeds controller capacitor bank when stop button is pressed — prevents dangerous residual voltage

---

## 🟢 Low Voltage (LV) System

### Components

| Component | Details |
|---|---|
| **Microcontroller** | Arduino |
| **Safety Circuit** | Latching relay circuit |
| **Self-holding Circuit** | Relay-based self-holding logic |
| **Capacitor Discharge** | MOSFET-based active discharge |
| **Ready to Drive** | Buzzer (RTD sound alert) |
| **Dashboard Switch** | Momentary switch — cart power on |
| **BMS Status Light** | Indicator for battery management system status |
| **LV Power Indicator** | LV system turn-on confirmation light |

### LV System Logic

```
Momentary Switch pressed on Dashboard
    → LV system powers ON
    → Self-holding relay circuit latches ON
        → Safety latching circuit checks all safety conditions
            → If all OK: AIRs close → HV system enabled
            → Arduino triggers RTD buzzer sound
            → BMS status light confirms battery OK
            → LV indicator light confirms system ready
                → Kart is Ready to Drive

Stop Button pressed
    → Safety latch releases
    → AIRs open → HV isolated
    → MOSFET discharge circuit activates
        → Controller capacitor bank discharged safely
    → System powers down
```

### Safety Features
- Latching safety circuit — system stays OFF unless all safety conditions are met
- Self-holding relay — maintains power state without continuous button press
- Active capacitor discharge via MOSFET — eliminates residual HV after shutdown
- BMS status monitoring — prevents operation if battery is in fault state

---

## 📁 Repository Structure

```
electric-go-kart-hv-lv-system/
├── media/
│   ├── hv_schematic.pdf
│   ├── lv_schematic.pdf
│   ├── kart_photo.jpg
│   └── competition_certificate.pdf
├── README.md
```

---

## 🛠️ Tools Used

- **KiCad** — Schematic design
- **Arduino IDE** — LV microcontroller programming
- **LiFePO4 Battery System** — 72V 60Ah pack

---

## 👤 Role

**Electrical Lead — Team MITS Motorsports**
- Designed complete HV power distribution system
- Designed complete LV safety and control system
- Implemented accumulator isolation, fusing, and active discharge
- Programmed Arduino for RTD sound and dashboard logic

---

## 👤 Author

**S Navaneeth Krishna**
B.Tech — Electrical and Electronics Engineering
Muthoot Institute of Science & Technology, Kerala

[![GitHub](https://img.shields.io/badge/GitHub-navaneeth--linh-181717?style=flat&logo=github)](https://github.com/navaneeth-linh)

---

## 📜 License

This project is open source and available for educational reference.
