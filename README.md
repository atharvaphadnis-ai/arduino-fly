# 🚁 **TRIPLE-NANO MODULAR DRONE SYSTEM**
<br>

## **1. PROJECT OVERVIEW**
<br>

This project is a high-performance, modular quadcopter system developed specifically for the **Inspire Award**. 

<br>

Instead of using a standard all-in-one flight controller, this system breaks the drone's "nervous system" into three dedicated **Arduino Nano** microcontrollers. 

<br>

By separating the **Transmitter**, **Receiver**, and **Flight Controller**, we achieve maximum processing speed and a highly educational "pure code" environment that is easy to troubleshoot and modify.

<br>
<br>

---

<br>

## **2. THE TRANSMITTER (TX) MODULE**
<br>

The Transmitter acts as the ground station. It uses an Arduino Nano to read the raw analog data from two dual-axis joysticks. 

<br>

The code maps these values (0-1023) into a single-byte format (0-255) to keep the wireless packets small and fast. This ensures there is zero "lag" between your hand movements and the drone's reaction.

<br>

The **NRF24L01+PA+LNA** module is used here to broadcast these signals over long distances with high reliability.

<br>
<br>

---

<br>

## **3. THE RECEIVER (RX) MODULE**
<br>

The Receiver Nano is the bridge between the air and the drone's brain. 

<br>

It listens for the specific "Pipe Address" sent by the transmitter. Once it catches the data, it uses a complex timing interrupt to generate a **PPM (Pulse Position Modulation)** signal.

<br>

This allows us to send all 7 channels of control data through **one single signal wire** to the Flight Controller, significantly reducing weight and wiring complexity.

<br>
<br>

---

<br>

## **4. THE FLIGHT CONTROLLER (FC) MODULE**
<br>

The "Brain" of the drone runs a custom-configured version of the **MultiWii Firmware**.

<br>

The software runs a high-speed PID (Proportional-Integral-Derivative) loop that calculates motor adjustments hundreds of times per second to keep the drone perfectly level, even during external disturbances like wind.

<br>

Key settings enabled in the **config.h** file include:
*   **QUAD-X Layout:** Sets the 4-motor geometry.
*   **GY-521 Driver:** Activates the MPU6050 I2C communication.
*   **SERIAL_SUM_PPM:** Enables the single-wire communication from the RX Nano.
*   **MPU6050_LPF_42HZ:** Filters motor vibrations to keep the sensor data clean.

<br>
<br>

---

<br>

## **5. REPOSITORY STRUCTURE**
<br>

*   📂 **/Transmitter_Nano**: Joystick-to-NRF24 broadcast code.
*   📂 **/Receiver_Nano**: NRF24-to-PPM translation code.
*   📂 **/Flight_Controller_Nano**: Full MultiWii source folder.
*   📂 **/Calibration_Tools**: Specialized MPU6050 offset calculation scripts.
*   📂 **/MultiWii_GUI_Tools**: Visual interface for real-time sensor monitoring.

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

**Please STARRING this repository to help other student engineers find this resource!**

<br>
<br>
