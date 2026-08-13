# Smart Motor Health Monitoring and Fault Detection System

A low-cost, ESP32-based edge intelligence system that monitors electric motor health in real time using multi-sensor fusion, and autonomously detects faults, triggers safety shutdowns, and sends alerts via Telegram — all without relying on cloud processing.

[View Full Project Dossier (PDF)](docs/Motor-Health-Monitoring-Report.pdf)

## Overview

Electric motor failures (overheating, overload, mechanical vibration, and shock damage) cause costly downtime in industrial and academic settings. This project implements an **edge-intelligent monitoring system** that:

- Fuses readings from 4 sensors into a single **Health Index (0–100%)**
- Classifies faults locally on the ESP32 (no cloud dependency)
- Automatically shuts down the motor on severe faults
- Sends real-time alerts via a Telegram bot
- Displays live status on a 16×2 LCD

## Features

- **Multi-sensor fusion**: Temperature, current, MEMS vibration, and piezoelectric shock sensing
- **Dual vibration sensing**: MPU6050 (broadband vibration) + piezoelectric disc (impulsive shocks)
- **Edge decision-making**: All fault logic runs on-device for sub-second response
- **Automatic safety shutdown** via relay-controlled power cutoff
- **IoT alerts** through Telegram Bot API over Wi-Fi
- **Low cost**: ~₹1,260 (~$15) per unit

## Hardware Components

| Component | Purpose |
|---|---|
| ESP32 Dev Module | Central processing unit (dual-core, Wi-Fi) |
| NTC Thermistor (10kΩ) | Temperature sensing |
| ACS712-05B | Current sensing / overload detection |
| MPU6050 | 6-axis IMU for vibration RMS |
| Piezoelectric Disc | Shock/impulse detection |
| 5V Relay Module | Motor power cutoff |
| 16×2 LCD (I2C) | Local status display |
| 18650 Li-ion Cells (×2) | Motor power supply |
| DC Gear Motor | Test motor |

## System Architecture
