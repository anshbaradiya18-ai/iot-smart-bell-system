# Design and Development of IoT-Enabled Intelligent Timetable Management and Automated Bell Control System

**Institution:** Madhav Institute of Technology & Science (MITS), Gwalior (M.P.), India  
**Department:** School of Engineering Mathematics and Computing  
**Team ID:** `68D44XGO`  
**Developed By:**  
- **Ansh Bardiya** (`BTMC26O1018`)  
- **Ankita Sharma** (`BTMC26O1017`)  

**Faculty Mentor:** Dr. Dheeraj Kumar Dixit  

---

## Project Overview
An IoT-enabled automated institutional bell control system built using an **ESP32 microcontroller**, **DS3231 Real-Time Clock (RTC)**, **optoisolated relay driver**, and a **JWT-authenticated web dashboard**. The system eliminates manual bell ringing delays, supports instant remote schedule updates over HTTPS, and ensures uninterrupted offline operation via local SPIFFS flash storage and battery-backed RTC timekeeping.

## Hardware Components & Pin Mapping
| Component | Specification | ESP32 Interface | Role |
| :--- | :--- | :--- | :--- |
| **ESP32 DevKit V1** | Dual-Core 240 MHz, Wi-Fi/BT | Core Controller (3.3V) | Cloud sync, web server & schedule engine |
| **DS3231 RTC Module** | ±2 ppm TCXO, CR2032 Backup | `GPIO 21` (SDA), `GPIO 22` (SCL) | Precision offline timekeeping |
| **1-Channel Relay** | 5V Optoisolated, 10A 250VAC | `GPIO 25` (Digital OUT) | Safe switching of 230V AC bell load |
| **Electric Gong Bell** | 230V AC Institutional Bell | Relay `NO` & `COM` | High-decibel campus acoustic alert |

## Key Features
- **Automated Schedule Execution:** Millisecond-accurate bell triggering based on daily or examination timetables.
- **Hybrid Cloud + Offline RTC Mode:** Syncs schedules via HTTPS REST APIs while falling back seamlessly to DS3231 RTC + SPIFFS cache during Wi-Fi outages.
- **Centralized Web Dashboard:** JWT-secured admin panel for real-time schedule management and manual emergency overrides.
- **Safe Electrical Isolation & Logging:** Optocoupler isolation for high-voltage bell switching and automated event logging in MySQL.
