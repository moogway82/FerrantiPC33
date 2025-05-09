# FerrantiPC33

A simple repo which collects together the information I found whilst troubleshooting the Ferranti PC33 motherboard.

The schematics are incomplete and just what I could find out from beeping out various signals.

## The ULAs and PALs

### ULA 5RA022E-2
This appears to replicate the functionality from Sheet 2 of the IBM PC 5150/XT 5160 Technical Reference Manuals: Wait states, DMA Arbitration, NMI/Parity Checks, etc...

### ULA 5RA023E-2
This appears to replicate the keyboard functionality from Sheet 9 of the IBM PC 5150/XT 5160 Technical Reference Manuals and also the PCLK / 2 to give the 1.19 MHz for the PIT.

### ULA 5RA024E-3
Dunno :) I didn't trace a single signal back to this chip during the course of troubleshooting the board - serial maybe?

### PAL 1751/1 (I think label missing?)
I believe that this is part of the 16/8bit bus convertor state machine. The 74F193 acts as a counter to step through the different bus signals on the ISA bus to do reads and writes and latch the bytes to feed back to the CPU. I used the excellent Olivetti M21/M24 Theory of operation as an example of a similar system to do bus conversion for 8086 CPUs with an 8bit ISA bus.

### PAL 1752/1
Not sure, seems to also play a part in doing bus transfers.

### PAL 1753/1
Not sure, I think it might be decoding chip selection for the PIT/PIC/PPI, etc...

