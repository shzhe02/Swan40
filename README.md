# Swan40 - A 40-key split keyboard.

My first attempt at designing a custom sleek split keyboard.

More extensive write-up (in progress): https://shzhe02.com/projects/swan40

Features:
- Uses the XIAO nRF528420 microcontroller
- Up to 1000 mAh lipo battery without tenting (with 102050 lipo)
- Dual-orientation lipo mounting
- On-off switch hard wired to battery
- Should be compatible with Choc v1 and v2 switches (only v1 tested)
- Hotswap switches
- Plate-mounted switches

BOM:
- 2x XIAO nRF52840 (compatible with both non-sense or sense versions)
- 2x MSK-12C02 switches
- 40x Kailh Low-profile hotswap sockets
- 40x 1N4148W T4 SOD123 diodes
- Some jumper wires (for connecting the battery pads on the PCB to the battery pads on the microcontroller)
- Electrical tape (place over battery-connected pads on PCB after soldering to reduce chances of a short-circuit occuring)
- 40x Kailh Choc v1/v2 switches
- 40x MBK keycaps (or compatible keycaps of your choice)
- (Optional) 2x MBK homing keycaps (In this case, only 38 normal keycaps are needed)

Case BOM:
- 3x M2 (OD 3.2mm) x 4mm brass inserts
- 3x M2 x 5mm screws (preferrably button head torx (or hex))
- 2x M2 x 10mm screws

Wiring notes:
- Positive and negative battery terminals should be soldered to the BAT+ and BAT- pads on the PCB respectively.
- The BOARD+ and BOARD- pads on the PCB should be soldered to jumper wires connecting them to the BAT+ and BAT- pads on the microcontroller respectively.
- I recommend first connecting the microcontroller to the PCB and using a multimeter to ensure that the switch works and there are no shorts between the BAT+ and BAT- pads of the PCB before connecting the battery.
- When soldering the battery to the PCB, I recommend doing the following:
  - Tape off the end of one of the battery wires with some sort of insulating tape (I used masking tape).
  - Route the taped wire through the battery wire hole on the PCB (check the write up for more details) followed by the other wire.
  - Solder the non-taped wire to its corresponding battery pad on the PCB.
  - After the pad has cooled down, place some insulating tape over the entire pad but leave the other pad exposed.
  - Un-tape the taped wire and solder it to the other battery pad on the PCB.
  - Remove the tape on the other pad, and cover both pads with electrical tape.

Potential future improvements:
- [ ] Make main PCB reversible
- [ ] Change lipo connection SMD pads to an SMD micro JST 1.25 connector
- [ ] Figure out a safer (more foolproof) method to connect battery pads of the controller to the PCB.
- [ ] Design a smaller battery cover for the 500 mAh 602035 lipo

Credits:
- [foostan's kbd KiCad Library/Symbols/3D Models](https://github.com/foostan/kbd/tree/crkbd4)
    - Located in the directory: pcb/assets/kbd, plate/assets/kbd, left-plate/assets/kbd, and right-plate/assets/kbd
- [Seeed Studio XIAO nRF52840 STEP model - by Maurice Pannard](https://grabcad.com/library/seeed-studio-xiao-nrf52840-sense-1)
    - Located in the directory: pcb/assets/xiao_nrf52840
- [Kailh 1350 Socket (Choc V1 Hotswap sockets) STEP model - by Dennis Lee](https://grabcad.com/library/kailh-1350-socket-2)
    - Located in the directory: pcb/assets/kailh_choc_v1_hotswap
- [MBK Choc Low Profile 1u keycap STEP model - by darryldh](https://www.thingiverse.com/thing:4564253)
    - Located in the directory: pcb/assets/kailh_choc_v1_hotswap
- [MSK-12C02 SMD Slider Switch Footprint - by mzst](https://mzstblog.blogspot.com/2016/01/msk-12c02-smd-slider-switch-spdt-eagle.html)
    - Located in the directory: pcb/assets/MSK-12C02

Note: Modifications were made to many of the assets.