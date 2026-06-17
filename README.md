# Blueetooth-Based-Home-Automation
# Bluetooth-Based Home Automation System

## Overview
A Bluetooth-enabled home automation system developed using the ARM7 LPC2129 microcontroller. The system allows users to control home appliances wirelessly through serial commands transmitted via a Bluetooth module. Commands are processed by the microcontroller to control connected devices such as LEDs and DC motors, while real-time status updates are displayed on a 16x2 LCD.

---
# Project Demonstration

## 1. Light ON

When the user sends the command **"light on"**, the LED connected to the LPC2129 turns ON and the LCD displays the corresponding status.

<p align="center">
  <img src="images/Light%20On.png" width="700">
</p>

---

## 2. Light OFF

When the user sends the command **"light off"**, the LED turns OFF and the LCD updates the status.

<p align="center">
  <img src="images/light_off.png" width="700">
</p>

---

## 3. Motor ON

When the command **"motor on"** is received, the LPC2129 drives the L293D motor driver to rotate the DC motor.

<p align="center">
  <img src="images/Motor on.png" width="700">
</p>

---

## 4. Motor OFF

When the command **"motor off"** is received, the motor is stopped and the LCD displays the updated state.

<p align="center">
  <>
</p>

---


## Features
- Wireless appliance control using Bluetooth communication
- Real-time command processing through UART
- LED ON/OFF control
- DC Motor ON/OFF control using L293D motor driver
- Status display on 16x2 LCD
- User-friendly command interface
- Embedded C firmware implementation
- Proteus-based simulation and testing

---

## Hardware Components
- ARM7 LPC2129 / LPC2124 Microcontroller
- HC-05 Bluetooth Module (or Serial Terminal in Simulation)
- LM016L 16x2 LCD Display
- L293D Motor Driver IC
- DC Motor
- LED Indicator
- Power Supply

---

## Software Tools
- Keil uVision
- Embedded C
- Proteus 8 Professional

---

## Pin Configuration

| Function | LPC2129 Pin |
|-----------|------------|
| UART0 TXD | P0.0 |
| UART0 RXD | P0.1 |
| LED Control | P0.10 |
| Motor IN1 | P0.12 |
| Motor IN2 | P0.13 |

---

## Command Protocol

| Command | Action |
|----------|---------|
| light on | Turn LED ON |
| light off | Turn LED OFF |
| motor on | Start Motor |
| motor off | Stop Motor |

---

## System Architecture

```text
Mobile Application
        │
        ▼
 HC-05 Bluetooth Module
        │
        ▼
 ARM7 LPC2129 Controller
        │
 ┌──────┴────────┐
 ▼               ▼
LED Control   L293D Driver
                  │
                  ▼
               DC Motor

        ▼
   16x2 LCD Display
```

---

## Working Principle
1. The user sends a command from a smartphone via Bluetooth.
2. The HC-05 Bluetooth module receives the command.
3. The LPC2129 microcontroller reads the command through UART communication.
4. Based on the received command, the controller performs the corresponding action:
   - Switches LED ON/OFF
   - Starts or stops the DC motor
5. The current system status is displayed on the 16x2 LCD.

---

## Proteus Simulation

### Schematic
![Bluetooth Home Automation]([docs/proteus_schematic.png](https://github.com/pillirajaratnam5-cmyk/Blueetooth-Based-Home-Automation/blob/main/images/Blueetoth%20Based%20Home%20Automatioin.png))

---

## Project Structure

```text
Bluetooth-Home-Automation/
│
├── Source/
│   ├── main.c
│   ├── uart.c
│   ├── lcd.c
│   ├── motor.c
│
├── Header/
│   ├── uart.h
│   ├── lcd.h
│   ├── motor.h
│
├── Proteus/
│   └── HomeAutomation.pdsprj
│
├── Docs/
│   └── proteus_schematic.png
│
└── README.md
```

---

## Future Enhancements
- Smartphone Android Application Integration
- Multiple Appliance Control
- Password-Based Authentication
- IoT Cloud Monitoring
- Voice Command Support
- MQTT-Based Smart Home Automation

---

## Learning Outcomes
- ARM7 Microcontroller Programming
- UART Communication
- Embedded C Development
- LCD Interfacing
- Motor Driver Interfacing
- Bluetooth Communication
- Embedded System Design and Debugging

---

## Author

**Raja Ratnam Pilli**

Embedded Systems Engineer | ARM | Embedded C | IoT Enthusiast
