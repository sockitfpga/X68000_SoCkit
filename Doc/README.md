FPGA version X68k compatible machine readme:
This RTL rewrites the FPGA of DE0-CV (TERASIC)
It has the function equivalent to X68000.

This RTL is free software.
-IP of MC68000 MPU: TG68 is copyrighted by Tobias Gubener.
-The font used for the disc emulator is the original Shinonome font.

For other RTLs, I'm in Pooh.
There is no guarantee for the files contained in this RTL. All responsibility including secondary damage
I will not bear it.

For malfunctions, blog
http://fpga8801.seesaa.net/
Please contact us by the message or comment in.

how to use:
This RTL is mainly developed in Altera's development environment QuartusII web edition.
This distribution is also packaged by the archive function of Quartus II.
Deploy this RTL with Project → Restore archived project
(I think it's done when this file is open)
I will compile, but due to license etc., the files required for compilation are
Some are missing.
-BIOS / CGROM.hex
Font data. It is sucked out from the actual machine or created by the Windows version emulator.
Convert CGROM.BIN or CGROM.TMP to intel hex.
Since it exceeds 64kB (over the segment in x86), please convert it with the corresponding conversion software.

When the above preparations are complete, compile with Start Compilation.
After the compilation is completed, write the IPLROM and the CGROM prepared above to the Flash for FPGA initialization.
Preparation is required.
Quartus II File → Convert Programming File
Click "Open Vonversion Setup Data ..." from
X68k_DE0CV.cof
please choose. Then click Advanced and go to Disable EPCS ID check
Please check it. Exit Advanced options with OK and click "Generate"
Click to generate the X68k_DE0CV.pof file.
Write to the DE0-CV board in Active Serial mode.

Regarding the switch,
-Main power switch: The power switch of the main unit.
・ IPL reset switch: Leftmost (small) of push switch
・ Power switch (front): Rightmost of the large push switch
・ NMI switch: The second largest push switch from the right
A function for debug is set for a part of the 10-slide switch.
From the right
・ First: Reset at regular (several seconds) intervals
・ Third: CPU PAUSE
is.

The SD card looks like a SASI HDD. SDSC (not SDHC or SDXC
Use a MicroSD card with a standard capacity).
Since the SD card is used as a disk instead of a file system, the contents are initialized and
Please note that you will not be able to operate files from other systems.
Since it is used as an HDD, it cannot be inserted or removed during operation. Main power or power supply
Please insert and remove it in the OFF state.

FDD is used as auxiliary storage.
As of 2015, 3.5 "for 1.44MB (for AT compatibles) is available as a drive.
I think it is the only one, so I can connect this drive.
Since the built-in main body of X68000 is 2 drives, it is possible to connect 2 drives,
For connection, the signal from the main unit is sent to the FDD cable for AT compatibles.
(34-core cable with 3 connectors for 2 drives and partially twisted)
It will be converted to and connected.
For connection, included
pin-assign.xls
Please refer to. Since it has the same wiring as the PC-8801 version, it can be used as it is.
For media, use 2HD media.
Since FDD is for AT compatible machines, I think that FDD initialized with X68000 cannot be read.
(X68000: 360rpm, AT: 300rpm)
It may be possible to read by connecting a 360 rpm FDD (for PC-98 etc.).
If you connect a 5 "2HD FDD, you may be able to read and write 5" media as it is.
(5 "FDD for AT is 360rpm.)

Use Virtual Floppy Image Converter to write data to the FDD
Convert from XDF to D88, write to 3.5 "2HD using DITT, and normally
I confirmed that it works.

For the disk emulation version using SD card, the included emulator
See the description, "diskemu.txt".
A slide switch for switching between the main screen and disk emulation screen on this unit.
Assigned to SW1.