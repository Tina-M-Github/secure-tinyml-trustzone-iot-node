# secure-tinyml-trustzone-iot-node
Secure TinyML anomaly detection prototype for resource-constrained IoT nodes using STM32U5A5ZJ-Q, DHT11 sensor input, TrustZone style secure processing, and verified alert generation.

# Secure TinyML IoT Node using TrustZone-Style Architecture

## Project Overview

This project presents a secure TinyML-based anomaly detection prototype for resource-constrained Internet of Things (IoT) devices. The prototype demonstrates how security concepts inspired by ARM TrustZone can be integrated with edge-based machine learning to provide trusted anomaly detection on embedded systems.

The system was developed using the **STM32U5A5ZJ-Q NUCLEO development board** and a **DHT11 temperature and humidity sensor**. It implements a lightweight TinyML-style anomaly scoring model, secure-style data validation mechanisms, simulated secure processing, and alert verification logic to demonstrate how intelligent IoT devices can perform secure local decision-making without relying on cloud resources.

This work was developed as part of a Bachelor of Science Honours Degree project in Hardware Engineering.

---

## Research Title

**Design and Implementation of a Hardware-Integrated TrustZone Architecture for Secure TinyML-Based Anomaly Detection on Resource-Constrained IoT Devices**

---

## Problem Statement

Tiny Machine Learning (TinyML) enables IoT devices to perform anomaly detection directly at the edge. However, resource-constrained microcontrollers often lack sufficient protection against firmware modification, model tampering, sensor manipulation, and false alert generation. This project investigates how TrustZone-inspired security concepts can be combined with TinyML techniques to provide secure and trustworthy anomaly detection on embedded IoT platforms.

---

## Project Objectives

1. Design a TrustZone-style architecture that separates secure and non-secure processing responsibilities.

2. Implement a secure TinyML inference workflow using controlled data validation and memory protection concepts.

3. Demonstrate alert verification mechanisms to improve trust in anomaly detection outputs.

4. Develop a functional prototype using STM32U5A5ZJ-Q and DHT11 sensor hardware.

---

## Hardware Components

* STM32U5A5ZJ-Q NUCLEO Development Board
* DHT11 Temperature and Humidity Sensor
* USB Type-C Cable
* Breadboard and Jumper Wires
* Host Computer running STM32CubeIDE

---

## Software Tools

* STM32CubeIDE
* STM32CubeMX
* STM32CubeProgrammer
* GNU Arm Embedded Toolchain
* GitHub

---

## System Architecture

The prototype follows a TrustZone-inspired architecture consisting of:

### Non-Secure Layer

Responsibilities include:

* Sensor data acquisition
* User interaction
* LED status indication
* Requesting secure processing services

### Secure Layer

Responsibilities include:

* Input validation
* Feature extraction
* Feature normalization
* TinyML-style anomaly scoring
* Alert verification
* Secure decision generation

---

## TinyML-Style Anomaly Detection

The prototype implements a lightweight anomaly scoring algorithm designed to simulate TinyML inference on a microcontroller.

Processing steps:

1. Acquire DHT11 temperature and humidity data.
2. Generate a combined environmental index.
3. Validate sensor inputs.
4. Extract features.
5. Normalize features.
6. Calculate anomaly score.
7. Verify generated alert.
8. Produce final system state.

This approach demonstrates how TinyML concepts can be executed locally on resource-constrained devices.

---

## LED Status Indicators

The onboard LD2 LED communicates system status.

| LED Behaviour    | Meaning                                             |
| ---------------- | --------------------------------------------------- |
| Slow Blink       | Normal monitoring state                             |
| Fast Blink Burst | Verified anomaly detected                           |
| 1 Second Blink   | Access blocked, tampering detected, or sensor error |

---

## Security Features

The prototype demonstrates:

* Secure-style processing separation
* Controlled access validation
* Input validation mechanisms
* Feature validation
* Tamper detection
* Alert verification
* Trusted anomaly reporting

---

## DHT11 Connections

| DHT11 Pin | STM32 Connection  |
| --------- | ----------------- |
| VCC       | 3.3V              |
| GND       | GND               |
| DATA      | PF13 (Arduino D7) |

---

## Building the Project

1. Open STM32CubeIDE.
2. Import the project.
3. Build the project.
4. Connect the STM32U5A5ZJ-Q board.
5. Flash the firmware.
6. Run the application.

---

## Demonstration Modes

### Normal Monitoring

```c
g_security_test_mode = 0;
g_tamper_test_mode = 0;
```

Expected Result:

* Slow LED blinking
* Normal sensor monitoring

### Tamper Detection

```c
g_tamper_test_mode = 1;
```

Expected Result:

* Invalid input detected
* Blocked LED pattern

### Access Blocked

```c
g_security_test_mode = 1;
```

Expected Result:

* Secure access denied
* Blocked LED pattern

---



## License

This project is intended for academic and research purposes.
