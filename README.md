# Custom-Boot-Loader-with-Secure-Boot-and-Firmware-Update-capabilities
This is a Mini Project for College 
🔥 Optiboot Bootloader Burning Using Arduino UNO as ISP

A Mini-Project for Embedded Systems / VLSI Labs

📘 Project Overview

This project demonstrates how to burn the Optiboot bootloader onto a target Arduino Uno / ATmega328P/328PB using another Arduino Uno configured as an ISP programmer.
The objective is to learn and showcase:

Custom bootloader flashing

Reducing bootloader size and improving upload speed

Using Arduino-as-ISP for low-level programming

Understanding boot processes and fuses in AVR microcontrollers

This mini-project is ideal for students working with Embedded Systems Design or Microcontroller Programming courses.

🚀 Features / What This Project Includes

Custom Optiboot compiled for ATmega328P/328PB

Ability to modify:

Baud rate

LED pin

Watchdog behavior

Flash size targets

Arduino Uno used as ISP (In-System Programmer)

Burning fuses + flashing bootloader using avrdude / Arduino IDE

A test “Blink” sketch to confirm successful installation

🛠 Hardware Requirements

1 × Arduino UNO (ISP Programmer)

1 × Arduino UNO (Target Board)

Jumper wires (Male–Male)

USB cable

External 10µF capacitor (optional but recommended to disable auto-reset on ISP Uno)

🔌 Wiring Diagram (Uno → Uno)
ISP Programmer UNO	Target UNO
10 (RESET)	RESET
11 (MOSI)	MOSI (11)
12 (MISO)	MISO (12)
13 (SCK)	SCK (13)
5V	5V
GND	GND

Add a 10µF capacitor between RESET and GND on the programmer Uno.

📥 Software Used

Arduino IDE / Arduino CLI

Optiboot bootloader source

avrdude (bundled with Arduino IDE)

🔧 Steps Performed in the Project
1️⃣ Prepare the ISP Programmer

Uploaded ArduinoISP sketch to the programmer UNO.

Disabled auto-reset using 10µF capacitor.

2️⃣ Setup Optiboot

Edited boards.txt to add support for custom Optiboot build.

Set custom baud rate (optional).

Compiled Optiboot using:

make atmega328


or selected Burn Bootloader from the Arduino IDE.

3️⃣ Burn the Bootloader

Used Arduino IDE or Arduino CLI:

Arduino IDE Method:
Tools → Programmer → Arduino as ISP
Tools → Burn Bootloader

Arduino CLI Method:

arduino-cli burn-bootloader -b arduino:avr:uno -P arduinoisp

4️⃣ Upload Blink Test Program

After burning, a Blink program was uploaded at the new bootloader baud rate to verify successful flashing.

✨ Expected Outcomes

Optiboot successfully installed

Reduced boot time

Faster upload speed (115200/230400 depending on config)

Extra 1.5 KB flash memory available for sketches compared to stock bootloader

Verified operation via Blink LED program
