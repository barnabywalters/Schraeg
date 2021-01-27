# Schräg 2019 Edition (v0.1) Build Guide

If you’re reading this, odds are you’re one of the 10 people who got my spare boards from the first run of Schräg PCBs and panels. If that’s not the case, you probably want the build guide for the current edition (2021, v0.2 or later).

Refer to the interactive HTML BOM for part placement help (`./ibom.html`).

Refer to the [Bastl Cinnamon Assembly guide](https://bastl-instruments.com/content/files/cinnamon-1.2-assembly-guide.pdf) for calibration once assembly is complete. But please **don’t bother the good people at Bastl if you have problems with your Schräg**. Instead, ask the person you got your board from, online communities explicitly for DIY synth help, or [Barnaby](https://waterpigs.co.uk).

## BOM Changes

Use the BOM provided for the 2021 edition, with the following exceptions or caveats.

The three SPDT switches are the less common subminiature ones with 0.1" pin spacing, sold by Thonk and presumably also available elsewhere.

In the first run of boards I made the mistake of using SC-70 footprints for the two LM4040s, rather than the more common and easier to handle SOT-23 footprints. There are two ways to deal with this: either buy LM4040s in SC-70 packages, or solder the regular SOT-23 ones on backwards as shown:

![](/img/schraeg-2019-v0.2-d6-sot-23.jpeg)

![](/img/schraeg-2019-v0.2-d4-sot-23.jpeg)

In case it’s not clear: the SOT-23s are upside-down, and their two active pins soldered to the two outside pads on the outsides of the 3-padded side of the SC-70 footprint. Consult the LM4040 datasheet for more information.

## Front panel changes

The D-holes for the subminiature toggle switches are slightly undersize, and will likely require filing the flat side. Please wear breath protection while filing the PCB and panel!

The panel holes for the 3.5mm jacks are slightly oversize. If you’re picky about getting the jacks perfectly aligned, it will require some extra care when positioning and soldering them.

## Circuit changes

I forgot two 100k 0603 resistors in the 2019 edition, and you will need to cut some traces and install them yourself if you want the attenuverters for voltage control of resonance and FM to work properly.

Cut the following traces close to R11 and R19:

![](/img/schraeg-2019-v0.2-missing-resistor-locations.png)

Scrape a few millimetres of copper away completely, and then scrape pads clear for your choice of 100k SMD resistors.

![](/img/schraeg-2019-v0.2-missing-resistors-unpopulated.jpeg)

Populate the resistors, and use a multimeter to check that the traces have successfully been replaced with 100k resistances.

![](/img/schraeg-2019-v0.2-missing-resistors-populated.jpeg)

## Miscellaneous Changes

I got the footprints of the toggle switches the “wrong way round”, resulting in each function being active in the upper position rather than the lower position I had intended. This has been changed on later editions, but is not really a big problem.

## Troubleshooting and known problems

If you don’t install the missing 100k resistors correctly, the two attenuverters will behave strangely, working okay on in the positive direction but backwards in the negative direction.

Other known problems and their corresponding solutions will be added here as necessary.