# Arduino, IoT and Embedded Projects

A collection of IoT and embedded systems projects — the kind of work that sits between
hardware and software. Microcontrollers, sensors, wireless communication, and the code
and PCBs that tie them together. Most projects here started as a real problem to solve
and ended with a working prototype, a custom PCB, and a short write-up of what was
learned.

## What is in this repository

Each project lives in its own folder with the firmware source code, a project write-up,
hardware notes, and — where applicable — a link to the matching PCB design in the
PCB-Design-Projects repository.

## Projects

### 1. Biometrics Enhanced School Feeding Programme (IoT-Based)

Final year engineering project. An IoT system that verifies a student's identity by
fingerprint before allowing them to be served a meal, and lets parents pay for meals
through M-Pesa.

**What it does**

- Verifies a student's fingerprint using an AS608 sensor before meal service
- Displays student name, status, and payment information on an OLED screen
- Uses LEDs and a buzzer to indicate success, failure, or insufficient balance
- Records attendance and meal events to a Firebase database in real time
- Parents top up a student's meal balance through M-Pesa STK Push (Daraja API)
- Balance is checked against the student's account before the meal is approved

**Hardware used**

- ESP32 microcontroller
- AS608 fingerprint sensor
- OLED display (SSD1306)
- LEDs, buzzer
- Resistors, capacitors, and supporting passives
- Custom PCB (designed in KiCad, fabricated and populated as a prototype)

**Software and services**

- Arduino IDE (ESP32 board package)
- Firebase Realtime Database (or Firestore — see project notes)
- M-Pesa Daraja API for STK Push payments
- HTTP client on the ESP32 for Firebase and Daraja calls

**Status**

Working prototype, tested end-to-end with simulated student accounts and real STK
Push responses. PCB fabricated and populated.

**Folder contents**

- `src/` — ESP32 firmware
- `docs/` — Circuit description, block diagram notes, database schema
- `images/` — Photos of the prototype and the fabricated PCB
- `README.md` — This project's own detailed write-up (in the project folder)

**Related PCB**

See the PCB-Design-Projects repository for the board used in this project.

---

### 2. Autonomous 4-Wheel Robot

A small autonomous robot that drives on its own, avoids obstacles, and navigates a
space using ultrasonic sensors mounted on the chassis.

**What it does**

- Drives using four motors controlled through a motor driver
- Senses obstacles using ultrasonic sensors
- Makes basic navigation decisions (stop, turn, reverse, continue)
- Runs entirely on-board, no external computer required

**Hardware used**

- ESP32 microcontroller
- Four DC motors with driver
- Two or more ultrasonic sensors
- Chassis, battery pack, and supporting components
- Custom PCB (designed in KiCad, fabricated and populated)

**Software**

- Arduino IDE (ESP32 board package)
- Motor control and sensor libraries (declared in the project README)

**Status**

Working prototype — drives, senses, and avoids obstacles as intended.

**Folder contents**

- `src/` — ESP32 firmware
- `docs/` — Wiring notes and behaviour notes
- `images/` — Photos of the build
- `README.md` — This project's own detailed write-up

**Related PCB**

See the PCB-Design-Projects repository for the board used in this project.

---

### 3. Smart Parking and Management System (with M-Pesa Integration)

A parking system that detects when a lot is occupied, manages entry and exit through a
servo-controlled gate, and lets users pay for parking through M-Pesa. Includes a web
dashboard for monitoring the parking area in real time.

**What it does**

- Detects occupancy of each parking lot using infrared sensors
- Opens and closes the entry and exit gates with servo motors
- Bills users for parking time through M-Pesa Daraja API
- Sends session data to a web application for live monitoring
- Shows available and occupied lots on the dashboard

**Hardware used**

- ESP32 microcontroller
- Infrared sensors (one per parking lot)
- Servo motors for gate control
- Gate mechanism and mounting
- Custom PCB (designed in KiCad, fabricated and populated)

**Software and services**

- Arduino IDE (ESP32 board package)
- M-Pesa Daraja API
- A web application for the dashboard (see project notes for stack)
- Firebase or a similar backend for session data

**Status**

Working prototype — infrared detection, gate control, M-Pesa checkout, and dashboard
display all tested together.

**Folder contents**

- `src/` — ESP32 firmware
- `web/` — Web dashboard source
- `docs/` — System architecture, database schema, API notes
- `images/` — Photos of the prototype
- `README.md` — This project's own detailed write-up

**Related PCB**

See the PCB-Design-Projects repository for the board used in this project.

---

## Getting started

1. Clone the repository:
git clone https://github.com/HenryOyoto/Arduino-IoT-and-Embedded-Projects.git


2. Open the folder of the project you want to explore. Each has its own README with
hardware requirements, wiring, and upload instructions.

3. Most projects use the Arduino IDE. Where a project uses PlatformIO or another
toolchain, that is stated in its README.

## Tools used across projects

- Arduino IDE
- ESP32 board package
- KiCad (for the custom PCBs referenced here)
- Firebase (database, in the projects that use it)
- M-Pesa Daraja API (in the projects that use it)

## Notes

- These projects are written for clarity and documentation, not for production
deployment. They are meant to be read, understood, and adapted.
- Where a library version matters, it is noted in the project's own README.
- Where a project uses a paid or external API (M-Pesa Daraja, Firebase), the README
explains what you need to set up to run it yourself.

## About

Maintained by Henry Oyoto — Electronics and Computer Engineer working in PCB design,
Python programming and technical documentation.

- GitHub: https://github.com/HenryOyoto
- LinkedIn: https://www.linkedin.com/in/henryoyoto
- Email: oyotohenry2021@gmail.com

## License

Unless a project states otherwise, the code in this repository is provided under the
MIT License. You are free to use, modify and share it, with attribution.
