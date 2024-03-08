# Logitech G305 FIBM (Fully Integrated Battery Mod)

![G305_lipo_PMIC.png](/Resources/PNG/Scope_of_modification.png)

## What is this?
![G305_lipo_PMIC.png](/Resources/PNG/G305_lipo_PMIC_F_2a.png)
  This is another battery mod for the Logitech G305. This modification is nondestructive and fully reversable.  The AA battery and holder are replaced with a lithium polymer
cell and power management PCB.  Charging is done by removing the top cover and sticking a mag-safe style connector, an LED indicates charge cycle. With a 230 mAh cell,the mouse has a projected run time of ~30 hours of continuous use between charges. Charging takes approximately 
1 hour.  This mod also retains the DPI button and indicator so that functionality is not lost.  

## Why is this?
  Previously there was a product on the market which did something similar, however the website no longer online.  As a result, I have made my own version of a G305
lithium-ion battery modification.  This board contains a lithium-ion charger which allows the battery to be recharged from any common USB supply.  It also crucially contains 
a DCDC step down converter which creates the proper 1.5V DC that Logitech G305 expects.  There are two DCDC step up converters in the Logitech G305, without knowing the 
exact parts used it is impossible to tell whether they are rated for operation when Vin ≈ Vout or Vin > Vout.  This is not a normal operating condition for most DCDC step up converters.
Anecdotally there are users who claim long term (1 year) use of a lithium-ion battery without a 1.5 volt regulator to no ill effect however, as the saying goes better safe than sorry.

## Implementation
![G305_lipo_PMIC.png](/Resources/PNG/g305_FBIM_mockup_point.png)
  The board is built around the TPS6224 from Texas Instruments, a DCDC step down converter which is optimized for light load applications.  This converter sports a theoretical ~90% efficiency with nominal current draw of the Logitech G305.  Real world testing will need to be carried out to verify this figure.

  This mod requires no drilling or gluing of any logitech components. The magnetic connector is integral to the replacement DPI button which screws into two existing hardpoints for the OEM AA battery holder.  
  
  As printed the DPI button is a flat which is bent into the final shape after printing.  The 
replacement DPI button and DPI light guide are two seperate pieces. The DPI button color can be customized to color match the mouse while the light guide is printed in clear PETG. The light guide was optimized in acordance with "3D Printing of Transparent Materials for Optical Applications" by Shaunak B. Gandhi of RIT.

## Notes
  Schematics, PCB, BOM and, GBR files are all attached.  The BOM assumes a 230 mAh battery will be used, if not R1 might have to be changed.  R1 controls the battery charging 
current which is dictated by the cells overall capacity and the max charge rate usually denoted in C (i.e. 1 C charge rate). The Microchip MCP73832 datasheet contains more information 
for those interested. 

For the equivalent battery capacity of a AA battery a lithium-ion battery of at least 1000 mAh is required.  If you choose to use another lithium-ion cell, ensure that it has a BMS circuit built in.

  This project is released under CERN-OHL-P-2.0 license, there is 0 secret sauce stuff happening here.

## Example
![Build_001_rev2a.png](/Resources/PNG/Build_001_rev2a.png)
(Mouse charging image also in Resources/PNG/)
-Built as specified the mouse weight has reduced from 100 -> 76 grams. (not 1:1 as MB1 / MB2 switches were also replaced & aluminum scroll wheel change)
-Ender 3 could not handle printing a 2mm rod, substitued with polystyrene rod. In practice any 2 mm diameter rod will work.



## Wishlist 🔮
- Lithium-ion battery low voltage indicator.
  -Revision 3 will contain circuitry to reduce voltage to the mouse tripping the G305 OEM battery alarm.

## Thanks to, 
Redditors:<br>
u/zwiebi for characterizing the Logitech G305’s power draw.<br>
u/Forty_0ne for the bottom and top cover 3d scans of the Logitech G305.<br>
<br>
Filip of 0x46.net for the high resolution disassembly photos of the G305.<br>
MatNS and, inornate on Thingiverse.<br>
Matt Gaidica of Gaidi.ca for modelling lithium-ion pouch cell weights and capacity.<br>
Digikey for constantly thinking I am a robot, I wish.😖<br>

![G305_lipo_PMIC_B.png](/Resources/PNG/G305_lipo_PMIC_B_2a.png)
