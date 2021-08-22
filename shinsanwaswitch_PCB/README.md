# SHINSANWASWITCH PCB possible variants

Now there are corrently available three variants of PCB you can use:
- `standard` - two-layered-board with `NSI45020AT1G` LED-driver on the top, use it if you planning to order PCBs on JLCPCB or somewhere else.
- `LEDDriver_one-layer` - one-layered-board with `NSI45020AT1G` LED-driver, driver places on the bottom of the board, use it if you want to make PCB by yourself at home.
- `Resistor_one-layer` - one-layered-board with resistor instead of LED-driver, if you do not want to use/do not have this LED-driver. You need to calculate resistor you need to use based on what input voltage will be used, consumption and voltage of the LED, but be sure that the total power dissipation across the resistor was not more than 1/4W, because board use 1/4W resistor. If you go beyond the power limits described above, you can try to install more powerfull resistor obliquely, but be sure that it will not interfere the installation of the board into the body or if you have problems with this I can recommend you to revise elements you use (use lower input voltage, use other LED or something like that to fit the limits, but if you use our recomendations - more likely you'll have problems with it).

# How to open PCB project files?
PCB source files created using KiCad 5.99+ (5.99.0-11737-gca42f31bb5), release build, so you need to use this version of KiCad or newer to open project files. If you use older version - program will not open it.
If you have suitable version, open the main windows of KiCad and click menu "File > Open Project..." or use  Ctrl + O keyboard buttons. In opened window go to ~/shinsanwaswitch_PCB folder and you will see three project files, that are called same as described above:
- `shinsanwaswitch_v1.1-standard.kicad_pro`
- `shinsanwaswitch_v1.1-LEDDriver_one-layer.kicad_pro`
- `shinsanwaswitch_v1.1-Resistor_one-layer.kicad_pro`

So you need to choose what you need project file and then same to open same-named satellite files with PCB or schematic.

# PCB thickness
SHISANWASWITCH body allows to install **only 1mm thickness PCB**. So be sure when you order PCB or if you will make it by yourself, that textolite thickness was 1mm.

# Parts needed

- PCB: 1x `shinsanwaswitch_PCB` **1mm thickness** (one of three possible variants, see above)
  - C1: Generic 0.1uF through hole ceramic capacitor.
  - C2: *not necessary, but recommended* 47uF 6.3v electrolitic capacitor on the power line input (there is no separated place on board for it's installing, so can be soldered directly to `S5B-PH-K-S` +5v and GND pins holes, especially for this holes were enlarged to fit two wires. Make sure that wires of capacitor do not contacts other pins, for reliability, wires of capasitor better to isolate with heat shrinkage)
  - J1: `S5B-PH-K-S` or equivalent.
  - LED: `S2B-PH-K-S` or equivalent.
  - PC1: `RPI-352`.
  - Q1: `2SC5395-F` or equivalent (may be rare but can be found on e.g. aliexpress).
  - R1: 330ohm 5% 1/4W through hole.
  - R2: 22kohm 5% 1/4W through hole.
  - R3: 10kohm 5% 1/4W through hole.
  - STI1: `NSI45020AT1G` (for standard and one-layered-board with LED driver board versions) or R4: 470ohm 5% 1/4W through hole (for one-layered-board with resistor and 12v power-up 20mA LED, in other case use calculation to know what resistor you need to use)
- 1x harness
  - 5x Single-ended **JST PH** wires (can be found on e.g. aliexpress or alternatively you can crimp them yourself, I recommend you to found on aliexpress for it 5pin 22 AWG white-blue-red-green-black cable, it amazingly fits connector, feels very reliable and also fits into the understandable color scheme)
  - 1x JST `PHR-5` or equivalent.
- 1x LED assembly (no resistors required)
  - 2x **JST PH** to **.1" (BLS-02/Dupont 2pin) female** wires (can be found on e.g. aliexpress or alternatively you can crimp them yourself. I recommend to use wires flexible as possible, that will be very useful. Wires length - somewhere around ~150-160mm, need be shorter as possible, because long wires will be nowhere to fold. Can be made by soldering single-ended JST PH wire and .1" (BLS-02/Dupont 2pin) female wire together and wrapping each wire with heat shrink tubing).
  - 1x 20mA through hole white LED (plugs into the .1" (BLS-02/Dupont 2pin) female connector).
  - 1x JST `PHR-2` or equivalent.
  - 1x 2 pin .1" (BLS-02/Dupont 2pin) female connector housing.
  
# Pin mapping

<img src="https://github.com/steelpuxnastik/SHINSANWASWITCH/source/board.webp" align="right" alt="board" width="40%" height="40%" />

I/O port (from up to down):

| \#  | Description |
| --- | ----------- |
|  1  | LED+ |
|  2  | LED- |
|  3  | +5V |
|  4  | OUT |
|  5  | GND |

LED connector (from up to down):

| \#  | Description |
| --- | ----------- |
|  1  | + |
|  2  | - |

# Assembly of board

To be done later.