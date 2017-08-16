# Smoothieware for Micromake D1

#Remember to change the jumper on the board to 1/32 microstepping

###Features:
Hotend fan turns on/off at 50 Degrees C.</br>
Works with standard Micromake Probe.</br>

Pinout info:</br>
http://forums.reprap.org/file.php?13,file=77370,filename=pcb-overview-compressed.jpg


Pronterface can connect to Smoothie over the network by using telnet</br>
just enter ip_of_smoothie:23instead of the serial port before clicking 'Connect'. </br></br>


#Delta calibration and grid levling



M561; clears the grid and turns off compensation</br>
M280 S3.0; Pin down</br>
G32; Probes the three probe points and defines the bed plane, this will remain in effect until reset or M561</br>
M500; Saves the probe points and the probe offsets</br>
G31; probes the grid and turns the compensation on, this will remain in effect until reset or M561/M370 optional parameters Jn sets the radius for this prob</br>
G28; Go Home</br>
G0 Z0; Then move to the point the machine currently thinks is Z 0</br>
; Then move the head to the bed by jogging, using Pronterface's arrows, the panel or the web interface.</br>
M306 Z0; Save new z height</br>
M374; Saves the grid to a file on the SD card (ZGrid).</br>
M500; Saves the probe settings</br> 
M280 S7.0; pin up</br></br>

#Bl Thouch commands
M280 S3.0; Pin down</br>
M280 S7.0; pin up</br>
M280 S5.5 zpin test mode</br>
M280 S8.4 self test</br>
M280 S10.6 Alarm release</br>
