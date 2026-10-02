# Industrial PNP IO HAT+ for Raspberry Pi

Many industrial sensors, actuators, and indicator lights use 24V digital signals.
The [GPIO on the Raspberry PI 40-pin header](https://pinout.xyz/), are strictly 3.3V and not directly compatible with these devices.
This board adapts the GPIO on the Raspberry Pi to be able to interface with these signals.

Industrial 24V signals come in two main flavors: PNP and NPN.
PNP signals are on when connected to 24VDC and off when disconnected (left floating).
NPN signals are on when connected to 0V (GND) and off when disconnected.

Where I live and work PNP signals are overwhelmingly more popular.
They are also a bit more intuitive for most people.
The digital inputs and outputs on this board are for PNP signals.

This IO board is designed to mount to DIN rail.
DIN rail is the dominant electronics mounting system in industry.
It comes in several varieties, but the most common is DIN 3 also known as "top hat".
This system is primarily designed to work with DIN 3 rail.

This board conforms to the [Raspberry Pi HAT+ specification](https://pip-assets.raspberrypi.com/categories/1215-raspberry-pi-hat/documents/RP-008281-DS-1-hat-plus-specification.pdf)


## Components

### PNP IO Board
The IO board will need to be fabricated and assembled.

#### Components
| Ref. | Qty. | Manufacturer    | Part Number | Description                                   | Notes                 |
| :--- | ---: | :-------------- | :---------- | :-------------------------------------------- | :-------------------- |

### Purchased Components
| Qty. | Manufacturer    | Part Number | Description                                   | Notes                 |
| ---: | :-------------- | :---------- | :-------------------------------------------- | :-------------------- |
|    4 | Phoenix Contact | 1202713     | DIN Rail Adapter                              |                       |
|    8 | McMaster-Carr   | 90485A477   | M5 x 12mm Lg. Thread-Forming Flat Head Screw  | Comes in packs of 50  |
|   12 | McMaster-Carr   | 90380A338   | M2.5 x 6mm Lg. Thread-Forming Flat Head Screw | Comes in packs of 100 |
|    1 | McMaster-Carr   | 8961K105    | DIN Rail                                      |                       |
|    2 | McMaster-Carr   | 5575N22     | DIN Rail Stop                                 | Comes in packs of 10  |

### 24VDC Power Supply
While not considered to be a part of this design, a 24V power supply will be needed to power the IO board.
It should be able to output at least 3A.
The IO board has a built in fuse on its power input so an external fuse or circuit breaker is not needed.

### Raspberry Pi
You will also need a Raspberry Pi and SD card with an operating system (OS) loaded on it to make it function.
See the official Raspberry Pi [getting started](https://www.raspberrypi.com/documentation/computers/getting-started.html) documentation for details.
The IO board does power the Raspberry Pi, so not additional power supply is needed.


## Design Notes
This section should be removed before the repository is made public.

https://www.raspberrypi.com/documentation/computers/raspberry-pi.html

```
Industrial-PNP-IO-HAT
|_ CHANGES.txt
|_ LICENSE.txt
|_ README.md
|_ cern_ohl_p_v2_howto.pdf
|_ Schematic.pdf
|
|_ extras
|_ fabrication_files
|
|_ src
   |_ .gitignore
   |_ Industrial-PNP-IO-HAT.kicad_pcb
   |_ Industrial-PNP-IO-HAT.kicad_pro
   |_ Industrial-PNP-IO-HAT.kicad_sch
   |_ QR_Code.svg
   |_ fp-lib-table
   |_ sym_lib_table
   |_ Project_Symbols.kicad_sym
   |_ Project_3DModels.3dshapes
   |_ Project_Footprints.pretty

```
