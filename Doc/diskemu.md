SD card-about disk emulator

Create a disk image on a FAT (FAT16 / FAT32) formatted MicroSD card (including MicroSDHC) and create a disk image.
This function emulates FDD, SASI-HDD, and SRAM.
Software emulation with a Nios II processor running on an FPGA.
FDD emulation has a complete user interface but still doesn't work.

Emulation works from power-on, but on the main unit and emulator
Since the screen and keyboard are shared, refer to the explanation of the main unit for which one to connect to.

1. How to use
Formatted to MicroSD card connector before powering on DE0-CV (contents may be destroyed)
Insert the SD card.
When the power is turned on, the configuration file (".config.xxx" in the root directory (xxx part depends on the model of the main unit)
Open (different). If not, it will be created automatically.

The emulator screen shows the status of each drive written in the configuration file.
During the emulation operation of each drive, the left side of the drive list lights up in red.
The keyboard may not respond during drive emulation.

Change the drive to operate with the up and down cursor keys on the keyboard, and press [Enter] or [Space].
You can change the drive status. At the bottom line, remount the LOAD, STORE and SD card of the configuration file
(Run after media replacement) can be selected.

The changes will depend on the drive type.
・ NONE (FDD, HDD) No drive
・ DRIVE 0 (FDD) Connect to physical drive 0
・ DRIVE 1 (FDD) Connect to physical drive 1
-Select a FILE (FDD, HDD, SRAM) file and assign it to the drive
・ NEW (FDD, HDD, SRAM) Create a new file or enter the file name directly and assign it to the drive.
-EJECT (FDD) drive available, eject status
・ STORE (SRAM) SRAM value is saved in a file
-LOAD (SRAM) Read a file into SRAM

2. Regarding SRAM
The contents of SRAM (nvram) are not automatically saved in a file. Whenever you need to save
Please execute "STORE".

3. About SASI HDD
Currently, it does not support the RESET signal, so if the drive is busy and you want to reset it.
It freezes while still busy.
Turn off the power once (KEY0 of the push switch is OK) and then turn it on again.