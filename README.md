# NES LEARNING

## NES hardware(Console)
Main component of the nes board will be:
- CIC - Checking integrated chip: 
    1. This chip runs 10NES, an internal program that checks for the existence of another lockout chip in the game cartridge. This chip sends some data to the catridge to check, if the data is matched then the cartridge is official nintendo cartridge.
    2. If the CIC 10NES check fails, the console is set to infinte reset.
    3. The CIC exists becausse of the video game crash of 1983. Japanese version of the NES the 'famicon' was designed before the 1983 crash so the famicon does not contain the CIC chip. 
- CPU - NES was powered by RICOH 6502 compatible CPU.  This was not the official 6502 processor. 
    1. There were 2 types of the RICOH 6502 chips, depending on the region and display standards:
        - Ricoh 2A03(NTSC)
        - Ricoh 2A07(PAL)
    2. The instruction set is compatible with the 6502 processor.
    3. This chip was formed by disabling the BCD(Binary decimal code) mode on the chip.
    4. Speed of the processor is 1.79 MHz.
    5. 1.79 million instructions per second.
    6. It is an 8-bit microprocesor.
    7. This is not just a CPU, it contains an APU(Audio processing unit) on the same die(chip).
- RAM: 2KB of internal WRAM(Work RAM) that CPU has access to.
    1. The NES maps the internal RAM from $0000 to $0800.($0800 is 2048 in decimal).
    2. Does that mean that every NES game could only use 2KB of RAM and that's it? No - Some games added extra RAM right on the carttridge.
- PPU - Picture processing unit - Responsible for rendering the graphics on the monitor.
    1. Our code does not run on the PPU. CPU sends instructions(signals) to the PPU to modify the scrolling, colors, etc.
    2. The PPU always performs the same display order, processing one TV scanline at a time.
- VRAM - Video RAM - PPU has access to the VRAM. It is 2KB of memory.
    1. The 2KB of VRAM are used to hold the data for 2 nametables(1KB each).
    2. A PPU nametable describes the layout of a frame's background. Each nametable holds information  of 32x30 tiles of background and rheir color attributes.

## NES Cartridge

