# [Sharp X68000](https://en.wikipedia.org/wiki/X68000) for [SoCkit (MiSTer) Platform](https://github.com/sockitfpga/MiSTer_SoCkit) 

Ported from [MiSTer Platform](https://github.com/MiSTer-devel/X68000_MiSTer).

Add this to the end of MiSTer.ini file

```
[X68000]
vga_scaler=1
forced_scandoubler=0
```



### Follows original readme:

This is the port of the [Sharp X68000](http://fpga8801.seesaa.net/category/24786679-1.html) core by Puu-san.

## Work in progress...

### Supported storage
* FDD *.d88 images
* SASI HDD *.hdf images

### Additional info
- Supported MT32-pi over USER I/O port.

### Installation
Copy *.rbf to SD card. Copy boot.rom and boot3.vhd to Games/X68000 folder.
You can use BLANK_disk_X68000.D88 if you need to make a new FDD image (or for saves).
