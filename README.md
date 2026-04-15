# 🚁 **TRIPLE-NANO MODULAR DRONE SYSTEM**
<br>

## **1. PROJECT OVERVIEW**
<br>

This project is a modular quadcopter system developed specifically for the **Inspire Award**. 

<br>

Instead of using a standard all-in-one flight controller, this system breaks the drone's "nervous system" into three dedicated **Arduino Nano** microcontrollers. 

<br>

By separating the **Transmitter**, **Receiver**, and **Flight Controller**, we achieve maximum processing speed and a highly educational environment that is easy to troubleshoot and modify.

<br>
<br>

---

<br>

## **2. COMPONENT BREAKDOWN**
<br>

### **A. Transmitter (TX Code)**
The Transmitter Nano reads raw analog data from dual-axis joysticks and maps them (0-1023) into a single-byte format (0-255). It uses the **NRF24L01+PA+LNA** to broadcast signals with zero "lag."

<br>

### **B. Receiver (RX Code)**
The Receiver Nano catches the wireless data packets and converts them into a **PPM (Pulse Position Modulation)** signal. This allows all control data to travel over a **single wire** to the brain of the drone.

<br>

### **C. Flight Controller (FC Code)**
Running a custom-tuned **MultiWii** configuration, this Nano uses the **MPU6050** sensor to run high-speed PID loops. It calculates motor adjustments hundreds of times per second to keep the flight stable.

<br>
<br>

---

<br>

## **3. SENSOR PRECISION**
<br>

Included in this repository is the **MPU6050 Calibration** script. 

<br>

Every sensor has small manufacturing errors (offsets). By running this script on a flat surface before flight, you calculate these specific errors and save them to the Nano. This ensures your drone stays perfectly level without drifting.

<br>
<br>

---

<br>

## **4. INCLUDED FILES**
<br>

*   📄 **Transmitter_Code.ino**: Code for the remote control Nano.
*   📄 **Receiver_Code.ino**: Code for the antenna-to-PPM Nano.
*   📄 **Flight_Controller_Code.ino**: Pre-configured MultiWii logic for the drone.
*   📄 **MPU6050_Calibration.ino**: Tool for high-precision sensor leveling.
*   📦 **MultiWii_GUI.rar**: The official software to monitor your drone sensors on a PC.

<br>
<br>

---

<br>

## **📬 CONTACT & FEEDBACK**
<br>

If you find something wrong with the code or have suggestions for improvement, please **Gmail me at atharvaphadnis8@gmail.com**.

<br>
<br>

---

<br>

## **⭐ SUPPORT THE PROJECT**
<br>

If this modular drone project helps you with your own engineering journey or Inspire Award preparation:

<br>

**Please FORK this repository to save a copy for your own edits!**

<br>

**Please STAR this repository to help other student engineers find this resource!**

<br>
<br>
