# **Slip Ring Test Kit**


## Introduction


This Test Kit is responsible for testing and validating signals from the Stator to the Rotor within a Slip Ring Assembly. 
This Test Kit in particular is based off of the BS300924 Slip Ring Assembly, found at the link below.

[BS300924SCH](https://baronservices.sharepoint.com/:u:/r/sites/PedestalDesign/_layouts/15/doc2.aspx?sourcedoc=%7BB981873C-AACA-43B1-A3F6-C8AE7189F0F1%7D&file=BS300646SCH_Slipring-Schematic_Baron-Pedestal_REVA.vsdx&action=default&mobileredirect=true&cid=556b9e5a-854f-46d5-ad45-b941565b529f)

The Test Kit is able to test and validate each signal by sending a 15V 0.5A signal through each input, and checking for the signal on each output. 
There are a total of thirty-seven inputs and thirty-seven respective outputs, through a total of fourteen connectors. 
For a detailed documentation of the cable connections, refer to the Cable Assembly spreadsheet found within this Repo. 


## How-To


In order to begin testing the signal, first make each and every connection from Stator and Rator to the board. 
The board is powered via a standard 20V 3A 5.5x2.5mm Barrel Jack Connector. 
Once the board receieves power, the LCD will come to life allowing you to navigate the options menu. 
The LCD screen is touchscren, albeit a little finicky, so to begin just hit the "Run" button. 
The program will now display each connection, with there either being a succesful match, mismatch, or a missing signal. 
Once the program has finished running each input against each output, you can head to the "Results" section.
Just hit the "Exit" button, and then hit the "Results" button. 
You will now be able to toggle between each input using the up/down arrows, this will display each input's respective output match. 


## Troubleshooting


First and foremost, feel free to reach out to me via my email: danielwilcox45@gmail.com

### DISCLAIMER

It is imperative that when troubleshooting you never send power to both the board and the microcontroller, the Teensy 4.1. 
In order to connect to the Teensy 4.1, you will first ensure that the board is not currently connected to power. 
You can then connect to the Teensy via a Micro-US cable. 

### Software

This board's logic is executed by the Teensy 4.1 microcontroller. 
I programmed the Teensy via the Arduino IDE and an extension Teensyduino, more info on that here: https://www.pjrc.com/teensy/td_download.html
The code that is currently running on this board can be found within this GitHub repo. 
In order to make any changes to the software on this board, you need to connect your computer to the Teensy via a Micro-USB cable.

### Hardware

All files related to the board can be found within the 'baronradar' folder under my user in Fusion 360.
Everything can be found within the folder 'Final Slip Ring Design', here is a [direct link](https://baronweather.autodesk360.com/g/projects/20230725658425551/data/dXJuOmFkc2sud2lwcHJvZDpmcy5mb2xkZXI6Y28ueGd3b3lNM2lUS0drOFgyQ05lYmlyUQ==) to that. 
The most current schematics found are not the current board however, so I will detail the changes that were made below. \
    - Changed the 5V linear voltage regulator to a 5V switching voltage regulator. The current board has a drop-in replacement for that: https://www.digikey.com/en/products/detail/murata-power-solutions-inc/OKI-78SR-5-1-5-W36-C/2259781 \
    - Added 10K pull-down resistors in parallel with the power resistors at the recieveing end of the outputs. The current board has 10K through-hole resistors stacked on top of the power resistors. This is done to ensure a known state even when an output signal maybe disconnected. \
    - Fixed the incorrect footprint for the three [CD74HC4514M](https://www.ti.com/lit/ds/symlink/cd74hc4514.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1704491308024&ref_url=https%253A%252F%252Fwww.ti.com%252Fgeneral%252Fdocs%252Fsuppproductinfo.tsp%253FdistId%253D10%2526gotoUrl%253Dhttps%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Fcd74hc4514), where Y14 and Y15 were swapped. The current board has these connections swapped, which affects the input signals fifteen, sixteen, thirty-one, and thirty-two. In order to mitigate this issue, I swapped the input cables. I made a note of this in the Cable Assembly spreadsheet.



