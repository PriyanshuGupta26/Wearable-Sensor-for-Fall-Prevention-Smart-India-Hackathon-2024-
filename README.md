# 🧠 Wearable Sensor for Fall Prevention (Smart India Hackathon 2024)
### Team ID: 21989 | Team Name: SparkInnovators  
**Problem Statement ID:** SIH1580  
**Theme:** MedTech / BioTech / HealthTech  
**Category:** Hardware  

---

## 🚀 Project Overview
Our project aims to develop a **smart wearable wristband** integrated with **AI-based fall detection and prevention** mechanisms for elderly individuals. The device continuously monitors movement patterns using motion and health sensors. When a potential fall is detected, it provides **real-time alerts** through vibration or sound feedback, enabling the user or caregiver to respond immediately.  

---

## 🛠️ Technical Approach

### **Hardware Components**
- **Sensors:** BNO055 (Accelerometer + Gyroscope), AD8232 (ECG Sensor)
- **Microcontroller:** ESP32 / Arduino Nano
- **Connectivity:** Bluetooth Low Energy (BLE)
- **Power Supply:** Rechargeable Li-ion Battery
- **Form Factor:** Lightweight, wristband-type enclosure

### **Software Stack**
- **Languages:** Python, C++
- **Platforms:** Arduino IDE, Tinkercad, TensorFlow Lite (TinyML)
- **ML Models:**  
  - **LSTM:** For time-sequence analysis of accelerometer/gyroscope data  
  - **CNN:** For spatial pattern detection in multidimensional motion arrays  

### **AI Model Input Features**
- Accelerometer Data → `[ax, ay, az]`  
- Gyroscope Data → `[gx, gy, gz]`  
- Derived Features → Distance from ground, center of gravity  
- **Input Shape:** `[time steps, feature vector]`

---

## 🧩 Machine Learning Pipeline
1. **Data Collection:** Multi-sensor motion data from controlled experiments.  
2. **Preprocessing:** Noise reduction, normalization, and window segmentation.  
3. **Model Training:** GRU/LSTM model trained on labeled time-series data.  
4. **Deployment:** Model compressed using **TinyML** and deployed on ESP32.  
5. **Feedback Loop:** Alerts user upon detecting potential fall posture or instability.

---

## ⚙️ System Architecture
```plaintext
Sensors (BNO055, AD8232)
        ↓
Microcontroller (ESP32)
        ↓
Preprocessed Data → ML Model (TinyML)
        ↓
Alert Module (Vibration/Sound/Bluetooth Notification)
