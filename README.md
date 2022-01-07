# Twomes CO₂ Monitor Shield hardware 

This repository contains the open hardware design files for the Twomes CO₂ Monitor Shield, which can measure CO₂ concentration, relative humidity and temperature.
It has the form factor of a [WeMos D1 Mini shield](https://www.wemos.cc/en/latest/d1_mini_shield/index.html). This allows it to be used in many ways, e.g.:
* on top of [Twomes Temperature Monitor Hardware](https://github.com/energietransitie/twomes-temp-monitor-hardware);
* on top of a [LilyGO TTGO T7 Mini32 V1.3 ESP32](https://github.com/LilyGO/ESP32-MINI-32-V1.3). 

<img src="./images/front.jpg" width="400" height="400" /> <img src="./images/back.jpg" width="400" height="400" />

## Table of contents
* [General info](#general-info)
* [Producing](#producing)
* [Developing](#developing) 
* [Features](#features)
* [Status](#status)
* [License](#license)
* [Credits](#credits)

## General info
This repository contains the open hardware designs files for the Twomes CO₂ Monitor Shield, It also includes a `docs` folder with recent printouts of the [schematics](./docs/twomes-co2-monitor-hardware-sch.pdf) and [PCB layout](./docs/docs/twomes-co2-monitor-hardware-pcb.pdf). 

The associated firmware you should use depends on the context:
* if you use the shield on top of [Twomes Temperature Monitor Hardware](https://github.com/energietransitie/twomes-temp-monitor-hardware), use the [Twomes Room Monitor firmware](https://github.com/energietransitie/twomes-room-monitor-firmware);
* if you use the shield on top of a [LilyGO TTGO T7 Mini32 V1.3 ESP32](https://github.com/LilyGO/ESP32-MINI-32-V1.3), use the [Twomes CO₂ Monitor firmware](https://github.com/energietransitie/twomes-co2-monitor-firmware).

## Producing


### Printed Circuit Board
To fabricate the printed circuit board you can use various PCB services. 

The folder [pcb/jlcpcb](./pcb/jlcpcb) includes all exported files needed to have the PCBs manufactured by [JLCPCB](https://www.jlcpcb.com). Upload the [zipped gerber files](./pcb/jlcpcb/gerber/gerber-OpenThermMonitorTwomes.zip) to the [JLCPCB quote page](https://cart.jlcpcb.com/quote), select the amount of PCBs and a colour for the silkscreen. All other options can be left on default. 

In the current version of this design, no SMT assembly is used. Hence, we do not provide BOM*.csv and CPL-*.csv files in the folder [pcb/jlcpcb/assembly](./pcb/jlcpcb/assembly)

### Enclosure
We do not yet have a design for an enclosure that fits a Twomes CO₂ Monitor Shield on top of a [LilyGO TTGO T7 Mini32 V1.3 ESP32](https://github.com/LilyGO/ESP32-MINI-32-V1.3) and LiPo battery. Hence we do not yet provide enclosure design files that allow you to fabricate an enclosure you can use your own 3D printer or use a 3D printing service.
## Developing
### Printed Circuit Board
To change the hardware design of the PCB, you need:
* [KiCad](https://www.kicad.org/download/) installed to change te PCB design. 

The KiCad source files of the PCB can be found in the folder [pcb](./pcb).

To convert the PCBs into a format suitable for fabrication, consult the webpage of your PCB manufacturer of choice. For example, see the [JLCPCB guide on how to export Gerbers](https://support.jlcpcb.com/article/149-how-to-generate-gerber-and-drill-files-in-kicad) and the  [JLCPCB guide how to export the BOM and POS files](https://support.jlcpcb.com/article/84-how-to-generate-the-bom-and-centroid-file-from-kicad). You may also use a KiCad plug-in for this purpose such as [kicad-jlcpcb-tools](https://github.com/Bouni/kicad-jlcpcb-tools).

### Enclosure
To add a hardware design for an enclosure, we recomend either either:
* [Autodesk Fusion 360](https://www.kicad.org/download/) installed (Autodesk provides 30 day free trials and [free one-year educational access](https://www.autodesk.com/education/edu-software/overview?sorting=featured&filters=individual) to its products and services for eligible students, teachers and research staff); 
* or [FreeCAD](https://www.freecadweb.org/), an open source alternative.

Put the source files of the enclosure in the folder [enclosure](./enclosure). Please always include a include a common 3D source file format editable with open source 3D design tools, such as [FreeCAD](https://www.freecadweb.org/).
## Features
The Twomes CO₂ Monitor Shield features the follwoing main hardware components:
* Sensirion [SCD41](https://www.sensirion.com/en/environmental-sensors/carbon-dioxide-sensors/carbon-dioxide-sensor-scd4x/) sensor, which can measure CO₂ concentration, relative humidity and temperature;
* [Si7051](https://www.silabs.com/sensors/temperature/si705x/device.si7051) temperature sensor. 

To-do:
* add tips for type of solder and temperature to use for realiably assembly of the Sensirion [SCD41](https://www.sensirion.com/en/environmental-sensors/carbon-dioxide-sensors/carbon-dioxide-sensor-scd4x/) sensor on the PCB;
* add female connector for the [SEK-SCD41](https://www.sensirion.com/en/environmental-sensors/evaluation-kit-sek-environmental-sensing/evaluation-kit-sek-scd41/) evaluation kit;
* add SMT assembly files for JLCPCB;
* add/re-use a recessed button that is positioned behind a pinhole in the device enclosure, which allows the end-user to do a Wi-Fi reset;
* change design and JLCPCB files to take advantage of the new [one-sided hand-soldering option for through-hole parts](https://jlcpcb.com/smt-assembly) for the pin headers `P1` and `P2`;
* add an enclosure design that fits a Twomes CO₂ Monitor Shield on top of a [LilyGO TTGO T7 Mini32 V1.3 ESP32](https://github.com/LilyGO/ESP32-MINI-32-V1.3) and LiPo battery. A reasonable starting point would be the [Twomes OpenTherm Monitor enclusure design](https://github.com/energietransitie/twomes-opentherm-monitor-hardware/enclosure).

## Status
Project is: _in progress_

## License
The hardware designs in this repository are available under the [CERN-OHL-P v2 license](./LICENSE), Copyright 2022 [Research group Energy Transition, Windesheim University of Applied Sciences](https://windesheim.nl/energietransitie)

## Credits
This open hardware design is a collaborative effort of:
* Sjors Smit · [@Shorts1999](https://github.com/Shorts1999)
* Marco Winkelman · [@MarcoW71](https://github.com/MarcoW71)

Thanks also go to:
* Henri ter Hofte · [@henriterhofte](https://github.com/henriterhofte) · Twitter [@HeNRGi](https://twitter.com/HeNRGi)

We use and gratefully acknowlegde the efforts of the makers of the following designs:
* [KiCad Libraries](https://kicad.github.io/), by the KiCad Development Team, licensed under [an adapted version of the CC-BY-SA 4.0 License](https://www.kicad.org/libraries/license/)
