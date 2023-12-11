# ZX-RC2014-Adapter

This is a simple adapter PCB for connecting RC2014 bus format Z80 boards to the ZX Spectrum 48/128K.  The primary purpose is to test or use RC2014 boards against a real ZX Spectrum.

Notable features are:

* Four RC2014 slots
* Interface 2 ROM slot
* Configurable power options including powering RC2014 boards either from Spectrum or external supply

![Top view of ZX RC2014 Adapter](https://github.com/ZXQuirkafleeg/ZX-RC2014-Adapter/blob/main/Images/IMG_20231211_170946.jpg)

## RC2014 Bus

There are some differences between the RC2014 bus and the Spectrum edge connector signals.  Notably the CPU clock is inverted on the edge connector.  Spectrum peripherals also use ROMCS and NMI (e.g. DIVMMC and Multiface), so these are brought out to the user pins on the RC2014 bus:

*	Pin 37 – User 1 – /ROMCS
*	Pin 38 – User 2 – /NMI 
*	Pin 39 – User 3 – /WAIT
*	Pin 40 – User 4 – (unallocated)

J2 Connects the user pins to the ZX Spectrum edge connector.  +2/+3 /ROMOE signals are also jumpered but this is untested.

U1 is a clock inverter which negates the spectrum CPU clock (if required).

## Build
All components are though-hole and standard density.  A schematic can be found [here](https://github.com/ZXQuirkafleeg/ZX-RC2014-Adapter/blob/main/PCB/ZX%20to%20RC2014%20Adapter%20Schematic.pdf).

### PCB 

For the PCB, EasyEDA (V6.5.22) design files can be found [here](https://github.com/ZXQuirkafleeg/ZX-RC2014-Adapter/tree/main/PCB) and gerbers [here](https://github.com/ZXQuirkafleeg/ZX-RC2014-Adapter/blob/main/PCB/Gerber_PCB_ZX%20to%20RC2014%20Adapter.zip).  The PCB is a standard two layer board approx. 100mm by 100mm.  

## Jumpers and Connectors

* J1 – Connects RC2014 and ZX Spectrum 5V lines so RC2014 boards can be powered from the ZX Spectrum regulator (alternatively, this can be left open and 5V (for RC2014) only can be suplied via CN3/4)
* J2 – ROMCS, NMI and WAIT jumper – used connect key Spectrum signals to the user pins of RC2014 bus
* J3 - Inverted (Spectrum) or non-inverted (RC2014) CPU clock
* J4 – Polarity of 9V supply (CN5/6 can be used to replace Spectrum PSU)
  
