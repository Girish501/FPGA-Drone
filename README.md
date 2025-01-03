# FPGA-Based Flight Controller for Quadcopter 🚁

---

## 📜 Project Overview

This project focuses on the design and implementation of a flight controller for a quadcopter using FPGA, developed in HDL. The flight controller integrates multiple sensors, control algorithms, and communication interfaces to provide precise control over quadcopter flight.

## 📋 Table of Contents
- [Motivation](#motivation)
- [System Design](#system-design)
- [Key Components](#key-components)
  - [PWM Decoder](#pwm-decoder)
  - [I2C Protocol and MPU 6050](#i2c-protocol-and-mpu-6050)
  - [PID Controller](#pid-controller)
  - [PWM Encoder](#pwm-encoder)
  - [FPV Camera](#fpv-camera)
- [Challenges](#challenges)
- [Results](#results)
- [Future Prospects](#future-prospects)
- [References](#references)

---

## 🔥 Motivation

There are a lot of flight controllers in the world working on microcontrollers that work on software-based approach. This project focused on an FPGA based approach, it is much more flexible, secure, customizable and faster. Yet only a few FPGA based Flight controllers are available in the market. Even though it is a better solution to the problem, it is more a question of "why can't we use FPGAs" or "why don't we see many in use". Since FPGA provide a hardware-based solution to the problem, they are harder to program as a flight controller developer. They are much more complex when compared to microcontrollers that are used currently. But that complexity has its own reward.
So, the main motivation of this project is to go beyond the barrier of complexity and provide a much better FPGA based solution to the existing drone system problems.

---

## ⚙️ System Design

The system integrates multiple modules to achieve smooth and stable flight for the quadcopter. It includes:
- **Transmitter & Receiver**: For remote control communication.
- **PWM Decoders**: Dedicated channels for throttle, yaw, pitch, and roll control.
- **MPU 6050**: Provides orientation data using I2C protocol.
- **PID Controller**: Ensures stable flight by adjusting motor speeds based on orientation data.
- **PWM Encoder**: Sends precise control signals to the Electronic Speed Controllers (ESCs) for motor control.

<div align="center">
    <img src="https://github.com/user-attachments/assets/f7090339-be16-44e5-8c92-316a45232282" alt="System Design" width="600"/>
</div>

---

## 🧩 Key Components

### PWM Decoder
The quadcopter control involves four channels - throttle, yaw, pitch, and roll, each represented by a PWM signal. The PWM decoder interprets these signals, translating them into motor speed adjustments for accurate control.

### I2C Protocol and MPU 6050
The **I2C master** module facilitates communication with the MPU 6050 gyroscope sensor, enabling data transfer for orientation tracking. This data is used for real-time adjustments during flight.

### PID Controller
The PID (Proportional-Integral-Derivative) controller ensures quadcopter stability by comparing user input with MPU 6050 data. It generates output signals for the PWM encoder to maintain smooth and stable flight.

<div align="center">
    <img src="https://github.com/user-attachments/assets/4dc9c67d-44eb-47d0-919d-2dcc8474a550" alt="PID Controller" width="500"/>
</div>

### PWM Encoder
The PWM encoder module is responsible for sending precise control signals to each ESC, adjusting the duty cycle of each PWM signal to control the speed of the quadcopter’s motors.

### FPV Camera
An FPV (First-Person View) camera module enables real-time video streaming, enhancing the UAV’s capabilities for monitoring and navigation.

---

## 🧗‍♂️ Challenges

- **Controlled Testing Environment**: Testing the quadcopter required a safe environment, such as controlled indoor spaces or designated outdoor UAV areas.
- **ESC Overload Protection**: Ensuring the Electronic Speed Controllers (ESCs) didn't overload due to voltage spikes was essential.
- **Wiring and Safety**: Proper wiring and metal-to-metal contact avoidance were critical for protecting the components.

---

## 🏆 Results

- Successfully completed and tested all modules, with generated bitstream files.
- Achieved synchronization of all four motors with the transmitter and receiver, ensuring stable and responsive flight control.

---

## 🔮 Future Prospects

1. **Autonomous PID Control**: Further refinement of the PID controller to enable fully autonomous flight without manual input.
2. **Enhanced Battery Management**: Developing an efficient battery management system to extend flight time.
3. **Power Optimization**: Improving power management techniques to reduce energy consumption and increase flight duration.

---

## 📚 References
1. R. Shantha Selva Kumari and C. Gayathri (2017) “Interfacing of MEMS motion sensor with FPGA using I2C protocol.”
2. Moad Idrissi, Mohammad Salami, and Fawaz Annaz (2021). “A Review of Quadrotor Unmanned Aerial Vehicles: Applications, Architectural Design, and Control Algorithms.”
3. [FS-i6 User Manual](https://static1.squarespace.com/static/5bc852d6b9144934c40d499c/t/5c0787e10e2e721a7f17c998/1543997593)
4. [Digilent Basys 3 Reference Manual](https://digilent.com/reference/_media/basys3:basys3_rm.pdf)
5. [ESP32 Hardware Guide](https://deepbluembedded.com/esp32-tutorials-full-hardware-kit-list/)

---

## 📸 Project Images

<div align="center">
    <img src="https://github.com/user-attachments/assets/ffaa474d-c842-43c5-a60d-ab1e7f6c6606" alt="Drone Prototype" width="300"/>
    <img src="https://github.com/user-attachments/assets/4162da30-f7a9-49bc-afde-2faa901e00ab" alt="FPV Camera Setup" width="300"/>
    <img src="https://github.com/user-attachments/assets/9f5957e6-5840-4b2c-98e6-fd3dfe97951a" alt="FPV Camera Setup" width="300"/>
</div>

---

### Team Members
- Girish Arora
- Aayush Chaudhary
- Siddhant N Sharma
- Navya Walia
- Ridhi Kapila
- Palak
- Ajay Pal
- Saloni Garg

### Mentors
- Dr. Manu Bansal
- Dr. Anil Singh
- Department of Electronics and Communication Engineering, Thapar Institute of Engineering and Technology, Patiala, Punjab

---

Thank you for exploring our project! We welcome any feedback or questions.
