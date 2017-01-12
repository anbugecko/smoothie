# Smoothieware for Micromake D1


###Features:
Hotend fan turns on/off at 50 Degrees C.</br>
Works with standard Micromake Probe.</br>

Pinout info:</br>
http://forums.reprap.org/file.php?13,file=77370,filename=pcb-overview-compressed.jpg


#Delta calibration and grid levling

M561; clears the grid and turns off compensation</br>
G32; Probes the three probe points and defines the bed plane, this will remain in effect until reset or M561</br>
M500; Saves the probe points and the probe offsets</br>
G31; probes the grid and turns the compensation on, this will remain in effect until reset or M561/M370 optional parameters Jn sets the radius for this prob</br>
G28; Go Home</br>
G0 Z0; Then move to the point the machine currently thinks is Z 0</br>
; Then move the head to the bed by jogging, using Pronterface's arrows, the panel or the web interface.</br>
M306 Z0; Save new z height</br>
M374; Saves the grid to a file on the SD card (ZGrid).</br>
M500; Saves the probe settings</br>
