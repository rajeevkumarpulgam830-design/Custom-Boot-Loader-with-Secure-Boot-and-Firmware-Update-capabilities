1️⃣ boot.h — Bootloader Configuration & Core Definitions

This header file contains key configuration settings used by the Optiboot bootloader. It defines:

Bootloader size and memory boundaries

CPU frequency

Upload baud rate

LED pin configurations

Watchdog settings

Flash page size and timeout values

Purpose:
boot.h acts as the main configuration file that tells Optiboot how the microcontroller should boot, what speed it should communicate at, and how large the bootloader region should be.

2️⃣ Makefile — Build Script for Bootloader Compilation

This file contains instructions for compiling the Optiboot bootloader using the GNU AVR toolchain.

It specifies:

Target microcontroller (e.g., ATmega328P/328PB)

Compiler flags (optimization, warnings, flash size)

Flashing commands using avrdude

How to create .hex and .elf bootloader files

Fuse settings for the chip

Purpose:
Makefile automates the entire build process.
With a single command like:

make atmega328


You can:
➡ Compile the bootloader
➡ Generate hex files
➡ Burn fuses + flash the bootloader

It is the automation backbone of the Optiboot project.

3️⃣ optiboot.c — The Main Bootloader Source Code

This is the heart of the Optiboot bootloader — the main C file that runs inside the bootloader region of the ATmega microcontroller.

It implements:

Bootloader start-up sequence

Communication protocol (STK500v1)

Reading & writing flash memory

Handling serial data

Watchdog reset handling

Jumping to the main application

Purpose:
optiboot.c contains the core logic that receives the program from the computer and writes it into flash memory.
This is the file that literally defines how Optiboot works.

4️⃣ pin_defs.h — Board- and MCU-Specific Pin Definitions

This header file defines all pin mappings used by the bootloader, including:

LED pin for bootloader activity

UART TX/RX pin assignments

SPI pins (MOSI, MISO, SCK)

Conditional definitions for different ATmega chips

Purpose:
pin_defs.h ensures that Optiboot works correctly on different AVR microcontrollers and Arduino boards by mapping hardware pins → bootloader functions.

It acts like a “pin translation layer.”

5️⃣ stk500.h — STK500 Protocol Constants & Commands

This file defines all the commands, constants, and responses used in the STK500v1 protocol.

It includes:

Command codes (e.g., STK_GET_SYNC, STK_READ_PAGE)

Response bytes (e.g., STK_INSYNC, STK_OK)

Packet structure

Error codes

Purpose:
stk500.h tells Optiboot how to communicate with avrdude, which uses the STK500 protocol to upload sketches.
Without this file, Optiboot wouldn’t understand upload commands.
