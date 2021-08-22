# SHINSANWASWITCH PCB possible variants

Now there are corrently available three variants of PCB you can use:
- `standard` - two-layered-board with `NSI45020AT1G` LED-driver on the top, use it if you planning to order PCBs on JLCPCB or somewhere else (example of look [front](https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/6.webp) and [back](https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/7.webp))
- `LEDDriver_one-layer` - one-layered-board with `NSI45020AT1G` LED-driver, driver places on the bottom of the board, use it if you want to make PCB by yourself at home. (example of look [front](https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/8.webp) and [back](https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/9.webp))
- `Resistor_one-layer` - one-layered-board with resistor instead of LED-driver, if you do not want to use/do not have this LED-driver. You need to calculate resistor you need to use based on what input voltage will be used, consumption and voltage of the LED, but be sure that the total power dissipation across the resistor was not more than 1/4W, because board use 1/4W resistor. If you go beyond the power limits described above, you can try to install more powerfull resistor obliquely, but be sure that it will not interfere the installation of the board into the body or if you have problems with this I can recommend you to revise elements you use (use lower input voltage, use other LED or something like that to fit the limits, but if you use our recomendations - more likely you'll have problems with it). (example of look [front](https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/10.webp) and [back](https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/11.webp))

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

- PCB: 1x `shinsanwaswitch_PCB` **1mm thickness** (one of three possible variants, see [above](#shinsanwaswitch-pcb-possible-variants))
  - C1: Generic 0.1uF through hole ceramic capacitor.
  - C2: *not necessary, but recommended* 47uF 6.3v electrolitic capacitor on the power line input (read [some nuances of board assembly](#some-nuances-of-board-assembly) for more ditails)
  - J1: `S5B-PH-K-S` or equivalent.
  - LED: `S2B-PH-K-S` or equivalent.
  - PC1: `RPI-352`.
  - Q1: `2SC5395-F` or equivalent (may be rare but can be found on e.g. aliexpress).
  - R1: 330ohm 5% 1/4W through hole.
  - R2: 22kohm 5% 1/4W through hole.
  - R3: 10kohm 5% 1/4W through hole.
  - STI1: `NSI45020AT1G` (for `standard` and `LEDDriver_one-layer` board versions) or R4: 470ohm 5% 1/4W through hole (for `Resistor_one-layer` board and 12v power-up 20mA LED, in other case use calculation to know what resistor you need to use)
- 1x harness
  - 5x Single-ended **JST PH** wires (can be found on e.g. aliexpress or alternatively you can crimp them yourself, I recommend you to found on aliexpress for it 5 pin 22 AWG white-blue-red-green-black cable, it amazingly fits connector, feels very reliable and also fits into the understandable color scheme)
  - 1x JST `PHR-5` or equivalent.
- 1x LED assembly (no resistors required)
  - 2x **JST PH** to **.1" (BLS-02/Dupont 2pin) female** wires (can be found on e.g. aliexpress or alternatively you can crimp them yourself. I recommend to use wires flexible as possible, that will be very useful. Wires length - somewhere around ~150-160mm, need be shorter as possible, because long wires will be nowhere to fold. Can be made by soldering single-ended JST PH wire and .1" (BLS-02/Dupont 2pin) female wire together and wrapping each wire with heat shrink tubing).
  - 1x 20mA through hole white LED (plugs into the .1" (BLS-02/Dupont 2pin) female connector).
  - 1x JST `PHR-2` or equivalent.
  - 1x 2 pin .1" (BLS-02/Dupont 2pin) female connector housing.
  
# Pin mapping

<img src="https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/board.webp" align="right" alt="board" width=60% height=60% />


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

# Some nuances of board assembly

- I recommend to start assembly of the board from soldering STI1 (or R4), because of you'll try to do it later, especially after soldering LED and J1 connectors - it will be quite difficult because of small space available.
<img src="https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/1.webp" alt="board" width=30% height=30% />

- I also recommend to cut leads pins of THT-type components to make it shorter as possible before soldering. In body of SHINSANWASWITCH there are available some space to fit the leads pins from the board (according to the drawing - 1.4mm from the board to the bottom of body, but in reality that space can be +/-0.1mm smaller/bigger because of possible nuances of 3D-printing and final installation of board inside the body), so make sure that output leads pins from the PCB does not protrude above ~1mm from the board to eliminate possible problems with installing the board because of that.

<img src="https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/2.webp" alt="board" width=30% height=30% /> <img src="https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/3.webp" alt="board" width=30% height=30% /> 

- It's not necessary, but recommended to use 47uF 6.3v electrolitic capacitor on the power line input. There is no separated place on board for it's installing, so SMD-type capacitor can be soldered directly to S5B-PH-K-S +5v and GND pins (look [image](https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/4.webp)). If you use THT-type electrolitic capacitor - you can put leads pins of capacitor directly to +5v and GND pins holes on the board with JST connector, it's possible because for this holes of +5v and GND were enlarged to fit two leads pins in one hole. Make sure that leads pins of capacitor do not contacts other nearby leads pins, for reliability, leads pins of capasitor better to isolate with heat shrinkage before soldering (look [image](https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/5.webp)).

<img src="https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/4.webp" alt="board" width=30% height=30% />  <img src="https://raw.githubusercontent.com/steelpuxnastik/SHINSANWASWITCH/version1.1/source/assimages/5.webp" alt="board" width=30% height=30% /> 