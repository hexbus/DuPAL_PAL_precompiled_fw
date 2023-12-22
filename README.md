# DuPAL_PAL_precompiled_fw
Precompiled Firmware for the DuPAL PAL Board
version 0.1.2

This is a precompiled version of the DuPAL firmware from https://github.com/DuPAL-PAL-DUmper/DuPAL_Firmware with an included Optiboot bootloader from https://github.com/Optiboot/optiboot.

The DuPAL repository assumes that the user building the device also has software development skills, and, as such, does not get into much detail on how to properly build the firmware for the device.  So, I've decided after going through all the hard work of learning how to compile this myself to make this firmware available to others who just want to download it themselves.

This image is simply a "dump" read by my EEPROM programmer of the AtMega 328P after it was programmed with the DuPAL Firmware and OptiBoot.  Both DuPAL and Optiboot run at the standard 16MHz clock speed, and serial is at 57600.

Here are the fuse settings I used to program this image to an AtMega 328P with my device programmer, which is a Dataman 48Pro2:

* high_fuse_val.hex = 0xd6
* efuse_fuse_val.hex = 0xfd
* low_fuse_val.hex = 0xff

Here is how I test that the board is operating properly:

* Plug in the DuPAL without an IC in either of the PAL slots.
* Plug in your serial to USB (or put an FTDI cable on pins 9-12 of U3 I believe, if you do not want to use a MAX232).
* Open PuTTY or whatever, set your COM port to 57600 8N1.
* Turn on DuPAL.

You should see:

DuPAL - 0.1.2

REMOTE_CONTROL_ENABLED

* Next, press the reset button.
* The LEDs should flash around 8 times.
* You then get another Remote Control message.
* Your DuPAL is now operational.
