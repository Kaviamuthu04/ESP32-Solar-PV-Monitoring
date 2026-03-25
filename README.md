# ESP32-Driven IoT Solution for Solar PV Performance Monitoring and Smart Load Control

An IoT-based solar photovoltaic monitoring and smart load control system built using ESP32 to monitor both generation and load-side parameters in real time and automatically control loads based on solar power availability.

---

## 📌 Project Overview

Solar energy systems usually monitor only power generation and ignore load consumption. This leads to battery over-discharge, uncontrolled load usage, and lack of real-time monitoring.

This project introduces a **low-cost ESP32-based IoT system** that monitors solar panel performance and load consumption simultaneously and automatically controls non-critical loads when generation falls below a threshold.

---

## 🚨 Problem Statement

- No load monitoring in existing solar systems
- No automatic load control
- Battery drains silently
- No real-time remote monitoring
- Manual supervision required

A solar panel without monitoring is a silent machine.

---

## 🎯 Objectives

- Dual-side monitoring (generation and load)
- Automatic priority-based load control
- IoT cloud dashboard for remote monitoring
- Low-cost implementation using ESP32
- Real-time voltage, current, and temperature tracking

---

## ⚙️ System Features

- Real-time solar panel monitoring
- Load-side power monitoring
- Automatic load shedding
- Temperature monitoring of solar panel
- IoT cloud dashboard
- Bidirectional control
- Offline fallback with LCD
- Low cost (~ ₹2,455)
- Response time < 1.4 seconds
- 99.7% cloud reliability

---

## 🧠 System Architecture

### Generation Side
- Voltage Sensor
- ACS712 Current Sensor

### ESP32 Controller
- Reads all sensor data
- Runs control algorithm
- Controls relay modules
- Sends data to cloud

### Load Side
- Voltage Sensor
- ACS712 Current Sensor

### Temperature Monitoring
- LM35 Sensor

### IoT Cloud
- HTTP POST (Upload data)
- HTTP GET (Receive commands)

---

## 🧩 Hardware Components

| Component | Purpose |
|-----------|--------|
| ESP32 | Main controller and WiFi module |
| ACS712 (2) | Current measurement |
| Voltage Divider | Voltage sensing |
| LM35 | Temperature sensing |
| Solar Panel (5W 12V) | Power generation |
| Relay Module | Load switching |
| L293D | Load control |
| LCD 16x2 | Local display |
| Battery | Energy storage |

---

## 🔄 Working Principle

1. Sensors read solar panel voltage and current
2. Sensors read load voltage and current
3. ESP32 calculates generated power
4. If power drops below threshold:
   - Non-critical loads OFF
   - Critical loads ON
5. Data sent to cloud every second
6. LCD shows real-time values
7. System continues even without internet

---

## 🧮 Load Control Algorithm
Read sensors every 1 second

Compute Power = Voltage × Current

If Power < 3W
Relay 2 OFF (Non-critical loads)
Relay 1 ON (Critical loads)

Else
Relay 1 ON
Relay 2 ON

Reconnect when Power > 3.5W
(Hysteresis to prevent relay chatter)

---

## 🌐 IoT Dashboard

### Upload
- Voltage
- Current
- Power
- Temperature

### Download
- Relay control commands

### Features

- Remote monitoring
- Remote control
- Real-time updates
- Offline fallback
- Global access

---

## 📊 Performance Results

- Response time: < 1.4 seconds
- Sensor error: < 2%
- Cloud success: 99.7%
- Packets received: 5741 / 5760
- Cost: ₹2,455

---

## 🆚 Existing vs Proposed System

| Feature | Existing System | Proposed System |
|--------|----------------|----------------|
| Generation Monitoring | Yes | Yes |
| Load Monitoring | No | Yes |
| Auto Load Control | No | Yes |
| Bidirectional Control | No | Yes |
| Cost | ₹10,000+ | ₹2,455 |

---

## 💡 Future Enhancements

- MPPT Implementation
- AI-based Load Prediction
- Mobile App
- Fault Detection
- Battery Health Monitoring

---

## 📚 References

1. Smart Monitoring of Photovoltaic Energy Systems – Scientific African (2025)
2. Enhancing Real-Time Monitoring of PV Systems – Electronics (2022)
3. IoT Enabled Solar Energy System – E3S Conferences (2025)
4. IoT Technology for PV Monitoring – E3S Conferences (2025)
5. IoT Based Solar Power Monitoring – AIIoT (2023)

---

## 📌 Conclusion

- Dual-side monitoring achieved
- Automatic load control implemented
- IoT cloud dashboard working
- Low-cost solar monitoring system
- Reliable and scalable solution

Solar energy without smart monitoring is like a car without a dashboard.

---

## 📎 License

This project is developed for academic and research purposes.
