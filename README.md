# Blueetooth-Based-Home-Automation


## Overview
This project implements a serial-controlled home automation system utilizing an ARM7TDMI microcontroller. It parses ASCII string commands received via UART to actuate physical peripherals, specifically an LED indicator and a DC motor. System status and command acknowledgments are displayed on an interfaced 16x2 character LCD.

## Hardware & Toolchain
* **Microcontroller:** NXP LPC2129 (Firmware Target) / NXP LPC2124 (Simulation Target)
* **Peripherals:** LM016L 16x2 LCD, L293D Motor Driver, DC Motor, Yellow LED, Serial Terminal (Bluetooth HC-05/HC-06 proxy)
* **Toolchain:** Keil uVision, ARM-ADS compiler
* **Simulation:** Proteus 8 Professional

## Pin Configuration
* **UART0:** `P0.0` (TXD) and `P0.1` (RXD) for serial communication.
* **LED Control (`LED_1`):** `P0.10`.
* **Motor Control (`MOTOR_IN1`, `MOTOR_IN2`):** `P0.12` and `P0.13` via L293D H-Bridge.

## Command Protocol
The firmware polls the UART for character strings terminated by a carriage return (`\r`) or line feed (`\n`). Input is normalized to lowercase before processing.
* `light on`: Drives `P0.10` HIGH, illuminates LED, updates LCD.
* `light off`: Drives `P0.10` LOW, extinguishes LED, updates LCD.
* `motor on`: Drives `P0.12` HIGH and `P0.13` LOW, engaging the DC motor.
* `motor off`: Drives both `P0.12` and `P0.13` LOW, halting the DC motor.
