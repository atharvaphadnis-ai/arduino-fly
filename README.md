DIY Triple-Nano Drone: Modular NRF24L01 Flight System
🚁 Project Overview
This project is a custom-engineered quadcopter system developed for the Inspire Award. Unlike standard flight controllers, this system breaks down the drone's "nervous system" into three dedicated Arduino Nano microcontrollers. This modular approach ensures high-speed signal processing, wireless reliability using the NRF24L01+PA+LNA, and a "Pure Arduino" environment for full control over flight dynamics.
🛠 Hardware Architecture (The Triple-Nano Setup)
The drone operates using three distinct modules:
Transmitter (TX): Reads joystick movements and sends data wirelessly.
Receiver (RX): Receives wireless packets and generates a PPM (Pulse Position Modulation) signal.
Flight Controller (FC): Processes the PPM signal and uses an MPU6050 to stabilize the 4 brushless motors via MultiWii firmware.
🔌 Wiring Specifications
1. Transmitter (TX) Wiring
Component	Arduino Nano Pin
NRF24 VCC	3.3V (Use 10uF Capacitor)
NRF24 GND	GND
NRF24 CE	D9
NRF24 CSN	D10
NRF24 SCK	D13
NRF24 MOSI	D11
NRF24 MISO	D12
Joystick Roll	A0
Joystick Pitch	A1
Joystick Throttle	A2
Joystick Yaw	A3
2. Receiver (RX) Wiring
Component	Arduino Nano Pin
NRF24 VCC	3.3V
NRF24 GND	GND
NRF24 CE	D9
NRF24 CSN	D10
PPM Signal Out	D2 (Connects to FC D2)
3. Flight Controller (FC) Wiring
Component	Arduino Nano Pin
MPU6050 VCC	5V
MPU6050 GND	GND
MPU6050 SDA	A4
MPU6050 SCL	A5
PPM Input	D2 (From RX Nano)
Motor 1 (Front R)	D3 (ESC Signal)
Motor 2 (Rear R)	D10 (ESC Signal)
Motor 3 (Rear L)	D9 (ESC Signal)
Motor 4 (Front L)	D11 (ESC Signal)
💻 Software & Configuration
Module 1: Transmitter Code
The TX code captures analog joystick values and maps them to a 0-255 byte range. It uses a low data rate (250KBPS) to ensure maximum range and signal penetration. The "Pipe Address" is set to a unique hex code to prevent interference with other drones.
Module 2: Receiver Code
The RX code converts the wireless data into a standard PPM stream. This allows 7 channels of data to travel over a single wire to the Flight Controller. It includes a "Fail-Safe" function: if the signal is lost for more than 1 second, the throttle is automatically set to 0 to prevent fly-aways.
Module 3: Flight Controller (MultiWii)
The config.h file in the MultiWii directory has been pre-configured with:
Frame: QUAD-X orientation.
Sensor: GY-521 (MPU6050) enabled.
Input: SERIAL_SUM_PPM enabled on Pin D2.
Filter: MPU6050 Low Pass Filter set to 42Hz to eliminate motor vibration noise.
⚖️ Calibration Procedures
MPU6050 (IMU) Calibration
Upload the MPU6050_Calibration.ino script found in the repository.
Place the drone on a perfectly level surface.
The script will generate X, Y, and Z offsets.
These offsets ensure the drone knows exactly what "level" is, preventing drifting during flight.
ESC Calibration
In config.h, uncomment #define ESC_CALIB_CANNOT_FLY.
Upload to FC Nano.
Connect battery (without propellers!). Wait for beeps.
Disconnect battery, comment the line back, and re-upload.
🚀 Getting Started
Clone the Repo: Download all folders to your local machine.
Libraries: Install the RF24 and Wire libraries via the Arduino IDE Library Manager.
Upload: Follow the folder names to upload the specific code to each of your three Nanos.
Connect: Use the wiring tables provided above.
GUI: Use the MultiWiiConf tool in the provided .rar file to visualize your drone sensors in real-time.
If you find this project helpful for your own drone builds or science fair entries, please consider FORKING this repository to save your own version or STARRING it to show your support!
