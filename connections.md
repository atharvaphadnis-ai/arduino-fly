# 🔌 **HARDWARE CONNECTION GUIDE**
<br>

## **1. TRANSMITTER (TX) NANO**
<br>

**NRF24L01+PA+LNA Module Connection:**
*   **VCC**  ->  Nano **3.3V** (Solder a 10uF capacitor here for stability)
*   **GND**  ->  Nano **GND**
*   **CE**   ->  Nano **D9**
*   **CSN**  ->  Nano **D10**
*   **SCK**  ->  Nano **D13**
*   **MOSI** ->  Nano **D11**
*   **MISO** ->  Nano **D12**

<br>

**Analog Joystick Connection:**
*   **Roll (X-Axis)**     ->  Nano **A0**
*   **Pitch (Y-Axis)**    ->  Nano **A1**
*   **Throttle (Y-Axis)** ->  Nano **A2**
*   **Yaw (X-Axis)**      ->  Nano **A3**

<br>
<br>

---

<br>

## **2. RECEIVER (RX) NANO**
<br>

**NRF24L01 Module Connection:**
*   **VCC**  ->  Nano **3.3V**
*   **GND**  ->  Nano **GND**
*   **CE**   ->  Nano **D9**
*   **CSN**  ->  Nano **D10**
*   **SCK**  ->  Nano **D13**
*   **MOSI** ->  Nano **D11**
*   **MISO** ->  Nano **D12**

<br>

**Signal Bridge to Flight Controller:**
*   **PPM Signal Out** ->  Nano **D2** (Connect this to the FC Nano D2)

<br>
<br>

---

<br>

## **3. FLIGHT CONTROLLER (FC) NANO**
<br>

**MPU6050 (Gyro/Accel) Connection:**
*   **VCC**  ->  Nano **5V**
*   **GND**  ->  Nano **GND**
*   **SCL**  ->  Nano **A5**
*   **SDA**  ->  Nano **A4**

<br>

**Electronic Speed Controller (ESC) Signals:**
*   **Motor 1 (Front Right)** ->  Nano **D3**
*   **Motor 2 (Rear Right)**  ->  Nano **D10**
*   **Motor 3 (Rear Left)**   ->  Nano **D9**
*   **Motor 4 (Front Left)**  ->  Nano **D11**

<br>

**Input from Receiver:**
*   **PPM Input** ->  Nano **D2** (Connect from RX Nano D2)

<br>
<br>

---

<br>

## **⚠️ CRITICAL POWER NOTE**
<br>

**Shared Ground (GND):**
You **MUST** connect a wire between the **GND** pin of all three Nanos. If they do not share a common ground, the PPM signal will be "noisy," and the drone will not fly safely.

<br>

**NRF24 Power:**
The NRF24L01+PA+LNA (with antenna) draws a lot of current. If your Nano cannot supply enough power, the connection will drop. Always use a capacitor (10uF to 100uF) across the VCC and GND pins of the NRF24 module.

<br>
<br>

---

<br>

## **📬 CONTACT & FEEDBACK**
<br>

If you find something wrong with these connections, please **Gmail me at atharvaphadnis8@gmail.com**.

<br>
<br>

---

<br>

## **⭐ SUPPORT THE PROJECT**
<br>

**Please FORK this repository to save a copy for your own edits!**

<br>

**Please STAR this repository to help other student engineers find this resource!**

<br>
<br>
