# Smoothieware for Micromake D1
#!!! Untested !!! Work in progress !!!



###Features:
Hotend fan turns on/off at 50 Degrees C.</br>
Works with standard Micromake Probe.</br>

Pinout info:</br>
http://forums.reprap.org/file.php?13,file=77370,filename=pcb-overview-compressed.jpg


#Delta calibrate

M561; clears the grid and turns off compensation

G32; Probes the three probe points and defines the bed plane, this will remain in effect until reset or M561

M500; Saves the probe points and the probe offsets

G31; probes the grid and turns the compensation on, this will remain in effect until reset or M561/M370 optional parameters Jn sets the radius for this prob

G28; Go Home

G0 Z0; Then move to the point the machine currently thinks is Z 0

; Then move the head to the bed by jogging, using Pronterface's arrows, the panel or the web interface.

M306 Z0; Save new z height

M374; Saves the grid to a file on the SD card (ZGrid).

M500; Saves the probe settings
