# Prusa i3 MK3 Tips and Tricks

The following informations are things that I have learned from my 3D printing journey with the Prusa Mk3. I don't claim that everything here is 100% factual, and if you think I am providing any incorrect information, please let me know by posting on my Github Issues list! I am still learning myself, and hope to help others to learn from mistakes I made.


# Table of Contents  


**Getting Up And Running**

• [Spare Parts and Supplies You Should Order Immediately](#spares)

• [Tensioning Belts Properly](#tension)

• [Calibrating Live Z My Way](#livez)

• [Calibrating Extruder Idler Tension](#tension)

• [Calibrating Extruder E-Steps](#esteps)

• [Better Slic3r PE Printing Profiles](#profiles)


**Troubleshooting**

• [First Layer Adhesion Issues And How To Fix Them](#flai)

• [Problems Printing PETG Unless Very Slow Speed Used](#petg)

• [Need More Help?](#help)

**Take Things To The Next Level**

• [Put A Sock On It](#sock)

• [My Optimized Startup GCODE](#gcode)

• [7x7 Mesh Bed Leveling](#7x7)

• [Slic3r PE On Meth](#meth)

• [Using Different Nozzles For Different Results and Speeds](#nozzles)

• [Properly Changing Nozzles](#nozzlechange)

• [Achieving Better Print Quality Through Hardware Upgrades](#quality)

• [Recommended Printable Mods For Your Mk3](#mods)



<a name="spares"/>

# Spare Parts and Supplies You Should Order Immediately

The Prusa MK3 is a machine. Like all machines, it needs regular maintenance. Like all machines, it has parts that break with use and need replacement. Below is a list of parts and supplies I recommend you order right away and always have on hand, if you don't want to have 3D printing down-time.

* [Part Cooling Fan](https://all3dmakers.com/products/mk3-part-cooling-fan). The wires on the part cooling fan are ridiculously fragile. I snapped mine right off just by bumping into them with my hand one time. And unless you are amazing at soldering, you can't fix them nor take the fans apart. Always have one of these in your spare parts bag! I also recommend dousing the wires with superglue where they connect to the fan body, it will help keep them from breaking off as easily in the future.
* [Belts](https://all3dmakers.com/products/gates-ll-2gt-rf-6mm-width-2mm-pitch-for-mk3-mk2-5-belt-for-y-axis). Your belts will eventually break with wear and tear. Or maybe you overtighten them and cause them to break prematurely. Always keep one spare on hand for each axis! And always get genuine Gates LL-2GT belts. THESE ARE DIFFERENT THAN GATES GT2 BELTS. Confusing, I know. But the Gates 2GT belts are made specific to the 2GT idlers that Prusa uses, which are different than the GT2 belts and idlers. (note: link is for Y belt only).
* [Powder Coated Sheet](https://www.amazon.com/Thekkiinngg-Double-Sided-Textured-Powder-Coated-Version/dp/B07HQZCWDV). I highly recommend this aftermarket powder coated sheet, it's so much better than the smooth PEI sheet that ships with the Prusa MK3s (unless you were lucky to get the Prusa Powder Coated Sheet which is better). The PEI on your sheet will eventually wear out and it's a pain in the ass to install new PEI on it (though not impossible) so just better to have a spare metal sheet ready to go, in my opinion.
* [Bearings](https://us.misumi-ec.com/vona2/detail/221000091803/?HissuCode=LM8UP&PNSearch=LM8UP&KWSearch=LM8UP&searchFlow=results2type). Your bearings are eventually going to go, and make your printer axis not glide smoothly and be noisy. The link are for Misumi LM8UP bearings, which are the highest quality bearings you can buy. They are even better than the LM8U Misumi bearings that many recommend to buy (the P stands for precision). You need to make sure to grease them when you get them, they come un-greased! Use [this printed tool](https://www.thingiverse.com/thing:1128781) to grease your bearings with [Super-Lube PTFE](https://www.amazon.com/dp/B0081JE0OO/ref=twister_B07HLTTG9L?_encoding=UTF8&psc=1).
* [Super-Lube with PTFE](https://www.amazon.com/dp/B0081JE0OO/ref=twister_B07HLTTG9L?_encoding=UTF8&psc=1). You are going to need to grease your bearings and Z screws every now and then to keep things running smoothly. I high recommend this type of lube for the Prusa MK3. 
* [16x16x2" Concrete Paver (Stepping Stone)](https://www.homedepot.com/p/Pavestone-16-in-x-16-in-x-1-75-in-Pewter-Square-Concrete-Step-Stone-72600/100346228). This is a thick, heavy slab of rock to put underneath your printer, for several benefits. First of all, your printer is basically an open oven - your hotend will heat up to sometimes 300c depending on what you are printing (that's nearly 600 degrees fahrenheit!). Although most of that heat is just happening in the nozzle and not near your surface, it's much safer to have this very hot thing that melts plastic into lava on a concrete surface that is fire-resistant instead of a wooden desk or workbench, just in case something happens and a fire gets started. But just as importantly, you are giving your printer a much more firm and stable surface with no vibrations, which will improve your print quality immensely and eliminate ghosting and ringing effects in your print quite a bit. Even with my printer on a very heavy duty oak wooden desk before, I saw a noticable difference in print quality. It's best to source one of these very large and heavy concrete pavers from your local hardware store - I got mine for only $2. Buying them online and paying for shipping is much more expensive, which is why I don't recommend buying online. Make sure to get one with a smooth flat surface, and not one with a brick or tile pattern that has grooves and ridges, because you want your printer to be level. Speaking of level - be sure your paver is level! If not, use a shim under any of the corners to level it out. You don't need a bigger one than 16x16x2", but that size is the SMALLEST you will need. So feel free to get a bigger one if you want!
* [Smoke Detector](https://www.amazon.com/Kidde-Battery-Operated-Smoke-Alarm/dp/B00PC5SPPK/ref=sr_1_4_acs_ac_1?s=hi&ie=UTF8&qid=1547274798&sr=1-4-acs&keywords=smoke+detector). Kind of going off of the last point, this is for safety reasons, but safety alone. 3D printers get very hot, and you should never leave them unattended; but if you need to because of long print times, a smoke detector is a good idea. People's homes have burned down because of 3D printers! The Prusa MK3 is one of the safest printers out there, but it's better to be safe than sorry! Please the smoke detector near your 3D printer, above it on the ceiling if possible. I highly recommend coupling your smoke detector with a [Roost Smart Wi-Fi Battery](http://www.getroost.com/product-battery.html) which will send alerts to your smartphone if your smoke detector goes off!
* [Remote Wi-Fi Power Shut Off](https://www.amazon.com/TanTan-Wireless-Required-Anywhere-Upgraded/dp/B071VYFJRL/ref=sr_1_3?rps=1&ie=UTF8&qid=1547275131&sr=8-3&keywords=wifi+power&refinements=p_85%3A2470955011). Again for safety, if your printer does happen to catch on fire (knock on wood) and you aren't home, you need a way to shut it off remotely ASAP! You should be monitoring your prints remotely with a web-cam, but wi-fi smoke detector is also useful!


<a name="tension"/>

# Tensioning Belts Properly

It's important your belts are all properly tensioned. Too tight, and you can get backlash (ugly prints), too loose and you can get shifted layer problems (also ugly prints). Now, the Prusa MK3 is kind of unique in that it can tell you what your belt tension is - sort of. To get your belt status numbers, you need to do a self-test (from the Calibration menu), and then after the self-test is done, it will update your belt status numbers which can be seen in the Support menu -> Belt Status. A lower number is a tighter belt, a higher number is a looser belt. Any time you want to get an updated belt status, you need to run self-test again from calibration menu.

Now, the thing about the belt status info is that it doesn't actually measure your belt tension. It instead measures the resistance the X or Y motor encounters when trying to turn, and tries to make a guess at the belt tension. The problem with this is that there can be other factors at play that "fool" the numbers - like belts that are rubbing on the side of the plastic parts or pulleys (not aligned properly), or problems with the motors themselves. 

Even worse is that there's a lot of misinformation out there about what the "perfect" belt status number is. I see 240 being floated around everywhere as the perfect number. That's what I tensioned my belts to. Worked fine for a while, but then one of them snapped on me. OUCH! Good thing I had a spare belt in my drawer.

[Chris Warkocki](https://prusacommunity.com/your-belt-status-and-you/), a pretty big name in the Prusa community that I highly respect, suggests about 270 as being a perfect number for belt status. I totally agree with this, 270 gives me the best results. But just be careful about these numbers. Like I said, the numbers reported on the printer aren't totally accurate. Right now my X belt is reporting 266 and my Y belt is reporting 278, but I can feel for sure that my Y belt is actually tighter. 

So just be very careful about overtightening the belts! You only need your belts tight enough so that the teeth stay engaged in the pulleys without slipping. There is no benefit to having belts tighter than that.

And it's better to have belts on the looser side than the tighter side, in my opinion. Having belts too tight makes it hard for the X and Y axis to move, which must surely put more strain on the motors, as well as decrease the life of the belts.

Ok wait, so how do you actually tension your belts? Well, on the stock MK3 it's kind of hard to do. The X axis has a built-in tensioning screw which is kind of a pain in the ass to really use, and if you tighten it too much it will crack your X axis end printed part (happened to me). So you can use this (follow the Prusa manual) but be very careful. Also, don't expect it to actually tension your X belt too much.  For the Y belt, the only method on stock MK3 to tension it is to loosen the screws that hold the Y belt pulley to the front of the frame, put your belt as tight as possible by hand into the belt grooves on the bottom of the bed, and then tighten the screws in the pulley to pull it tighter. Again, this method really sucks and doesn't allow you to tighten the belt very much.

A much better thing to do is just take the time to upgrade your whole extruder and X axis to the [Bear X axis and Extruder](https://www.thingiverse.com/thing:3226689), and upgrade your Y axis to the [Taurus Y axis](https://www.thingiverse.com/thing:3269389). This will require a lot of printing of parts and a few extra hardware supplies, but it's highly worth it for many reasons, one of them being how easily and convenient they will make it to tension your belts in the future.


<a name="livez"/>

# Calibrating Live Z My Way

Calibrating your Live Z is the most important thing you can do, because your first layer is the most important layer and is what supports all of your other layers. Unfortunately, the Prusa Mk3's built-in live Z calibration has many flaws. For one, it only works with .40mm nozzle size (stock nozzle). Second, the little square it prints at the end for inspection is very small and prints too fast to make any last minute adjustments. I've found this to be the best way to Calibrate Live Z:

1. Download my [100x100x0.20 calibration STL](https://github.com/photog0411/Prusa-i3-Mk3-Resources/blob/master/Calibration%20STLs/LiveZ100x100.stl) file.
2. Open it into Slic3r and slice it with the following settings:
* 0.20mm Layer Height
* Infill Before Perimeters
* Rectilinear top/bottom infill with fill angle of 90 degrees.
* Bed temp at the bed temp you will use for printing the majority of your things.
3. Now print it! It will begin printing a big live Z calibration square that is much easier to see what's going on than with the built-in Prusa one. Because you did infill before perimeters, it will start much quicker because you don't have to wait for the uneeded permieter to get laid down first. And because you have the infill angle set to 90 degrees, it won't waste filament in the corner of the square where you can't see whta's going on.
4. Press the knob on the front of your printer and enter the live Z adjustment mode.
5. Adjust the live Z number until each line that gets laid down has no gaps between it and the last one. You don't want to smush the plastic down too much where the plastic layer developes ridges in it, but really do not want any gaps. I would actually recommend starting at -0.300 and working your way up from there in -0.100 increments. Once you get to a number that looks good (it was -0.700 for me) you can adjust in smaller increments of -0.025 to get it perfect.
6. If you use multiple nozzle sizes, be sure to make a calibration GCODE for each of your nozzles! I personally have a /calibration/ folder on my SD card and calibrate the live Z whenever I swap nozzles.


<a name="tension"/>

# Calibrating Extruder Idler Tension

It's a good idea to make sure your idler in your extruder has proper tension - too loose and it won't grab the filament well enough, too tight and it will crush the filament and cause extrusion issues. It's very simple to get it tensioned properly!

1. With filament loaded and printer preheated for your filament, undo the two screws (or one screw if you are using bear extruder) that hold the idler door in place. These are the screws with the springs on them.
2. Swing the door open fully, make a black mark somewhere on the filament with a sharpie marker for visual reference.
3. Make your printer move the extruder quite a bit, you can do this from inside the printer menu. At this point, the filament should not be moving even though your extruder motor is moving.
4. Close the idler door lightly, and then start screwing the screws in slowly. You want to keep screwing them in until they JUST start to grab the filament and the filament starts moving and extruding.
5. Once it has just grabbed the filament, tighten the screws just a bit more (a few more complete turns).

Now your extruder idler should be properly tensioned!


<a name="esteps"/>

# Calibrating Extruder E-Steps

It's important that when you tell your printer to extrude 100mm of filament, it actually does extrude 100mm of filament. If it's extruding more than you request, it's over-extruding, and if it's extruding less than you request, it's under-extruding. Overextrusion can make for worse print quality on the ouside edges and cause bridges to sag too much, and under-extrusion can cause your prints to be weaker or not have proper infill. 

This is all controlled in your printer firmware by a thing called E-Steps. By default, the Prusa MK3 E-Steps are set to 280, which should be perfect for most printers. But you should still double check it! Here's how:

1. With filament loaded, move your extruder by hand so that it's directly below the filament spool and the filament is straight up and down.
2. Measure 120mm from where the filament enters your extruder and put a mark 120mm up on the filament with a black sharpie marker.
3. Connect the printer to your computer via USB, open Pronterface, and connect to the printer in Pronterface. 
4. Preheat your printer, wait for extruder to be warmed up, and then use the extrude button and settings in Pronterface to extrude 100mm of filament at 100mm / minute. 
5. Once it's done extruding, measure from the top of the extruder to the black mark you made. It should measure exactly 20mm, because you marked out 120mm but asked the printer to extrude 100mm.

Did you get 20mm left? If so, great! If not, remember the amount you measured and follow the steps below to calibrate:

1. Mark the filament again 120mm from the top of the extruder. 
2. In pronterface, issue M503 command in the terminal. It should return steps value, you want to remember the one that says "EXXX" where XXX is the steps number for extruder. If you have never done this before, it should be 280. Those are your extruder steps value currently.
3. Now subtract the amount that was left over from 120mm in the first instructions. So for example if you had 10mm left over instead of the correct 20mm, you would do 120-10=110. This means that your extruder actually extruded 110mm of filament when you asked it to do 100mm.
4. Multiply your current extruder steps value by 100. So if it was at the default of 280, you would do 280x100=28000.
5. Now divide that big number (28000 in example) by the real amount your extruder did. In above example, we said 110 so you would do 28000/110 = 254.54. This will be your new E-Steps value instead of 280. Now you need to actually change this value and save it in your firmware.
6. In Pronterface terminal, issue command M92 EXXX.XX where the X's are your number. In above example, you would do M92 E254.54.
7. Now issue command M500 to save it to your firmware, and you can also do M503 again to verify that the changes were saved.

Your extruder should now be calibrated and pushing 100mm of filament when you ask for it. But you need to verify that it's correct now!  Just start these steps all over again and mark out the 120mm on the filament, and measure when it's done extruding. You should now have 20mm left when you asked it to extrude 100mm.


<a name="profiles"/>

# Better Slic3r PE Printing Profiles

Here in my repository, I have several printing profiles uploaded into the [/profiles/](https://github.com/photog0411/Prusa-i3-MK3-Tips-Tricks/tree/master/Printing%20Profiles) folder. These profiles are much better than the stock Prusa profiles included with Slic3r PE, especially if you have a well tuned and calibrated printer that is functioning well. 

Here's the list and notes for each profile:

* Pretty PLA V3.5a.ini - This is Chris Warkocki's latest Pretty PLA profile (as of 1/12/2018) for printing with PLA filament. YOU MUST have the [7x7 Mesh Bed Leveling Firmware](#7x7) installed on your MK3 printer to use it as-is, but you can also use it on stock firmware by changing the "G80 N7" command in the start gcode to just "G80". This profile is highly tuned for the best possible results printing with PLA, and you should see a nice difference in print quality! Keep in mind this profile is only made for the standard .40 nozzle size, but you can also duplicate this profile in Slic3r and change nozzle size on the printer tab to whatever size nozzle you are using.
* Pretty PETG V3a(7x7).ini - This is Chris Warkocki's latest Pretty PETG profile (as of 1/12/2018) for printing with PETG filament. YOU MUST have the [7x7 Mesh Bed Leveling Firmware](#7x7) installed on your MK3 printer to use it as-is, but you can also use it on stock firmware by changing the "G80 N7" command in the start gcode to just "G80". This profile is highly tuned for the best possible results printing with PETG, and you should see a nice difference in print quality! Keep in mind this profile is only made for the standard .40 nozzle size, but you can also duplicate this profile in Slic3r and change nozzle size on the printer tab to whatever size nozzle you are using.

To install these, just download the .ini files, open Slic3r PE, go to file menu -> Import Profile. Please note that for any of these profiles, I highly recommend duplicating them and adding [My Optimized Startup GCODE](#gcode) to the profiles instead. ;)



<a name="flai"/>

# First Layer Adhesion Issues And How To Fix Them

Before trying the steps below, make sure you have [calibrated your live Z correctly](#livez). Ignore the Prusa video where Josef says it should be a value of around -1.200. Your value will depend on how far up your PINDA is mounted and how thick your bed plate is. Your live Z value is adjusted properly when the lines of plastic that are laid down do not have any gaps in between them. If you think your live Z is adjusted properly, you may begin the following steps: 

1. Clean your bed plate with [99.9% Isopropyl alcohol](https://www.amazon.com/dp/B005DNQX3C/ref=cm_sw_r_cp_apap_2tu8Mct2ObEU7) and UNSCENTED paper towels. Do not use anything less than 99.9% and do not rub it in a circular motion, rather, rub it from side to side. Your bed plate has oils on it from the manufacturing process, and from whenever you touch it with your oily hands. Your goal is getting the oil off, not spreading it around! It's very important to also use unscented paper towels with no coloring designs as these may have oils in them.  

2. If the isopropyl alcohol fails to help, use unscented dish soap and hot water to clean your bed plate in the sink. Scrub it well, and dry with unscented paper towels. Be sure to not touch the clean bed plate with your hands once washed (grip the edges only). Soap breaks down grease and oils even better than Isopropyl alcohol, but is obviously a more annoying process. If you don't touch your bed plate too much, you should be fine with washing your plate in the sink once per month, and rubbing it with isopropyl alcohol once a day before your first print of the day. 

3. If you are still having issues, try printing your first layer hotter. Hotter plastic is more "liquidy" and will spread on the bed easier, as well as stick better. I personally use 220c for PLA and 265c for PETG first layers. 

4. Make sure fan is disabled for first layer in slic3r. You might even want to disable it for the first 2 or 3 layers for  smaller prints, as your plastic being laid down might be cooling too quickly for it to stick. 

5. Try a warmer bed temperature. I personally find that my bed is actually 5c colder than the printer reports after measuring it with an IR thermometer. So I print with my bed temp at 65c for PLA instead of the default of 60c. 

6. If you are using a smooth PEI sheet, rough it up gently with a scotchbrite pad or fine grit sandpaper. It won't affect your print quality and the rough surface will create more friction for the hot plastic to stick to. 

7. Run the temperature calibration procedure in your printer's options. It will calibrate your PINDA to be more accurate which will help your bed to be more level.

8. Use my startup GCODE below. I've highly optimized it to give the best possible first layer results.

9. If all else fails, buy a powder coated sheet. You can get an aftermarket one on Amazon called [thekkiinngg v3](https://www.amazon.com/Thekkiinngg-Double-Sided-Textured-Powder-Coated-Version/dp/B07HQZCWDV/ref=sr_1_1?s=hpc&ie=UTF8&qid=1546403022&sr=8-1&keywords=prusa+powder+coated) for $60. It's a bit pricey, but PLA sticks amazingly well to this sheet,  and I love the textured finish it gives my prints. Once Prusa begins selling their own powder coated sheets again, they will be a better option.

<a name="petg"/>

# Problems Printing PETG Unless Very Slow Speed Used

I had major issues printing PETG using the default Prusa profiles - the infill would just crumble and break. After much trial and error, I discovered the only way to get it to print was to lower the infill speed down ridiculously low to like 15mms. Obviously, this was not preferred. But I was able to eventually get it solved! The easy solution is to just print at 265c for PETG. The Prusa default of 235c is too cold. As someone on the Prusa discord server said to me, "PETG likes it hot". This is absolutely true. After switching to 265c for PETG, it prints faster and more beautiful for me than ever before.


<a name="sock"/>

# Put A Sock On It

I really recommend buying a pack of [silicone socks for the E3D hot end](https://e3d-online.com/v6-silicone-socks-pack-of-3). They are cheap, easy to install, and have several advantages! First of all, they help insulate your hot-end so it stays at a more stable temperature. Second, they make it so that melted plastic won't stick to your hot-end, so you won't have the "Blob of death" issue where you leave a print unattended for hours and come back to find a big blob of plastic stuck to your hot-end that is near impossible to remove. Although my temperatures are much more stable with one installed, I didn't really see an improvement in print quality, but a more stable temperature is never a bad thing.


<a name="gcode"/>

# My Optimized Startup GCODE

The following startup GCODE is my custom version which has several advantages over the default Prusa startup gcode. First, it waits until the PINDA is at or below 35c before it does anything, and it enables the print fan to help cool it down quicker in case it's already too warm. It then proceeds to preheat the nozzle to warm temperature (but not the actual print temperature) so that when the printer is doing the automated bed leveling, you do not get plastic leaking everywhere. It sets a standardized bed temp of 65c for the automated bed leveling procedure (change this to whatever bed temperature you do your live Z adjust at) because studies have shown that doing the mesh bed leveling at the same temperature that you did your live Z adjust will be the most accurate. Then, it warms up and waits for your PINDA to reach 35c because studies have also shown that the PINDA is the most accurate after it has warmed up to 35c or warmer and does the mesh bed leveling. Finally, it warms everything up to your real printing temperatures, turns the print fan on so you don't get any ooze, runs an advanced purge line that purges better and is easier to remove from your bed (PETG!), and finally your print begins. 

**NOTE: AS OF 1/12/2018, MY GCODE BELOW WILL ONLY WORK ON THE PRUSA MK3 WITH THE CUSTOM [7X7 MESH BED LEVELING FIRMWARE](#7x7) INSTALLED. YOU CAN STILL USE IT ON MK2 AND MK3 WITH STOCK FIRMWARE BY CHANGING THE "G80 N7" line to just "G80"**

```M83  ; extruder relative mode

; PINDA cooling
M104 S0 ; Turn off nozzle heat if it's on
M140 S0 ; Turn off bed heat if it's on
M106 S255 ; turn on fan to cool PINDA
M860 S35 ; wait until PINDA is <= 35C
M106 S0 ; Turn cooling fan off if PINDA is cooled

; PINDA warming and Nozzle Preheating
M104 S170 ; preheat nozzle temp for no-ooze and heat up PINDA in the process
M140 S70 ; heat up PINDA quicker by heating bed to hotter temperature
G28 W ; go home without mesh bed leveling

; Mesh bed leveling with standardized bed temp and warm PINDA
M860 S35 ; wait until PINDA is >= 35C
M140 S65 ; set standardized bed temp for mesh leveling
M190 R65 ; wait for bed temp to finish
G80 N7 ; 7x7 mesh bed leveling @ 65c bed temp across all filament types. Do your first layer calibration at this temp!

; Goto start corner and come up to final temp
G1 Y-3.0 F1000.0 ; go outside print area
M106 S255 ; Turn cooling fan on to prevent oozing and make purge line easier to remove
M104 S[first_layer_temperature] ; set extruder temp for printing
M140 S[first_layer_bed_temperature] ; set bed temp for printing
M109 R[first_layer_temperature] ; wait for extruder temp
M190 R[first_layer_bed_temperature] ; wait for bed temp to finish

; Start the improved purge line
G92 E0.0 ; reset extrusion distance
G1 E2 F1000 ; de-retract and push ooze
M106 S0 ; Turn cooling fan off now for enough time to stop spinning
G1 X20.0 E6  F1000.0 ; fat 20mm intro line @ 0.30
G1 X60.0 E3.2  F1000.0 ; thin +40mm intro line @ 0.08
G1 X100.0 E6  F1000.0 ; fat +40mm intro line @ 0.15
G1 E-0.8 F2100; retract to avoid stringing
G1 X99.0 E0 F1000.0 ; -1mm intro line @ 0.00
G1 X110.0 E0 F1000.0 ; +10mm intro line @ 0.00
G1 E0.6 F1500; de-retract
G92 E0.0

; And a beep to let us know the print is starting!
M300 S100 P10 ; chirp - optional
```
Note: Improved purge line taken from [Bob's Project Notebook](http://projects.ttlexceeded.com/)'s custom gcode.

<a name="7x7"/>

# 7x7 Mesh Bed Leveling

On the stock MK3, it does a 9-point mesh bed leveling before each print. With custom firmware, it's possible to do a 7x7 mesh leveling (49-point) mesh bed leveling procedure using custom start GCODE. The advantage of doing this is that it will lead to a much more level and accurate bed while printing, if your bed was not very level to begin with or if your steel build sheet has imperfections. The disadvantage to using this is that it will add about a minute to the start of your print, because it's takes longer for the nozzle to move to 49 points and measure them instead of only 9. Personally, I prefer waiting the extra minute to ensure I have a perfectly level bed!

You can [download it here](https://github.com/prusa3d/Prusa-Firmware/files/2715148/Prusa-Firmware-3.5.1-7x7.zip). Please note that the link is for the most recent version as of writing this (1/12/2019), v3.5.1 of the firmware. When Prusa releases the next version of their official firmware, you will have to wait for the firmware modder to add a new version, or temporarily flash to the official Prusa firmware and stop using the 7x7 mesh bed leveling for a period of time. If you join the Prusa Community facebook group, you can [check in the files section for updated releases](https://www.facebook.com/groups/prusacommunity/files/).

To flash to this firmware, simply download the .hex firmware file, connect your MK3 to your computer via USB, and flash the firmware file onto the printer using Slic3r PE.

To actually use the 7x7 mesh bed leveling, you have to insert the M80 N7 gcode command somewhere before your print starts, using the custom start gcode window in Slic3r PE. Or, you can use [My Optimized Startup GCODE Script](#gcode) which already has the 7x7 built into it.


<a name="meth"/>

# Slic3r PE On Meth

A wonderful github user named [Supermerill](https://github.com/supermerill) has created a custom version of Slic3r PE called [Slic3r++](https://github.com/supermerill/Slic3r). I highly recommend using this version, because it has a lot of new features that the official Slic3r PE is lacking, such as but not limited to top surface ironing, XY hole compensation, continuous perimeter loops, interior top layer supports, avoiding unsupported perimeters, and more! Supermerill  keeps his version current with the latest release of Slic3r PE (so you won't miss out on anything from the main version!) and he's really smart (he's actually the guy that invented Gyroid infill). 


<a name="nozzles"/>

# Using Different Nozzles For Different Results And Speeds

One of the best things you can do with 3D printing is using different sized nozzles. The stock Prusa MK3 comes with only a 0.40mm nozzle, but you can get nozzles in a range from 0.15mm to 1.00mm. Using a bigger nozzle will allow you to print things faster and create stronger functional parts, but printing with a smaller nozzle will allow you to print finer details and make nicer looking prints at the expense of speed. I personally recommend buying 0.15, 0.25, 0.60, and 0.80 only (in addition to your 0.40) for a total of 5 different nozzles. I also recommend buying only genuine E3D nozzles (is it worth it to buy a cheap knock-off brand to save only a dollar or two?) and I recommend buying only [hardened steel](https://e3d-online.com/hardened-steel-nozzles-v6) (or better yet, [Nozzle X](https://e3d-online.com/blog/?p=1006)) nozzles so that you can print with abrasive filament such as wood-fill or carbon fiber (these materials will damage regular brass nozzles).

With a smaller nozzle, you are able to print much more small or detailed objects. They are really great for making tiny miniature figurines with very great detail! But the 0.25mm and 0.15mm nozzles print things very slow - a 3 hour print on the 0.40mm nozzle could take as long as 15 hours with the 0.15mm nozzle! So I really recommend using these smaller nozzles only for very small prints, or prints that you absolutely need the best detail for.

With a larger nozzle, you can print quicker (because your nozzle is laying down wider lines of plastic); and because the lines are thicker, your functional parts will be stronger.

Using a 0.80mm nozzle, you can print almost twice as quick as the standard 0.40mm nozzle - your 16 hour print can now take only 8 hours! That's a great time savings. But why don't I recommend the 1.00mm nozzle? Because the stock E3D v6 hotend can only melt plastic so fast and push it through the nozzle so fast, and in order to use the 1.00mm nozzle you have to drastically lower your print speeds in Slic3r, which negates the time savings of using a larger nozzle. The only reason at all I would recommend using the 1.00mm nozzle is to make the strongest parts possible. If you upgrade your hot-end to an E3D volcano hot-end, you can use the 1.00mm nozzle efficiently (and even print with the other nozzles at faster speeds), but it requires a lot of tinkering and modding of your printer that I don't want to write about. ;)

<a name="nozzlechange"/>

**So how do you change nozzles the proper way once you have them?**

Changing your nozzles seems very complicated, but with practice and the right tools, you can do it in 2 minutes flat like I do. I'm so good at it now that I usually change nozzles before each print depending on what I'm printing! Before starting, I recommend getting and making the following tools:

* [16mm Spanner Wrench](https://www.amazon.com/TEKTON-16-Combination-Wrench-18286/dp/B00Q01OBS0/ref=sr_1_3?rps=1&ie=UTF8&qid=1547272866&sr=8-3&keywords=16mm+wrench&refinements=p_85%3A2470955011). You will use this to hold your heat block in place. You can also use needle nose pliers but the wrench is much better.
* [E3D Nozzle Change Tool](https://www.thingiverse.com/thing:3277211). You can print and make this tool - I highly recommend it! Or you can just use the standard [7mm E3D spanner](https://e3d-online.com/e3d-7mm-nozzle-spanner) instead, but it's a bit slower to use. If using the standard E3D spanner, please wear leather gloves while doing the nozzle change procedure for safety.
* [E3D Nozzle Holder](https://www.thingiverse.com/thing:3280665). Optional, but a nozzle holder you can print to safely store all of your nozzles.

Once you have those items, you can change your nozzle! Just do the following steps:

1. Preheat your printer for the filament currently loaded, and once it's preheated, unload the filament. Skip this step obviously if no filament is loaded.
2. Move your extruder so that the X-axis is almost to the top of your printer, so you can see and work with the nozzle the best. You can do this by holding in the knob on the front LCD panel on the printer and turning the dial.
3. Now carefully remove your front print fan by releasing it's screws, and tuck your print fan between the X axis belts. Be very careful, the wires on the print fan are fragile and can break if you are not careful.
4. Remove the fan duct that the front print fan was sitting in by releasing it's screw.
5. Now heat your nozzle up to 280c and wait for it to come up to temp. This is an important step because you never want to screw and unscrew the nozzles while the heat block is cold, and you want to do it when the heatblock is past it's thermal expansion temperature, which is about 270-275c for the stock aluminum heat block.
6. Place a soft cloth or rag on your print bed.
7. **This thing is EXTREMELY HOT, SO BE CAREFUL**. Take your 16mm spanner wrench (or needle nose pliers) and put a firm grip on the front of the heatblock so it cannot twist while you are unscrewing your nozzle. Be very careful where you place the wrench on the heatblock so you are not close to the wires (the wires are very fragile). The goal is to stop the heatblock from twisting and breaking the heat break tube inside. You don't need to put a super hard crocodile grip on this thing, just enough grip so it's steady when unscrewing the nozzles.
8. Using your E3D Nozzle Change Tool or 7mm spanner, put it on the hex part (6-sided flats) at the top of the nozzle and unscrew it by turning it counter-clockwise. You will have to unscrew it quite a bit before it comes out all the way. It might fall and hit your print bed, which is why I recommend putting the cloth or rag down to protect it. If you are using the 7mm spanner, this will definitely happen, so also be careful of your fingers and hands because the nozzle will burn you severly if it touches your hand when it falls. This is why I highly recommend using the E3D Nozzle Change Tool because it will support the nozzle on the bottom and prevent it from falling. Even better is to wear a nice set of gloves while doing this.
9. Make sure you are gripping the heatblock with the 16mm wrench again so it does not turn or twist.
10. Now screw the new nozzle in, clockwise. You want it to be snug, but don't overtighten it or you can break the heatbreak inside the hot end.
11. Finally, re-install your fan duct and front print fan in the reverse order you took them apart, and cool down your printer. I also recommend only keeping one of the fan screws installed so it's quicker to remove the fan in the future when you are changing nozzles - one screw is more than sufficient to keeping your fan in place and sturdy.

You have now successfully installed a new nozzle.  Be sure when slicing new prints, you are using correct nozzle side settings! Slic3r PE comes with built-in profiles for 0.25, 0.40, and 0.60 nozzles, but if you are using another sized nozzle you can easily duplicate these profiles and set a new nozzle side under the "printer" tab in Slic3r PE.



<a name="quality"/>

# Achieving Better Print Quality Through Hardware Upgrades

There are many things you can do to your Prusa MK3 printer to make it print objects at higher quality. Mostly, it will be print settings in Slic3r that you will have to tweak with trial and error on a per object basis. But let's discuss acheiving better quality with better hardware!

The Prusa printers are known to be cursed with a problem called the [602 Inconsistent Extrusion Issue](https://github.com/prusa3d/Prusa-Firmware/issues/602). Follow that link for example photos and more information. Basically, it leads to layer lines on the sides of your prints sticking out our being recessed in at spots which is very noticable. This is very hard to correct 100%, but there are some things you can do to help fix this problem a bit - those are listed below. The main cause of this issue is inadequate heatbreak cooling.

There are also other hardware upgrades listed below that not only correct the 602 issue, but also improve print quality in other ways. I ordered them from what I believe to have the biggest affect on print quality to least. Also check out the "printable mods" section following this section for more things that will help increase your quality!

* [Bondtech BMG Extruder](https://www.bondtech.se/en/product/prusa-i3-mk2-5-mk3-extruder-upgrade/). This is a whole new extruder  for your Mk3, and it's expensive. But because it has much better cooling than the stock extruder and a better gearing ratio, it has been shown to almost completely eliminate the 602 Issue and allows printing at higher resolution.
* [Sunon Extruder Fan](https://all3dmakers.com/products/sunon-mk2-5-mk3-5v-hotend-cooling-fan). This is a replacement fan for the default Noctua fan that ships with the printer. It is much more powerful, at the expense of being louder. But it will help your 602 Issue very much by cooling your heatbreak much better! I highly recommend this fan to replace the stock fan.
* [Misumi LM8UP Bearings](https://us.misumi-ec.com/vona2/detail/221000091803/?HissuCode=LM8UP&PNSearch=LM8UP&KWSearch=LM8UP&searchFlow=results2type). These are arguably the best bearings available for your printer. They might increase print quality slightly, as well as make your printer slightly quieter. They will also last longer than the stock bearings that ship with the MK3. You need to make sure to grease them when you get them, they come un-greased! Use [this printed tool](https://www.thingiverse.com/thing:1128781) to grease your bearings with [Super-Lube PTFE](https://www.amazon.com/dp/B0081JE0OO/ref=twister_B07HLTTG9L?_encoding=UTF8&psc=1). You should also get matching Misumi rods (below)! You will need 3 bearings for the X axis, 3 bearings for the Y axis, and 4 bearings for the Z axis. However, X and Y axis are most important if you want to save some money, the Z axis is not as important.
* [Misumi Rods](https://us.misumi-ec.com/vona2/detail/110302634310/?HissuCode=PSFU&PNSearch=PSFU&KWSearch=PSFU&searchFlow=results2type&curSearch=%7b%22field%22%3a%22%40search%22%2c%22seriesCode%22%3a%22110302634310%22%2c%22innerCode%22%3a%22%22%2c%22sort%22%3a1%2c%22specSortFlag%22%3a0%2c%22allSpecFlag%22%3a0%2c%22page%22%3a1%2c%22pageSize%22%3a%2260%22%2c%2200000028941%22%3a%22mig00000001498696%22%2c%2200000028938%22%3a%2200000028938.a!00001%22%2c%2200000028940%22%3a%22b%22%2c%2200000028942%22%3a%22e%22%2c%22typeCode%22%3a%22PSFU%22%2c%22fixedInfo%22%3a%22MDM00000529299110302634310-1518478229%7c13%22%7d&Tab=wysiwyg_area_0). These rods are more precise than the stock rods that ship with the Prusa MK3. They are matched to the Misumi bearings above. You will need a total of 6, 2 of each of the following lengths: 320mm, 330mm, 370mm.
* [Better Thermal Paste for your Heatbreak](https://www.amazon.com/Thermal-Grizzly-Kryonaut-Grease-Paste/dp/B011F7W3LU). Since we know that one of the leading causes of the 602 Issue is bad heatbreak cooling, it couldn't hurt to put a higher quality thermal paste on your heatbreak. Simply unscrew the heatsink from the heatbreak, remove the old thermal paste, and apply the new paste gingerly to the threads. This probably won't help a whole lot, but it can't hurt! The link above is for Thermal Grizzly Kryonaut paste which is very good and what I'm using, but if you want the very best paste look into something called CooLaboratory Liquid Pro - it's the very best paste you can buy, but very expensive.


<a name="mods"/>

# Recommended Printable Mods For Your Mk3

Below are mods I highly recommend you make for your MK3. They will either make your life easier, or improve the quality of your prints. Maybe both.

* [Bear Extruder and X Axis](https://www.thingiverse.com/thing:3226689). This is a whole new extruder and X-axis for your Mk3, but everything is printable. It's a big project, but very much worth it. It will increase your print quality, make it easy to tension your X axis belt, and also make your printer easier to take apart or fix in the future. I highly recommend it, but make sure to print a [compatible fan duct](https://www.thingiverse.com/thing:3320490) for it too!
* [Taurus Y Axis](https://www.thingiverse.com/thing:3269389). This is a new Y motor mount and belt system, mostly all printable as well. It is much stronger than the default Y axis parts, and allows you to easily tension your Y axis belt. You may notice a slight increase in print quality with this.
* [Rigid Feet for MK3](https://www.thingiverse.com/thing:3082188). The rubber feet with the Prusa MK3 are great for making the printer slightly quieter, but upgrading to rigid feet (printable) will improve quality and help eliminate ringing and ghosting effects!
* [Bed Bearing Holder Clamps](https://www.thingiverse.com/thing:2984280). Do you remember how much of a pain in the ass it was to install the bearings to the bottom of your bed using those stupid U-bolt things? Well, print 3 of these puppies out and it will make your life a lot easier in the future if you ever have to change out the bearings. They also made my bed a little bit quieter! Just be careful before installing these, they will NOT work on a stock MK3 frame with M3 Nuts in them (they will bump into the frame), you have to get heat-press inserts (threads!) instead to put in these! Just search online for Brass M3 Heat-Press Threaded Inserts, you will want ones 3mm in length. They are fairly cheap.
* [Improved Z Motor Mounts](https://www.thingiverse.com/thing:2775169). These improved Z-motor mounts will fix some leveling issues with the stock Z motor mounts, make them sturdier, and also make it easier to take your printer apart in the future because they are modular and have a slot! I highly recommend installing these.
* [Mk3 Dust Filter](https://www.thingiverse.com/thing:2983334). Easily print and make a dust filter for your extruder. This will help prevent nozzle clogs from happening by filtering dust from your filament. This is only compatible with stock extruder, not bear extruder.
* [Extruder Visualizer](https://www.thingiverse.com/thing:2638857). Decorate your extruder, but at the same time be able to see what your motor is doing. Great for troubleshooting extruder movements. There are many other design available on thingiverse, or you make your own. All you need is a magnet and some glue.
* [E3D Nozzle Holder](https://www.thingiverse.com/thing:3280665). A great way to store your E3D nozzles if you have a bunch of them.
* [E3D Nozzle Change Tool](https://www.thingiverse.com/thing:3277211). Change your nozzles very easily if you have multiple nozzles.
* [Prusa Mk3 Top Tool Holder](https://www.thingiverse.com/thing:3175038). Conveniently store and access the most frequently used tools.



<a name="help"/>

# Need More Help?

Read Bob's Project Notebook:

http://projects.ttlexceeded.com/


Check out the Prusa Owner's Wiki:

https://github.com/mcm001/prusaOwnersWiki


Post on Reddit:

https://www.reddit.com/r/prusa3d/


Or ask a question in the 602 Wasteland Discord Chat for more immediate help:

https://discord.gg/hYUjSnW
