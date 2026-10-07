# Autonomous Mobile Robot Firmware (ESP32)

Embedded firmware developed in **C++** using **PlatformIO** for an autonomous differential-drive mobile robot powered by an **ESP32** microcontroller. This project implements real-time closed-loop motor control, sensor fusion, and autonomous navigation state machines.

---

## 🚀 Key Features

* **Differential Drive Kinematics & Odometry:** Real-time pose estimation ($x, y, \theta$) derived from high-resolution wheel encoder interrupts.
* **Closed-Loop Motor Regulation:** Discrete **PID controllers with anti-windup protection** ensuring smooth and stable velocity control.
* **Multi-Sensor Perception & Safety:** 
  * **ToF Distance Sensor (VL53L0X):** I2C-based continuous distance measurement triggering instant hardware-level emergency braking.
  * **IR Line Sensor Array:** Analog sensing coupled with crossing detection algorithms for line-following navigation.
* **Deterministic Finite State Machine (FSM):** Structured architecture managing autonomous mission execution states.
* **Telemetry & Communications:** Serial and UDP infrastructure for remote state tracking and debugging.

---

## 🛠️ Tech Stack

* **Microcontroller:** ESP32
* **Framework:** Arduino (via PlatformIO ecosystem)
* **Language:** C++ (Object-oriented modular design)
* **Libraries:** Custom PID, IRLine, Robot Kinematics, and VL53L0X driver integration.

---

## 📁 Repository Structure

```text
├── include/          # Shared project headers
├── lib/              # External dependencies (e.g., VL53L0X driver)
├── src/              # Core source code
│   ├── main.cpp      # Main loop, telemetry, and setup
│   ├── control.cpp   # Finite State Machine & safety triggers
│   ├── robot.cpp     # Kinematics, odometry, and motor mapping
│   ├── PID.cpp       # PID controller implementation with anti-windup
│   └── IRLine.cpp    # Infrared line-following and cross counting
├── platformio.ini    # PlatformIO build configuration
└── README.md
