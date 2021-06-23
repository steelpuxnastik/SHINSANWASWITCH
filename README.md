# SHINSANWASWITCH

Photointerrupter microswitch/lamp holder 2-in-1 (similar to OBSA-LHSXF) for generic 100mm Chinese arcade buttons.

## Parts list

### Electrical

- PCB: 1x `shinsanwaswitch_PCB` (KiCad 5.99+ required for exporting Gerber files)
  - C1: Generic 0.1uF through hole ceramic capacitor.
  - D1: `NSI45020AT1G`.
  - J1: `S5B-PH-K-S` or equivalent.
  - LED: `S2B-PH-K-S` or equivalent.
  - PC1: `RPI-352`.
  - Q1: `2SC5395-F` or equivalent (may be rare but can be found on e.g. aliexpress).
  - R1: 330ohm 5% 1/4W.
  - R2: 22kohm 5% 1/4W.
  - R3: 10kohm 5% 1/4W.
- 1x harness
  - 5x Single-ended **JST PH** wires (can be found on e.g. aliexpress or alternatively you can crimp them yourself)
  - 1x JST `PHR-5` or equivalent.
- 1x LED assembly (no resistors required)
  - 2x **JST PH** to **.1" female** wires (can be found on e.g. aliexpress or alternatively you can crimp them yourself. Can be made by soldering single-ended JST PH wire and .1" female wire together and wrapping each wire with heat shrink tubing).
  - 1x 20ma white LED (plugs into the .1" female connector).
  - 1x JST `PHR-2` or equivalent.
  - 1x 2 pin .1" female connector housing.

### Mechanical

- 3D printable parts (printing in resin recommended for best accuracy but not required)
  - 1x `STL/body.STL`
  - 1x `STL/cap.STL`
  - 1x `STL/lever.STL`
- 1x 0.3x6x10mm (wire thickness x outer diameter x length) spring (can be found on e.g. aliexpress).
- 2x M?x? screws <!-- TODO confirm the type with steelpuxnastik -->
