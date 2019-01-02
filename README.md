# Prusa i3 Mk3 Resources
Resources for Prusa i3 Mk3 Printer. The following information are things that I have learned from my 3D printing journey with the Prusa Mk3. I don't claim that everything here is 100% factual, and if you think I am providing any incorrect information, please let me know by posting on my Github Issues list! :)

##### Table of Contents  
[Headers](#headers)  
[Emphasis](#emphasis)  
...snip...    
<a name="headers"/>
## Headers

# First Layer Adhesion Issues And How To Fix Them
Before trying the steps below, make sure you have calibrated your live Z correctly. Ignore the Prusa video where Josef says it should be a value of around -1.200. Your value will depend on how far up your PINDA is mounted and how thick your bed plate is. Your live Z value is adjusted properly when the lines of plastic that are laid down do not have any gaps in between them. If you think your live Z is adjusted properly, you may begin the following steps: 
1) Clean your bed plate with [99.9% Isopropyl alcohol](https://www.amazon.com/dp/B005DNQX3C/ref=cm_sw_r_cp_apap_2tu8Mct2ObEU7) and UNSCENTED paper towels. Do not use anything less than 99.9% and do not rub it in a circular motion, rather, rub it from side to side. Your bed plate has oils on it (from the manufacturing process, and from whenever you touch it with your oily hands) and your goal is getting the oil off, not spreading it around. It's very important to also use unscented paper towels with no coloring designs as these may have oils in them.  
2) If the isopropyl alcohol fails to help, use unscented dish soap and hot water to clean your bed plate in the sink. Scrub it well, and dry with unscented paper towels. Be sure to not touch the clean bed plate with your hands once washed (grip the edges only). Soap breaks down grease and oils even better than Isopropyl alcohol, but is obviously a more annoying process. If you don't touch your bed plate too much, you should be fine with washing your plate in the sink once per month, and rubbing it with isopropyl alcohol once a day before your first print of the day. 
3) If you are still having issues, try printing your first layer hotter. Hotter plastic is more "liquidy" and will spread on the bed easier, as well as stick better. I personally use 220c for PLA and 265c for PETG first layers. 
4) Make sure fan is disabled for first layer in slic3r. You might even want to disable it for the first 2 or 3 layers for  smaller prints, as your plastic being laid down might be cooling too quickly for it to stick. 
5) Try a warmer bed temperature. I personally find that my bed is actually 5c colder than the printer reports after measuring it with an IR thermometer. So I print with my bed temp at 65c for PLA instead of the default of 60c. 
6) If you are using a smooth PEI sheet, rough it up gently with a scotchbrite pad or fine grit sandpaper. It won't affect your print quality and the rough surface will create more friction for the hot plastic to stick to. 
7) Run the temperature calibration procedure in your printer's options. It will calibrate your PINDA to be more accurate which will help your bed to be more level.
8) Use my startup GCODE below. I've highly optimized it to give the best possible first layer results.
9) If all else fails, buy a powder coated sheet. You can get an aftermarket one on Amazon called [thekkiinngg v3](https://www.amazon.com/Thekkiinngg-Double-Sided-Textured-Powder-Coated-Version/dp/B07HQZCWDV/ref=sr_1_1?s=hpc&ie=UTF8&qid=1546403022&sr=8-1&keywords=prusa+powder+coated) for $60. It's a bit pricey, but PLA sticks amazingly well to this sheet,  and I love the textured finish it gives my prints. Once Prusa begins selling their own powder coated sheets again, they will be a better option.

# Calibrating Live Z My Way
I've found that

# My Optimized Startup GCODE
The following startup GCODE is my custom version which has several advantages over the default Prusa startup gcode. First, it waits until the PINDA is at or below 35c before it does anything, and it enables the print fan to help cool it down quicker in case it's already too warm. It then proceeds to preheat the nozzle to warm temperature (but not the actual print temperature) so that when the printer is doing the automated bed leveling, you do not get plastic leaking everywhere. It sets a standardized bed temp of 65c for the automated bed leveling procedure (change this to whatever bed temperature you do your live Z adjust at) because studies have shown that doing the mesh bed leveling at the same temperature that you did your live Z adjust will be the most accurate. Then, it warms up and waits for your PINDA to reach 35c because studies have also shown that the PINDA is the most accurate after it has warmed up to 35c or warmer and does the mesh bed leveling. Finally, it warms everything up to your real printing temperatures, turns the print fan on so you don't get any ooze, runs an advanced purge line that purges better and is easier to remove from your bed (PETG!), and finally your print begins. 

```M83  ; extruder relative mode

; PINDA cooling
M104 S0 ; Turn off nozzle heat if it's on
M140 S0 ; Turn off bed heat if it's on
M106 S255 ; turn on fan to cool PINDA
M860 S35 ; wait until PINDA is <= 35C
M106 S0 ; Turn cooling fan off if PINDA is cooled

; Standardized bed temp and nozzle preheating
M104 S150 ;preheat nozzle temp for no-ooze and heat up PINDA in the process
M140 S65 ; Set standardized bed temp for mesh leveling and heat up PINDA in the process
G28 W ; go home without mesh bed leveling


; Mesh bed leveling with standardized bed temp and warm PINDA
M190 S65 ; wait for bed temp to finish
M860 S35 ; wait until PINDA is >= 35C
G80 ; mesh bed leveling

; Goto start corner and come up to final temp
G1 Y-3.0 F1000.0 ; go outside print area
M106 S255 ; Turn cooling fan on to prevent oozing and make purge line easier to remove
M104 S[first_layer_temperature] ; set extruder temp for printing
M140 S[first_layer_bed_temperature] ; set bed temp for printing
M109 S[first_layer_temperature] ; wait for extruder temp
M190 S[first_layer_bed_temperature] ; wait for bed temp to finish

; Start the improved purge line
G92 E0.0 ; reset extrusion distance
G1 E2 F1000 ; de-retract and push ooze
G1 X20.0 E6  F1000.0 ; fat 20mm intro line @ 0.30
G1 X60.0 E3.2  F1000.0 ; thin +40mm intro line @ 0.08
G1 X100.0 E6  F1000.0 ; fat +40mm intro line @ 0.15
M106 S0 ; Turn cooling fan off now for enough time to stop spinning
G1 E-0.8 F2100; retract to avoid stringing
G1 X99.0 E0 F1000.0 ; -1mm intro line @ 0.00
G1 X110.0 E0 F1000.0 ; +10mm intro line @ 0.00
G1 E0.6 F1500; de-retract
G92 E0.0

; And a beep to let us know the print is starting!
M300 S100 P10 ; chirp
```
