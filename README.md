# Logitech G305 FIBM (Fully Integrated Battery Mod)

![G305_lipo_PMIC.png](/Resources/G305_lipo_PMIC.png)

## What is this?
  This is another battery mod for the Logitech G305. This modification is nondestructive and fully reversable.  The AA battery and holder are replaced with a lithium polymer
cell and power management PCB.  Charging is done by removing the top cover and sticking a mag-safe style connector, an LED indicates the battery is charging 
extinguishing when charging has completed. With a 230 mAh cell,the mouse has a projected run time of ~30 hours between charges. Charging takes approximately 
1 hour.  This mod also retains the DPI button and indicator so that functionality is not lost.  

## Why is this?
  Previously there was a product on the market which did something similar, however the website no longer online.  As a result, I have made my own version of a G305
lithium-ion battery modification.  This board contains a lithium-ion charger which allows the battery to be recharged from any common USB supply.  It also crucially contains 
a DCDC step down converter which creates the proper 1.2V DC that Logitech G305 expects.  There are two DCDC step up converters in the Logitech G305, without knowing the 
exact parts used it is impossible to tell whether they are rated for operation when Vin ≈ Vout or Vin > Vout.  This is not a normal operating condition for most DCDC step up converters.
Anecdotally there are users who claim long term (1 year) use of a lithium-ion battery without a 1.2 volt regulator to no ill effect however, as the saying goes better safe than sorry.

## Implementation
  The board is built around the TPS6224 from Texas Instruments, a DCDC step down converter which is optimized for light load applications like the Logitech G305.  This converter sports a theoretical ~90% efficiency with nominal current draw of the Logitech G305.  Real world testing will need to be carried out to verify this figure.

  This mod requires no drilling or gluing of any logitech components. The magnetic connector is integral to the replacement DPI button which screws into two existing hardpoints for the OEM AA battery holder.  The 
replacement DPI button / battery  holder is 3D printed from clear PETG, as a result the part acts as a light guide for the DPI indicator.  Bicolor 3d printing would be ideal for this part for better color matching & less light bleed.

## Notes
  Schematics, PCB, BOM and, GBR files are all attached.  The BOM assumes a 230 mAh battery will be used, if not R1 might have to be changed.  R1 controls the battery charging 
current which is dictated by the cells overall capacity and the max charge rate usually denoted in C (i.e. 1 C charge rate). The Microchip MCP73832 datasheet contains more information 
for those interested. 

For the equivalent battery capacity of a AA battery a lithium-ion battery of at least 1000 mAh is required.  If you choose to use another lithim-ion cell, ensure that it has a BMS circuit built in.

  This project is released under MIT license, there is 0 secret sauce stuff happening here.

  ## Thanks
Thanks to,<br>
Redditors:<br>
u/zwiebi for characterizing the Logitech G305’s power draw.<br>
u/Forty_0ne for the bottom and top cover 3d scans of the Logitech G305.<br>
Filip of 0x46.net for the high resolution disassembly photos of the G305.<br>
MatNS and, inornate on Thingiverse.<br>
Digikey for constantly thinking I am a robot, I wish.😖<br>

![G305_lipo_PMIC_B.png](/Resources/G305_lipo_PMIC_B.png)
