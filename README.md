# TRS-512k
![Development in progress](./img/main.jpg)
This is my Z80 computer. Everyone designs one, but this one is mine.
This started as an attempt to make a TRS-80 Model 1 compatible [Expansion Interface](https://alnwlsn.com/projectrepository/index.php?title=TRS-80_Model_1_-_Wilson_Expansion_Interface) and then quickly got out of hand when I realized I could easily make the rest of the computer too.
It is mostly (but not quite) compatible with the TRS-80 Model 1. The system is based around 100mm x 100mm PCBs, which is the loss-leader size you can get from JLCPCB or PCBWay. As a result, the system assembles into a cube shape.

The name comes from the 512K of SRAM I picked for the main memory. By coincidence, 512000 also happens to be 80 (from TRS-80) cubed!

This isn't really a product or even much of a project with direction; it's just that in these modern times you can design and have made circuit boards with stupidly little effort. I built this because nobody stopped me from building it, I guess. However, it did teach me a lot about PCB design, digital electronics, programming, and how microcontrollers and computers really work at the lowest level.

In progress since about 2020, and slowly going online; this is a low priority.

Current features are:
* Backplane design with dual row pin headers instead of card edge connectors
* Mostly discrete 74 logic ICs, period correct higher function chips, and GALs (for address decoding), no FPGA/CPLD
* A mixture of through hole and SMD parts, whatever I could find in stock / cheaper
* Z80 CPU at 1.78, 2, 2.28, 2.66, 3.2, 4, 5.33 or 8 MHz
* 512K of battery backed SRAM, and 512K ROM, organized as 64 pages of 16K each, which can be inserted at 0000, 4000, 8000, or C000 in Z80 address space
* Supports use of cassette tape drive for storing / loading data
* Real time clock via phantom time chip
* Keyboard with TRS-80 Model 1 compatible layout and memory map (relocatable also)
* For use as TRS-80 EI: an extra RAM board which has another 512K, an Arduino compatible microcontroller (or ESP32) with dual port RAM to share between Z80 and Arduino
* Full Expansion Interface functions: 40 Hz heartbeat interrupt signal, printer port, floppy disk controller with doubler (uses either a INS1771 for single density + TRSDOS compatibility, or WD2793 for single / double density)
* Fully Model 1 compatible TR1602 UART RS-232 serial port
* Alpha joystick compatible (IO port 0), uses Atari joystick
* MC68B45 video board (dual port RAM), supporting 64x16 or 80x25 (and some other) text modes with redefinable character set
* Sound board supporting Orchestra 80/85, plus a handful of later FM sound synth chips thrown on for good measure
* One board on the top with just a bunch of blinking lights
* Programmers keypad "DSKY" attachment

## Keyboard
The [keyboard](./img/keyboard.jpg) is made using modern cheap Gatreon keyswitches, and blank DSA keycaps, to which I lasered on decals I drew up [this method](https://www.youtube.com/watch?v=JR1BwcFyexQ) which uses a laser and printer toner. The switches are wired in a key matrix which matches the original TRS-80, so it can read from the same hardware locations. There was room for a few extra keys in the matrix, so I added a few. Keycap font is [Hershey](https://en.wikipedia.org/wiki/Hershey_fonts) if you're curious.

