# Schräg

Schräg is an 8HP multimode filter module for the eurorack format, based off the [Bastl Cinnamon](https://bastl-instruments.com/eurorack/modules/cinnamon).

<img src="img/Schraeg-finished.jpeg" alt="" width="200" />

## Smaller Warning and Disclaimer

As of 2021-03-01, at least one person has reported successfully building the current board revision. However, another builder reported a minor issue with the attenuverter circuits which prevents full-range voltage control over resonance (and limits voltage control over FM). This should be fixable only with component substitutions, we’re working on a fix. More information and updates [in the corresponding lines thread](https://llllllll.co/t/diy-module-release-schrag-bastl-cinnamon-rework/40590).

See the Changelog below for more updates and version-specific fixes.

## Quick links

* [Schematic](Schraeg/Schraeg.pdf)
* [Gerbers](Schraeg/output)
* [BOM](Schraeg/Schraeg%20BOM.csv)
* [Schräg on ModularGrid](https://www.modulargrid.net/e/other-unknown-schraeg)

## Features

Schräg is effectively a repackaged Bastl Cinnamon:

* Multimode filter with independent outputs (2-pole LP, 2-pole HP, 1-pole BP)
* V/oct input
* Self-resonates for use as a sine oscillator
* Input with an attenuator and 5x gain switch
* Two character switches for altering the resonance tracking
* All-SMD construction in a DIY-friendly format, with 0603 handsoldering footprints, all components on the back of the circuit board
* Built mostly using standard and easily-available components

with a few modifications:

* larger 8HP form factor, allowing for a big juicy cutoff knob and larger character and gain switches
* Voltage control over resonance, through an attenuverter
* FM input through an attenuverter, which works as a pitch fine-tune control with nothing patched
* A bi-directional power connector, with polyfuses
* An Interactive BOM (`Schraeg/Output/Interactive BOM.html` once you’ve cloned the repo locally) to aid in part placement
* Schematics and PCB laid out using KiCAD

The additional functionality is achieved with a minimum of extra components, thanks to the two unused VCA cells in the original design.

## License

The schematic, board layout and graphics are released under a cc-by-sa license. [Bastl Instruments](https://bastl-instruments.com/) generously gave their permission for me to release my rework of their module. They’re a cool company. Go check out their work!

## Development

In 2019 I was looking through the [Bastl Cinnamon schematic](https://github.com/bastl-instruments/bastlSchematics/blob/master/CINNAMON_V1.2.pdf) and realised that it only uses two of the four available V2164D VCA cells.

At the time I needed PCB layout practise (and a filter module for my DIY eurorack!), so I ended up prototyping and building an 8HP version of cinnamon for myself which uses the two spare cells to implement voltage control over resonance, as well as a few other little additions listed above.

I called it “Schräg” because of both the angled panel design, the weird sounds possible with Bastl’s cool distortion circuits, and the strange way KiCAD mangled the panel graphics.

A bit more than a year after building the first Schräg, I finally got around to fixing the various small issues with the first board revision, and asking Bastl if they were okay with me open-sourcing the project. They were, and here we are.

## Changelog

### v0.2.1

* Fixed the LM4040 schematic symbols and PCB traces (#2)

### v0.2

* First version released to the public.
* These boards have an issue with the LM4040 orientation (see #2). Depending on the specific LM4040s, it may not cause any problems, but if building from scratch it’s best to install them correctly the first time. To fix it, solder the LM4040s at an angle so that pin 2 (NC) gets connected to pin 3 (5V Ref or GND, depending on the LM4040)