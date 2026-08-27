<div align="center">

# 🌡️ Smart AC-Humidifier 💧

**A Rule-Based Intelligent Decision System for Climate Control**

---

### "Smart climate choices for a smarter room."

[📖 Turorial Hardware Assembly](docs/TUTORIAL.md)

</div>

## Overview
**Smart AC-Humidifier** is a system based on (*rule-based*) that design for changing environment climete automatically.  

---

## Hardware
This system is implemented using Arduino and can be also with ESP32 as well, additional with LCD 20x4 I2C.  

### 🛒 Shopping List
Please see on: [bom](hardware/bom/list_component.md)

### 📂 Project Architechture
```
./                              : Root project directories
├── docs/                           : Documentation folder
├── firmware/                       : Firmware programs code
│   ├── fast_implementation/            : First or my fast implementation of this project
│   ├── include/                        : Rule-based logic
│   ├── src/                            : Source code
│   └── unit_test/                      : Unit testing program function
├── hardware/                       : File design (to be), Bill of Materials, etc
│   └── bom/                            : Bill of Materials folder
├── LICENSE.md
└── README.md
```

---

## ✨ Features
- **Rule-Based Logic**  : Fast decision making system.  
- **Smart Power Mode**  : Power saver mode (Temperature: 24-28°C, Humidity: 40-50%).  
- **LCD 20x4 Support**  : Monitoring real-time temperature status, humidity, and hardware mode.  

---

## Decision Logic

### ❄️ AC Rules
| Temperature condition (°C) | Status AC |
| :--- | :--- |
| > 28.0 | **ON** |
| <= 24.0 | **OFF** |
| 24.1 - 28.0 | **STANDBY** |

### 💧 Humidifier Rules
| Humidity condition (%) | Status Humidifier |
| :--- | :--- |
| < 40.0 | **ON** |
| >= 50.0 | **OFF** |
| 40.0 - 49.9 | **STANDBY** |

---

## 🛠️ Installation & Usage

### 1. Desktop (C++)
```bash
g++ firmware/src/main.cpp firmware/src/smartdecision.cpp -Iinclude -o app
```
then to run it:    
```bash
./app
```
  
#### nb.  
Use ```cd firmware/``` to make the path more shorter than this original path.  
so it can be:  
```bash
g++ src/main.cpp src/smartdecision.cpp -Iinclude -o app && ./app
```

### 2. Hardware (Arduino IDE)
- Instal library: `DHT sensor library` (Adafruit) & `LiquidCrystal I2C`.
- Open file `.ino` in folder `firmware/`.
- Connect I2C LCD to Pin A4 (SDA) & A5 (SCL).

---

<div align="center">

*Developed for learning & curiosity*

</div>