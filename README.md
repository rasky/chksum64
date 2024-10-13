This tool allows to fix the checksum in Nintendo 64 ROM headers.

Nintendo 64 ROMs contain a boot code called IPL3. All official IPL3 that
were released by Nintendo during the course of the console commercial life 
required the header of the ROM to contain a 6-byte checksum (using a custom
hash function) of the first megabyte of data (which is the data being loaded
at boot). 

Different IPL3 variants were released for different versions of the CIC
protection chips (part of the game cartridges); the hash function is always
the same but a 32-bit seed changed.

This tool allows to calculate the correct checksum for that data and writes it
to the header in the correct position. The tool currently only works for ROMs
using the IPL3 for CIC 6101/6102, because it hardcodes the valid seed for them.

This tool used to be part of [Libdragon](https://github.com/DragonMinded/libdragon)
but it's not shipped there anymore as Libdragon moved to an open source IPL3
that doesn't require a checksum anymore. It was republished here for posterity.

References: 
* https://n64brew.dev/wiki/ROM_Header
* https://n64brew.dev/wiki/PIF-NUS#IPL3_checksum_algorithm

Derived tools:
* http://n64dev.org/n64crc.html Derived version that supports all the CICs.
