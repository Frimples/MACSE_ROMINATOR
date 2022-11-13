# MACSE_ROMINATOR

Project to create a Macintosh SE compatible ROM with the ROM Disk Booting of the ROMINATOR.

Original Project here for the Mac Plus ROM:

http://synack.net/~bbraun/plusrom/index.html

In part for PiStorm Booting with SoftROM that can be larger than 256K.

Greetings,

I've gotten the PiStorm to boot on my Mac SE with a softROM file of the Mac SE FDHD base ROM.


Floppy and SCSI are not fully functional and since I can make the ROM bigger than stock I am attempting to implement the "ROMINATOR I" driver in the Mac SE ROM to allow me to add a ROM Disk for booting.

From this post on the ROMINATOR I have:

1. Disabled the ROM Checksum (I just put in the end routine jump on the first line of the routine).
2. Concatenated the ROM Driver to the end of the ROM (0x040000).



From reading the instructions on how the original ROMINATOR was put together I need to:



1. Find a driver unused by the Mac SE ROM for the resource number.
2. Set the Sound Driver to jump to the ROM Disk driver at 0x040000.
3. Modify the ROM Disk driver to jump back to the Sound driver...or add the sound driver either at the end or in the photo Easter Egg part of the SE ROM.



At that point I can Concatenate a disk image to the modified ROM and attempt booting.
