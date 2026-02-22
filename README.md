# 🎤 Voice-Controlled Home Automation

---

## 📌 Project Overview

This project was developed as part of the Microprocessors (CPE-312) Laboratory.
It focuses on building a voice-controlled automation system that enables users to operate household appliances and trigger a security alert using a smartphone through Bluetooth communication.

The system is based on the Tiva C Series (TM4C123GH6PM) microcontroller, which receives voice commands from a mobile device, processes them, and translates them into real-time hardware actions

---

## 🎯 Project Objectives

- Control household appliances using **voice commands**
- Implement a **security alert (Danger Mode)** for emergency situations
- Safely interface **low-power logic** with **high-current devices**
- Gain hands-on experience with:
  - Embedded C programming  
  - UART communication  
  - Relay interfacing  

---

## 🧠 System Design Overview

### 🔹 Main Components

- **Microcontroller:** Tiva C Series (TM4C123GH6PM)  
- **Bluetooth Module:** HC-05  
- **Relay Module:** 5V Opto-Isolated Relay  
- **Actuator:** Fan (external load)  
- **Indicators:** Onboard RGB LED & Piezo Buzzer  
- **Power Source:** External 5V Battery (for high-current load)

---

## ⚙️ Power & Hardware Architecture

The system uses **dual power rails for safety**:

- **3.3V Logic Power:** Tiva C microcontroller  
- **5V External Power:** Relay coil and fan  

This design prevents **brownouts** and protects the microcontroller from the high current drawn by the fan.

---

## 🔄 System Operation Flow

### 🗣️ Voice Command Control

1. User gives a voice command via mobile app (e.g., `"fan on"`)
2. Command is sent as a string via Bluetooth (**UART**)
3. Tiva C processes the command
4. If command matches:
   - **PA2** is set **HIGH**
   - Relay is activated
   - Fan turns **ON** using external power

---

### 🚨 Emergency Alert Mode (Danger Mode)

Activated using the voice command: `"danger"`

System response:

- 🔴 **Red LED (PF1)** blinks rapidly  
- 🔊 **Piezo buzzer (PA3)** generates alarm sound 
- System enters a continuous alert loop indicating an emergency state

---

## 🔌 Pin Configuration

| Component       | Tiva C Pin | Function             |
|----------------|------------|----------------------|
| HC-05 RX       | PE4        | UART Receive         |
| HC-05 TX       | PE5        | UART Transmit        |
| Relay Module   | PA2        | Fan Control          |
| Buzzer         | PA3        | Audible Alert        |
| Red LED        | PF1        | Visual Alert         |
| Power          | VBUS (5V)  | Relay Coil Power     |

---

## 🛠️ Challenges & Solutions

Power Isolation: External battery supply used to avoid system resets due to high current loads.

Relay Interfacing: Correct use of NO (Normally Open) and COM terminals for safe switching.

Timing Control: Software delays optimized for synchronized LED and buzzer operation.

---

## 📚 Tools & Technologies

- Embedded C  
- TivaWare / TM4C Peripheral Libraries  
- UART Communication  
- Relay Interfacing  
- Bluetooth Communication (HC-05)

---

## 👥 Team Members

- Khadija Nadeem 
- Hadia Sajid 
- Ayesha 
- Laiba  

---

## ✅ Project Summary

This project showcases a real-world application of microprocessors by combining voice control with hardware automation.
It strengthened our understanding of embedded system design, hardware–software integration, power management, and collaborative development.

---


## 👩‍💻 Author

**Khadija Nadeem**  
Electrical Engineering Student

---

## ⭐ Support

If you like this project, give it a ⭐ on GitHub and feel free to fork or contribute!
