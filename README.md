# Industrial IO Board for Raspberry Pi

Many industrial sensors, actuators, and indicator lights use 24V digital signals.
The [GPIO on the Raspberry PI 40-pin header](https://pinout.xyz/), are strictly 3.3V and not directly compatible with these devices.
This board adapts the GPIO on the Raspberry Pi to be able to interface with these signals.

Industrial 24V signals come in two main flavors: PNP and NPN.
PNP signals are on when connected to 24VDC and off when disconnected (left floating).
NPN signals are on when connected to 0V (GND) and off when disconnected.

Where I live and work PNP signals are overwhelmingly more popular.
They are also a bit more intuitive for most people.
So at present I am only providing a PNP version of the IO board.

This IO board is designed to mount to DIN rail.
DIN rail is the dominant electronics mounting system in industry.
It comes in several varieties, but the most common is DIN 3 also known as "top hat".
This system is primarily designed to work with DIN 3 rail.

The IO board does not attach to the Raspberry Pi like a typical HAT.
The It attaches to the Raspberry Pi at a right angle.
This is to minimize the length of DIN rail needed while providing good access to all of the Raspberry Pi's IO: ethernet, USB, HDMI, etc.

The designs for mounting hardware are provided as part of this design.
The mounting hardware aligns the 40-pin connectors of the Raspberry Pi and IO Board to each other while connecting both to the DIN rail.
It is possible to install a HAT (Hardware-Attached-on-Top) in between the Raspberry Pi and the IO Board.
The IO board makes extensive use of the GPIO on the Rasberry Pi.
If a HAT is used, it should not require any GPIO other than the `ID_*` pins (GPIO0 and GPIO1) or the I2C pins (GPIO2 and GPIO3).

The IO board itself is not considered a [HAT](https://github.com/raspberrypi/hats) or [HAT+](https://pip-assets.raspberrypi.com/categories/1215-raspberry-pi-hat/documents/RP-008281-DS-1-hat-plus-specification.pdf) because it does not conform the the mechanical requirements of those specifications.
However it does electrically function as a standard HAT+.


## Components

### PNP IO Board
The IO board will need to be fabricated and assembled.

#### Components
| Ref. | Qty. | Manufacturer    | Part Number | Description                                   | Notes                 |
| :--- | ---: | :-------------- | :---------- | :-------------------------------------------- | :-------------------- |


### 3D Printed Bases
The base for the IO board and the appropriate base for your Raspberry Pi will need to be fabricated.
See [3D-Printed-Parts](./3D-Printed-Parts).

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
You will also need a Raspberry Pi with a B+ or Zero form factor and everything to make it function.
See the official Raspberry Pi [getting started](https://www.raspberrypi.com/documentation/computers/getting-started.html) documentation for details.
The IO board does not power the Raspberry Pi, so an appropriate power supply for your Pi will be needed.

https://www.raspberrypi.com/documentation/computers/raspberry-pi.html

```
Industrial-IO-Board-for-Raspberry-Pi
|_ CHANGES.txt
|_ LICENSE.txt
|_ README.md
|_ cern_ohl_p_v2_howto.pdf
|_ PNP-IO-Board-Schematic.pdf
|
|_ extras
|_ gerbers
|_ stl_files
|
|_ src
   |_ Mounting_Hardware
   |  |_ .gitignore
   |  |_ PNP_IO_Board_Assembly.FCStd
   |  |_ Raspberry_Pi_3_B+_Assembly.FCStd
   |  |_ Raspberry_Pi_Zero_W_Assembly.FCStd
   |  |_ Base_for_IO_Board.FCStd
   |  |_ Base_for_Raspberry_Pi_Model_B.FCStd
   |  |_ Base_for_Raspberry_Pi_Zero.FCStd
   |  |_ Raspberry_Pi_3_B+.FCStd
   |  |_ Raspberry_Pi_Zero_W.FCStd
   |_ PNP-IO-Board
      |_ .gitignore
      |_ PNP-IO-Board.kicad_pcb
      |_ PNP-IO-Board.kicad_pro
      |_ PNP-IO-Board.kicad_sch
      |_ QR_Code.svg
      |_ fp-lib-table
      |_ sym_lib_table
      |_ Project_Symbols.kicad_sym
      |_ Project_3DModels.3dshapes
      |_ Project_Footprints.pretty

```
