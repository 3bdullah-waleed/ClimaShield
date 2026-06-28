# ClimaShield 🌿🛡️
> **Smart Rooftop Garden Guardian** 
> Developed by Team Taylor | Asian Hackathon for Green Future 2026

ClimaShield is an affordable, solar-powered IoT ecosystem designed to protect rooftop and home-garden crops,, specifically optimized for **Mint**, from extreme ambient heat waves and drought stress.

---

## 🚀 Our Core Competitive Advantage: Offline Resiliency
Unlike cloud-dependent agricultural solutions that fail during a network outage, ClimaShield operates entirely on a local **SENSE-DECIDE-ACT** architectural loop. The system runs on-device without requiring an internet connection to protect the crops; the web dashboard and LLM agent function purely as an advanced monitoring and insight layer.

---

## 🏗️ System Architecture & Data Flow

```text
    [ SENSE ]                      [ DECIDE ]                     [ ACT ]
+---------------+              +----------------+             +-------------+
|     ESP32     |--USB Serial->| Raspberry Pi 5 |--USB Serial>|   Arduino   |
| 4 Sensors +   |   (JSON)     | (Random Forest |             | (Shade Servo|
| Tank level %  |              |   & OpenCV CV) |             | & H2O Pump) |
+---------------+              +----------------+             +-------------+
                                       |
                               +-------+-------+
                               |               |
                               v               v
                         [Local DB]     [Flask Server] <--> WiFi <--> [Web Dashboard / AI Agent]
                          (SQLite)        (Host 0.0.0.0)
