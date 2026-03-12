# 🏭 Industrial Automation: PLC & SCADA Water Tank Control System

[![PLC](https://img.shields.io/badge/PLC-Siemens%20LOGO!-blue?style=for-the-badge&logo=siemens)](https://www.siemens.com)
[![PLC](https://img.shields.io/badge/PLC-Allen%20Bradley-red?style=for-the-badge)](https://www.rockwellautomation.com)
[![SCADA](https://img.shields.io/badge/SCADA-ScadaBR-orange?style=for-the-badge)](http://www.scadabr.com.br)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-In%20Progress-yellow?style=for-the-badge)]()
[![University](https://img.shields.io/badge/Project-Semester%20Assignment-purple?style=for-the-badge)]()

---

## 📋 Overview

This project is a semester assignment for the **Industrial Automation** course. It implements a complete **Water Tank Level Control System** using two industry-standard PLC platforms and a full SCADA supervisory system.

The project demonstrates real-world industrial automation concepts including PLC programming, HMI design, industrial communication protocols, and SCADA system integration.

---

## 🎯 Project Goals

- Design and implement a PLC-based control system for a water tank
- Program the control logic using **two different PLC platforms** (Siemens & Allen-Bradley)
- Develop a **SCADA HMI** for real-time monitoring and control
- Implement **industrial communication** via Modbus TCP protocol
- Apply **cybersecurity best practices** for SCADA systems
- Document the complete system architecture and implementation

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────┐
│              LEVEL 3 - SUPERVISORY                   │
│         SCADA HMI (ScadaBR)                         │
│    Real-time monitoring | Alarms | Trending          │
└───────────────────┬─────────────────────────────────┘
                    │ Modbus TCP
┌───────────────────▼─────────────────────────────────┐
│              LEVEL 2 - CONTROL                       │
│    Siemens LOGO! PLC  |  Allen-Bradley PLC          │
│    FBD Logic          |  Ladder Logic               │
└───────────────────┬─────────────────────────────────┘
                    │ Digital I/O
┌───────────────────▼─────────────────────────────────┐
│              LEVEL 1 - FIELD                         │
│  Level Sensors | Inlet Valve | Outlet Pump | Alarms  │
└─────────────────────────────────────────────────────┘
```

---

## ⚙️ System Description

### Application: Water Tank Level Control

The system automatically maintains the water level in an industrial tank within safe operating limits.

**Control Logic:**
| Condition | Action |
|-----------|--------|
| Level below LOW setpoint | Open Inlet Valve (Q1) |
| Level above HIGH setpoint | Close Inlet Valve, Start Outlet Pump (Q2) |
| Emergency STOP activated | All outputs OFF + Alarm ON (Q3) |
| Pump start | 3-second delay (TON Timer) |

### I/O List

| Signal | Type | Terminal | Description |
|--------|------|----------|-------------|
| I1 | Digital Input | PLC Input 1 | Level Sensor HIGH |
| I2 | Digital Input | PLC Input 2 | Level Sensor LOW |
| I3 | Digital Input | PLC Input 3 | Manual START Button (NO) |
| I4 | Digital Input | PLC Input 4 | Emergency STOP (NC) |
| Q1 | Digital Output | PLC Output 1 | Inlet Valve |
| Q2 | Digital Output | PLC Output 2 | Outlet Pump |
| Q3 | Digital Output | PLC Output 3 | Alarm LED |

---

## 🛠️ Tools & Software

| Tool | Version | Purpose |
|------|---------|---------|
| Siemens LOGO! Soft Comfort | V8/V9 | PLC programming (FBD) |
| Siemens LOGO! PLC | Physical HW | Real hardware testing |
| RSLogix 500 / RSLinx | Emulator | Allen-Bradley Ladder Logic |
| ScadaBR | Latest | SCADA HMI & data acquisition |
| Draw.io | Online | Architecture & P&ID diagrams |
| GitHub Desktop | Latest | Version control |

---

## 📁 Project Structure

```
plc-scada-industrial-automation/
│
├── 📁 docs/                          # Documentation & diagrams
│   ├── report.pdf                    # Full theoretical report
│   ├── architecture_diagram.png      # System architecture
│   ├── pid_diagram.png               # P&ID diagram
│   └── io_list.xlsx                  # Complete I/O list
│
├── 📁 plc/                           # PLC programs
│   ├── siemens-logo/
│   │   ├── water_tank_control.lsc   # LOGO! Soft Comfort project
│   │   ├── screenshots/              # FBD diagrams & simulation
│   │   └── README.md                 # Loading instructions
│   └── allen-bradley/
│       ├── water_tank_ladder.rss     # RSLogix project file
│       ├── screenshots/              # Ladder Logic rungs
│       └── README.md
│
├── 📁 scada/                         # SCADA system
│   ├── scadabr_project/              # ScadaBR export files
│   ├── hmi_screens/                  # HMI screenshots
│   ├── modbus_config.json            # Communication settings
│   └── README.md
│
└── 📁 demo/                          # Demonstrations
    └── demo_video.mp4                # System demo recording
```

---

## 🚀 Getting Started

### Prerequisites

- Siemens LOGO! Soft Comfort (V8 or later)
- RSLogix 500 + RSLinx Classic (or emulator)
- ScadaBR (Java Runtime Environment required)
- Physical Siemens LOGO! PLC (optional, for hardware testing)

### PLC - Siemens LOGO!

1. Install **LOGO! Soft Comfort**
2. Open `plc/siemens-logo/water_tank_control.lsc`
3. Run simulation or transfer to physical LOGO! PLC
4. See `plc/siemens-logo/README.md` for detailed instructions

### PLC - Allen-Bradley

1. Install **RSLogix 500** and **RSLinx Classic**
2. Configure RSLinx emulator driver
3. Open `plc/allen-bradley/water_tank_ladder.rss`
4. Go Online and run simulation

### SCADA - ScadaBR

1. Install **ScadaBR** and start the server
2. Access HMI at `http://localhost:8080/ScadaBR`
3. Import project from `scada/scadabr_project/`
4. Configure Modbus data source with settings from `modbus_config.json`

---

## 📊 Features

- ✅ Automatic water level control with hysteresis
- ✅ Emergency stop with fail-safe logic
- ✅ Pump start delay (anti-water-hammer protection)
- ✅ Real-time SCADA monitoring & control
- ✅ Alarm management (HIGH level, LOW level, E-STOP)
- ✅ Historical data trending
- ✅ Modbus TCP communication
- ✅ Dual-platform PLC implementation (Siemens + Allen-Bradley)
- 🔄 Cybersecurity analysis & countermeasures (in progress)
- 🔄 Demo video (in progress)

---

## 📚 Theoretical Background

This project covers the following topics from the course curriculum:

**PLC Systems:**
- PLC architecture and scan cycle
- IEC 61131-3 programming languages (LAD, FBD, ST)
- Timer and counter instructions
- Safety interlocks and fail-safe design

**SCADA Systems:**
- SCADA architecture (MTU, RTU, HMI, Historian)
- Industrial communication protocols: Modbus, DNP3, OPC-UA
- HMI design principles
- Cybersecurity threats and countermeasures

---

## 🔐 Cybersecurity Considerations

This project includes analysis of SCADA cybersecurity threats and implements basic countermeasures:
- Access control (operator / engineer levels)
- Network segmentation recommendations
- Intrusion detection awareness
- Encrypted communication guidelines

---

## 📈 Development Progress

| Phase | Task | Status |
|-------|------|--------|
| 1 | Theory & System Design | ✅ Complete |
| 2 | Siemens LOGO! PLC Programming | 🔄 In Progress |
| 3 | Allen-Bradley Ladder Logic | ⏳ Pending |
| 4 | SCADA HMI Development | ⏳ Pending |
| 5 | Report & Documentation | ⏳ Pending |
| Bonus | Demo Video | ⏳ Pending |

---

## 👨‍💻 Author

**JurgenMbersi**
- GitHub: [@JurgenMbersi](https://github.com/JurgenMbersi)

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Siemens LOGO! documentation and community
- Allen-Bradley / Rockwell Automation resources
- ScadaBR open-source community
- Course instructor and university resources

---

*Semester Project — Industrial Automation Course*
