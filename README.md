
🚁 Triple-Nano Modular Drone System

An open-source, fully functional quadcopter built from scratch using three dedicated Arduino Nano microcontrollers and the NRF24L01+PA+LNA wireless communication module, developed for the Inspire Award (MANAK). This project replaces traditional all-in-one flight controllers with a modular "Pure Arduino" architecture to maximize processing loops and provide a transparent educational platform.

🏗️ Architecture & Component Breakdown

• Transmitter (NRF24_Transmitter): Reads raw analog joystick inputs, maps them to a single-byte payload (0–255), and transmits them via the NRF24L01+PA+LNA module.
• Receiver (NRF24_Receiver): Decodes incoming wireless packets and outputs a clean Pulse Position Modulation (PPM) stream over a single wire to the flight controller.
• Flight Controller (Flight_controller_code): Runs a customized MultiWii configuration using data from an MPU6050 IMU to execute high-speed PID stabilization loops.

##📁 Repository Overview & Tools##

The repository includes core source files for the transmitter, receiver, and flight controller, alongside a high-precision sensor calibration script (mpu6050_calibration.ino) and physical connection guides. Users can refer to the repository files for complete code implementations and use the MultiWii GUI for live performance tracking. Detailed pin mappings and assembly instructions are documented within the repository's connections.md file.

📬 Support & Contact

For questions, compilation support, or feedback, contact the developer at atharvaphadnis8@gmail.com, or star and fork the repository on GitHub.
