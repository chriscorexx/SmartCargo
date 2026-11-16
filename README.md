# SmartCargo 🚛
### IoT-Enabled Self-Protecting Cargo Container for Intelligent Goods Transportation

SmartCargo is an IoT-based cargo monitoring and protection system designed to improve the safety of goods during transportation. It uses sensors and an ESP32 microcontroller to monitor environmental conditions, detect physical disturbances, and identify unauthorized access.

When abnormal conditions are detected, the system can alert the driver through a local display, buzzer, and warning LEDs. It can also trigger protective actions, such as activating a ventilation fan when the temperature exceeds a predefined threshold, while sending monitoring data to a remote dashboard over Wi-Fi.

---

## 📌 Project Overview

Traditional cargo transportation systems may lack affordable, real-time monitoring and immediate response mechanisms. Temperature changes, excessive vibrations, sudden tilting, and unauthorized access can damage or compromise transported goods.

SmartCargo aims to address these problems through a low-cost IoT-enabled system that follows a simple workflow:

**Sense → Process → Detect → Alert → Respond → Communicate**

The system is designed as a prototype representing a smart cargo container that could be installed inside a commercial transportation vehicle. The project focuses on the cargo container system rather than constructing a complete truck model.

## ✨ Key Features

- **Temperature Monitoring:** Monitors internal temperature and detects high-temperature conditions.
- **Humidity Monitoring:** Tracks humidity levels inside the cargo container.
- **Tilt Detection:** Detects abnormal container tilting during transportation.
- **Shock and Vibration Detection:** Identifies sudden impacts and unusual physical disturbances.
- **Door Security Monitoring:** Detects unauthorized container door openings.
- **Driver Alerts:** Displays warning messages and activates a buzzer and warning LEDs.
- **Automatic Ventilation:** Activates a cooling/ventilation fan when the temperature exceeds a configured threshold.
- **IoT Connectivity:** Uses Wi-Fi to transmit monitoring information to a remote dashboard.
- **Optional Door Lock Demonstration:** A servo motor can demonstrate an automated locking mechanism.

## 🛠️ Hardware Components

| Component | Purpose |
|---|---|
| ESP32 | Main microcontroller and Wi-Fi communication |
| DHT11 | Temperature and humidity monitoring |
| MPU6050 | Tilt, acceleration, and vibration monitoring |
| Reed Switch | Cargo door open/close detection |
| OLED Display | Local status and warning messages |
| Buzzer | Audible alerts |
| Warning LED | Visual alerts |
| DC Fan | Ventilation when temperature is high |
| SG90 Servo Motor (Optional) | Demonstration of an automated door-lock mechanism |

## 🧠 System Architecture

```text
       ┌─────────────────────────────┐
       │       SENSOR LAYER          │
       │                             │
       │  DHT11      MPU6050         │
       │  Reed Switch                │
       └──────────────┬──────────────┘
                      │
                      ▼
       ┌─────────────────────────────┐
       │          ESP32              │
       │                             │
       │  Sensor Processing          │
       │  Threshold Detection        │
       │  Decision Making            │
       └──────────────┬──────────────┘
                      │
          ┌───────────┼───────────┐
          ▼           ▼           ▼
      ┌────────┐ ┌─────────┐ ┌──────────┐
      │ OLED   │ │ Buzzer  │ │ Fan /    │
      │Display │ │ + LED   │ │ Servo    │
      └────────┘ └─────────┘ └──────────┘
                      │
                      ▼
       ┌─────────────────────────────┐
       │      Wi-Fi Connectivity     │
       │                             │
       │   Remote Monitoring        │
       │   Dashboard / MQTT          │
       └─────────────────────────────┘
```

## ⚙️ Working Principle

1. The sensors continuously collect environmental and physical data from the cargo container.
2. The ESP32 receives and processes the sensor readings.
3. The readings are compared against predefined threshold values.
4. If an abnormal condition is detected, the ESP32 activates the appropriate warning or response.
5. The OLED displays the detected condition, while the buzzer and LEDs provide local alerts.
6. The ventilation fan can activate when the temperature exceeds its configured threshold.
7. Monitoring data can be transmitted over Wi-Fi to a remote dashboard.

### Example Alert Conditions

| Condition | System Response |
|---|---|
| Temperature exceeds threshold | Display warning and activate fan |
| Humidity exceeds threshold | Display humidity warning |
| Abnormal tilt detected | Activate warning alert |
| Sudden shock detected | Activate warning alert |
| Cargo door opened unexpectedly | Trigger security alert |

*Threshold values will be calibrated and tested during prototype development.*

## 💻 Technology Stack

- **Embedded Programming:** C/C++ for ESP32
- **Microcontroller Platform:** ESP32
- **Communication:** Wi-Fi
- **IoT Messaging:** MQTT (planned integration)
- **Sensor Interfaces:** GPIO and I²C
- **Display:** OLED
- **Monitoring:** Remote dashboard

## 🎯 Project Objectives

- Develop an affordable IoT-enabled cargo monitoring prototype.
- Monitor environmental conditions during transportation.
- Detect abnormal tilt, shock, and unauthorized door access.
- Provide immediate local alerts to the driver.
- Demonstrate automatic responses to selected abnormal conditions.
- Enable remote monitoring through wireless communication.

## 🔮 Future Scope

- Integration of GPS for real-time cargo location tracking.
- Cloud-based data storage and historical monitoring.
- Machine learning for anomaly detection and predictive analysis.
- Improved sensor accuracy and calibration.
- Integration of additional environmental sensors.
- Enhanced cargo security and access-control mechanisms.
- Mobile application for remote monitoring and notifications.

## ⚠️ Current Limitations

- The DHT11 provides basic environmental monitoring and has limited accuracy.
- The ventilation fan improves airflow but cannot cool the container below the surrounding air temperature.
- MPU6050 readings require calibration to distinguish normal transportation movement from damaging impacts.
- The prototype's servo-based locking mechanism is a demonstration, not an industrial-grade cargo lock.
- Remote monitoring depends on network connectivity; local alerts are designed to operate independently.

## 📂 Repository Structure

```text
SmartCargo/
│
├── README.md
├── SmartCargo.png
├── CPSSppT011138.pdf
├── SmartCargo_Research_Paper_2page.docx
├── SmartCargo_Research_Papers.docx
└── ...
```

*The repository currently contains project documentation and reference material. Hardware firmware and dashboard source code can be added as development progresses.*

## 👨‍💻 Project Information

**Project Name:** SmartCargo

**Project Title:** IoT-Enabled Self-Protecting Cargo Container for Intelligent Goods Transportation

**Domain:** Internet of Things (IoT), Embedded Systems, Smart Logistics

**Institution:** Cusrow Wadia Institute of Technology, Pune

**Author:** Chris Dsouza

---

⭐ If you find this project interesting, consider giving the repository a star!

**SmartCargo — Making Cargo Transportation Smarter, Safer, and More Intelligent.**
