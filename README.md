# LPC ROM emulator on USB dongle FPGA core set

Freed from http://opencores.org/project,usb_dongle_fpga

Information below is from the project's website on opencores.org.

Short dongle user guide by coreboot.org:
https://www.coreboot.org/FlexyICE

Original project maintainer: Toomessoo, Jüri

Created: Dec 7, 2006  
Updated: Mar 10, 2009  
Category: Communication controller  
Language: VHDL  
Development status: Stable  
Additional info: FPGA proven  
WishBone Compliant: No  
License: LGPL  

## Main features of latest v5 HW are:

- LPC memory read (can be disabled),LPC Firmware Hub memory read and IO write for POST Code capture (and display on LED segments)
- POST code peek mode (LPC reads from dongle are disabled)
- POST code logger (sends all postcodes to USB serial port as hexadecimal bytes in ASCII)

This is hardware project for existing USB dongle board (costing about 150 EUR you should check from sales(at)artecgroup.com).
Using it for LPC dongle.

## IP cores

- LPC slave (supporting IO write, Memory read and LPC Firmware Hub read from device ID 0x0000)
- Flash Waveform generator
- FTDI parallel interface to onboard flash (supports 32 byte block write and 64K block read)
- FTDI parallel interface to convert and send bytes as hex codes in ASCII
- Scanning LED segment display coder

## Status
- HW cvs tag HWVersion_1_0 released (HW code 3)
- Software cvs tag SoftVersion_1_1 released (dongle.py script version 1.1)
- HW/Software bundle cvs tag version_1_4 released (bug fixes and added LPC Firmware hub [FWH] read). Contains HW version code 4 and dongle.py script version 2.0
- HW/Software bundle cvs tag version_1_5 released (Added Post code logger hardware, fast block read hardware and fast read flow control hardware. Updated software to support all the new hardware and older HW in legacy mode). Contains HW version code 5 and dongle.py script version 2.5

## PCB Board

http://www.artecgroup.com/en/flexyice

- Cyclone FPGA EP1C6T144C8N
- Serial Platform Flash
- Intel Strata Flash E28F128 (16MB) in 16 bit mode
- FTDI parallel to USB bridge FT245BM
- 4 segment LED display

## Downloads

 Hardware, software and Quartus project bundle for v5 hardware
https://github.com/flashrom/artec_dongle_fpga/blob/master/release/usb_dongle_v5_web_release.zip?raw=true

Datasheet for v5 hardware
https://github.com/flashrom/artec_dongle_fpga/blob/master/release/dongle_v5_datasheet_ver1_09.pdf?raw=true

Software and datasheet bundle for v5 hardware
https://github.com/flashrom/artec_dongle_fpga/blob/master/release/DongleTool_2_5.zip?raw=true

ALTERA EPCS configuration memory programmer tool (needs python and pyParallel), dongle v5 binary and diagram of ByteBlaster II hardware (older Altera cables like ByteBlaster MV won't work)
https://github.com/flashrom/artec_dongle_fpga/blob/master/release/EPCS_update_tool.zip?raw=true

LPC Dongle AD67441103 PCB schematic
https://github.com/flashrom/artec_dongle_fpga/blob/master/doc/441103_DONGLE_SCHEMATIC.pdf?raw=true

LPC Dongle AD67441104 PCB schematic
https://github.com/flashrom/artec_dongle_fpga/blob/master/doc/441104_DONGLE_SCHEMATIC.pdf?raw=true
