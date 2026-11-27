# Smart Hand-Tracking Robotic Arm (5-DOF)

A standalone, real-time vision-based 5-DOF robotic arm powered by **Raspberry Pi 4**. The system tracks human hand landmarks and gestures using embedded Computer Vision (**OpenCV** & **MediaPipe**) and translates them into smooth, real-time servo movements without requiring an external PC or laptop.

---

## Key Features
- **Standalone Embedded System:** Runs entirely on Raspberry Pi 4 (64-bit OS) with no external laptop dependency.
- **Real-Time Hand Tracking:** Uses MediaPipe Hands to detect 21 3D hand landmarks and map joint angles & gripper pinch gestures.
- **Smooth Multi-Servo Control:** Driven by a 16-channel **PCA9685** I2C PWM driver for jitter-free motion.
- **Decoupled Power Architecture:** Dedicated 5V 5A power supply for servos isolated from the Raspberry Pi power rail to prevent voltage drops and brownouts.

---

## Hardware Components
| Component | Specification / Quantity | Role |
| :--- | :--- | :--- |
| **Main Controller** | Raspberry Pi 4 Model B (4GB RAM) | Runs CV pipeline & servo control logic |
| **Camera** | Raspberry Pi Camera Board V1.3 (5MP, 1080p) | Captures real-time video feed |
| **Robotic Arm** | 3D-Printed 5-DOF Robotic Arm Kit | Mechanical structure & gripper |
| **High-Torque Servos** | 3 × MG995 (180°, Metal Gear) | Base, shoulder, and elbow joints |
| **Micro Servos** | 3 × SG90 (180°) | Wrist rotation, wrist pitch, and gripper |
| **PWM Driver** | PCA9685 (16-Channel, 12-Bit I2C) | Drives all 6 servos via I2C |
| **Power Supply** | 5V 5A External PSU + 5V 3A USB-C Adapter | Decoupled power for servos and Pi |

---

## Software Stack
- **OS:** Raspberry Pi OS (64-bit)
- **Language:** Python 3
- **Computer Vision:** OpenCV, MediaPipe Hands, `picamera2`
- **Hardware Control:** `adafruit-circuitpython-servokit` (I2C / PCA9685)

---

## System Architecture
```text
[Pi Camera V1.3] ──▶ [Raspberry Pi 4 (OpenCV + MediaPipe)]
                               │
                          (I2C Bus)
                               ▼
[5V 5A PSU] ──▶ [PCA9685 16-Ch PWM Driver] ──▶ [6x Servos (5-DOF Arm)]
```

---

## Team Members
- **Sameh Salama** (Team Leader) — [@samehsalama-ai](https://github.com/samehsalama-ai)
- Omar Abdelhamid — [@i-omar1](https://github.com/i-omar1)
- Ahmed Sabry — [@engahmedsabry327-Igtm](https://github.com/engahmedsabry327-Igtm)
- Mazen Shokry — [@mazenshokry877-alt](https://github.com/mazenshokry877-alt)

