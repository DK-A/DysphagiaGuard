# DysphagiaGuard

![Platform](https://img.shields.io/badge/Platform-ESP32-blue)
![Android](https://img.shields.io/badge/Android-API%2024%2B-green)
![Language](https://img.shields.io/badge/Language-Kotlin%20%7C%20C%2B%2B-orange)
![Architecture](https://img.shields.io/badge/Architecture-Offline--First-critical)
![Status](https://img.shields.io/badge/Status-Prototype-informational)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

DysphagiaGuard is an offline-first wearable healthcare system designed to detect safe and unsafe swallowing events in real time. It integrates an ESP32-based embedded system with a Jetpack Compose Android application, enabling reliable monitoring without internet dependency.

---

## Features

- Real-time swallow detection using sensor fusion (IMU + acoustic)
- Offline-first communication via ESP32 WiFi Access Point
- Android application built with Jetpack Compose
- Dual alert system:
  - Silent mode → vibration motor
  - Day mode → buzzer and LEDs
- Session tracking and PDF report generation
- Edge processing with no cloud dependency

---

## System Architecture

![System Architecture](docs/architecture.png)

---

## Tech Stack

### Embedded System
- ESP32 (DevKit V1)
- PlatformIO
- C/C++
- I2C communication (MPU6050)
- ADC signal processing (MAX9814)

### Mobile Application
- Kotlin
- Jetpack Compose
- Android SDK (API 24+)
- WebSocket (local communication)

### Communication
- WiFi Access Point (ESP32)
- Local WebSocket protocol
- Offline-first architecture

---

## Hardware Components

| Component              | Purpose                                  |
|----------------------|------------------------------------------|
| ESP32 DevKit V1      | Microcontroller + WiFi AP                |
| MPU6050              | Laryngeal vibration sensing (IMU)       |
| MAX9814              | Acoustic swallow detection              |
| ERM Vibration Motor  | Silent alerts                           |
| Buzzer               | Audible alerts                          |
| LEDs (Green & Red)   | Visual indication                       |

---

## Wiring Diagram

| Component        | ESP32 Pin |
|-----------------|----------|
| MPU6050 SDA     | GPIO 21  |
| MPU6050 SCL     | GPIO 22  |
| MAX9814 OUT     | GPIO 34  |
| Buzzer          | GPIO 25  |
| Vibration Motor | GPIO 26  |
| Green LED       | GPIO 27  |
| Red LED         | GPIO 14  |

---

## Setup and Installation

### ESP32 Firmware

1. Open `firmware/` in Visual Studio Code (PlatformIO)  
2. Install dependencies via `platformio.ini`  
3. Connect ESP32 via USB  
4. Build and upload firmware  

### Android Application

1. Open `android/` in Android Studio  
2. Sync Gradle  
3. Build APK  
4. Install on Android device (API 24+)  

---

## Running the Demo

1. Power on ESP32  
2. Connect to WiFi: **DysphagiaGuard-AP**  
3. Launch the Android app  
4. Enter patient details  
5. Start monitoring  

Trigger an unsafe swallow event:
- App vibrates  
- Alert is displayed  
- Event is logged  

6. End session to generate and share PDF report  

---

## Use Cases

- Dysphagia patient monitoring  
- Elderly care systems  
- Clinical swallow assessment  
- Assistive wearable healthcare  

---

## Future Enhancements

- TinyML-based classification on device  
- Optional cloud integration  
- Caregiver alert system  
- Improved noise and motion filtering  
- Wearable miniaturization  

---

## Authors

### Team TECHTONICS

- Dhamarai Kannan A  
- Akshaya Sreleka P S  
- Ashwinkumar K  
- Dharshan S  

Electronics and Communication Engineering (ECE)  
Chennai Institute of Technology, Chennai  

---

## Contributing

Contributions, issues, and feature requests are welcome.

---

## License

This project is licensed under the MIT License.
