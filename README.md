# 🏭 Industrial Automation: PLC & SCADA Water Tank Control System

[![PLC](https://img.shields.io/badge/PLC-Siemens%20LOGO!-blue?style=for-the-badge\&logo=siemens)](https://www.siemens.com)
[![SCADA](https://img.shields.io/badge/SCADA-Industrial%20Automation-orange?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)]()
[![University](https://img.shields.io/badge/Project-Semester%20Assignment-purple?style=for-the-badge)]()

---

## 📋 Overview

This project is a semester assignment for the **Industrial Automation** course. It presents the design and implementation of a **Water Tank Level Control System** using PLC logic and SCADA-based supervision concepts.

The main objective of the project is to demonstrate how an industrial process can be monitored and controlled using sensors, actuators, PLC programming logic, alarms, and supervisory system architecture.

---

## 🎯 Project Goals

* Design a PLC-based control system for a water tank
* Implement control logic using **Siemens LOGO! Soft Comfort**
* Define the required digital inputs and outputs
* Use level sensors, pump/valve control, alarms, and emergency stop logic
* Present the system architecture using industrial automation layers
* Document PLC, SCADA, Modbus communication, and cybersecurity concepts
* Provide a complete semester project report and PLC project file

---

## 🏗️ System Architecture

```text
┌─────────────────────────────────────────────────────┐
│              LEVEL 3 - SUPERVISORY                  │
│       SCADA / HMI Monitoring Concept                │
│    Real-time monitoring | Alarms | System status     │
└───────────────────┬─────────────────────────────────┘
                    │ Industrial Communication
┌───────────────────▼─────────────────────────────────┐
│              LEVEL 2 - CONTROL                      │
│              Siemens LOGO! PLC                      │
│       FBD / LAD Logic | Timers | Interlocks          │
└───────────────────┬─────────────────────────────────┘
                    │ Digital I/O
┌───────────────────▼─────────────────────────────────┐
│              LEVEL 1 - FIELD                        │
│  Level Sensors | Inlet Valve | Outlet Pump | Alarm   │
└─────────────────────────────────────────────────────┘
```

---

## ⚙️ System Description

### Application: Water Tank Level Control

The system controls the water level inside an industrial tank. The PLC receives signals from level sensors and controls the inlet valve, outlet pump, and alarm output.

### Control Logic

| Condition                   | Action                                  |
| --------------------------- | --------------------------------------- |
| Water level is LOW          | Activate inlet valve                    |
| Water level is HIGH         | Stop filling / activate outlet pump     |
| Emergency STOP is activated | Turn all outputs OFF and activate alarm |
| Fault or unsafe condition   | Activate alarm indication               |

---

## 🔌 I/O List

| Signal | Type           | Terminal     | Description         |
| ------ | -------------- | ------------ | ------------------- |
| I1     | Digital Input  | PLC Input 1  | High level sensor   |
| I2     | Digital Input  | PLC Input 2  | Low level sensor    |
| I3     | Digital Input  | PLC Input 3  | Manual START button |
| I4     | Digital Input  | PLC Input 4  | Emergency STOP      |
| Q1     | Digital Output | PLC Output 1 | Inlet valve         |
| Q2     | Digital Output | PLC Output 2 | Outlet pump         |
| Q3     | Digital Output | PLC Output 3 | Alarm indicator     |

---

## 🛠️ Tools & Software

| Tool                       | Purpose                                   |
| -------------------------- | ----------------------------------------- |
| Siemens LOGO! Soft Comfort | PLC programming and simulation            |
| Siemens LOGO! PLC          | Physical PLC platform                     |
| Draw.io                    | Diagrams and system architecture          |
| SCADA / HMI concepts       | Supervisory monitoring and alarm analysis |
| GitHub                     | Version control and project presentation  |

---

## 📁 Project Structure

```text
plc-scada-industrial-automation/
│
├── docs/
│   └── Report.pdf
│
├── plc/
│   └── siemens-logo/
│       ├── TankProjectFinal.lld
│       ├── tank_contol_logo.lsc
│       ├── plc_diagramm.png
│       └── screenshots/
│
├── scada/
│
├── demo/
│
├── README.md
├── LICENSE
└── .gitignore
```

---

##  How to Open the PLC Project

1. Install **Siemens LOGO! Soft Comfort**
2. Open the file:

```text
plc/siemens-logo/TankProjectFinal.lld
```

3. Run the simulation inside LOGO! Soft Comfort
4. Test the input conditions for:

   * Low level sensor
   * High level sensor
   * Manual start
   * Emergency stop
   * Alarm output

---

## 📊 Features

* ✅ Water tank level control logic
* ✅ Digital input and output mapping
* ✅ Inlet valve and outlet pump control
* ✅ Emergency stop logic
* ✅ Alarm indication
* ✅ PLC program file included
* ✅ System architecture documentation
* ✅ Final theoretical report included
* ✅ GitHub repository organized as a portfolio project

---

## 📚 Theoretical Background

The project report includes theoretical and practical analysis of:

### PLC Systems

* PLC architecture
* PLC scan cycle
* Digital inputs and outputs
* Ladder / FBD programming logic
* Timers, interlocks, and industrial control logic

### SCADA Systems

* SCADA architecture
* HMI monitoring
* Alarm handling
* Industrial communication protocols
* Modbus communication concepts

### Cybersecurity

* SCADA cybersecurity risks
* Access control
* Network segmentation
* Basic industrial security recommendations

---

## 📈 Development Progress

| Phase | Task                          | Status     |
| ----- | ----------------------------- | ---------- |
| 1     | Theory & System Design        | ✅ Complete |
| 2     | Siemens LOGO! PLC Programming | ✅ Complete |
| 3     | PLC Simulation / Testing      | ✅ Complete |
| 4     | SCADA & HMI Documentation     | ✅ Complete |
| 5     | Report & Documentation        | ✅ Complete |
| 6     | GitHub Final Version          | ✅ Complete |

---

## 📄 Final Deliverables

| Deliverable      | File / Folder                           |
| ---------------- | --------------------------------------- |
| Final Report     | `docs/Report.pdf`                       |
| PLC Project File | `plc/siemens-logo/TankProjectFinal.lld` |
| PLC Diagram      | `plc/siemens-logo/plc_diagramm.png`     |
| Screenshots      | `plc/siemens-logo/screenshots/`         |
| Documentation    | `README.md`                             |

---

##  Author

**Jurgen Mbersi**

GitHub: [@JurgenMbersi](https://github.com/JurgenMbersi)

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

##  Acknowledgments

* Siemens LOGO! documentation
* Industrial Automation course material
* PLC and SCADA learning resources
* University project guidelines

---

*Semester Project — Industrial Automation: PLC & SCADA Water Tank Control System*
