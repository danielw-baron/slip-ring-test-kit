# **Slip Ring Test Kit**

## Introduction

This Test Kit is designed for testing and validating signals from the Stator to the Rotor within a Slip Ring Assembly. It is specifically based on the BS300924 Slip Ring Assembly, details of which can be found at the following link:

[BS300924SCH](https://baronservices.sharepoint.com/:u:/r/sites/PedestalDesign/_layouts/15/doc2.aspx?sourcedoc=%7BB981873C-AACA-43B1-A3F6-C8AE7189F0F1%7D&file=BS300646SCH_Slipring-Schematic_Baron-Pedestal_REVA.vsdx&action=default&mobileredirect=true&cid=556b9e5a-854f-46d5-ad45-b941565b529f)

The Test Kit can test and validate each signal by sending a 15V, 0.5A signal through each input and checking for the signal on each output. There are thirty-seven inputs and corresponding outputs, distributed across fourteen connectors. Detailed documentation of the cable connections is available in the Cable Assembly spreadsheet within this repository.

## How-To

To begin testing the signal, first connect every cable from the Stator and Rotor to the board. The board is powered via a standard 20V, 3A, 5.5x2.5mm Barrel Jack Connector. Upon receiving power, the LCD will activate, allowing navigation through the options menu. The LCD screen is touchscreen, though it may be slightly finicky. To start, press the "Run" button. The program will display each connection, indicating a successful match, mismatch, or a missing signal. After running each input against each output, you can proceed to the "Results" section by pressing the "Exit" button, followed by the "Results" button. Here, you can toggle between each input using the up/down arrows to display each input's corresponding output match.

## Troubleshooting

Feel free to contact me via email at danielwilcox45@gmail.com.

### DISCLAIMER

When troubleshooting, it is crucial to never send power to both the board and the microcontroller, Teensy 4.1, simultaneously. To connect to the Teensy 4.1, first ensure that the board is not connected to power. Then, connect to the Teensy using a Micro-USB cable.

### Software

The board's logic is executed by the Teensy 4.1 microcontroller. It is programmed using the Arduino IDE with the Teensyduino extension, which you can learn more about here: [Teensyduino](https://www.pjrc.com/teensy/td_download.html). The current code running on this board is available in this GitHub repository. To make changes to the software on this board, connect your computer to the Teensy using a Micro-USB cable.

### Hardware

All files related to the board are located in the 'baronradar' folder under my user in Fusion 360. Everything is within the folder 'Final Slip Ring Design'. Here is a [direct link](https://baronweather.autodesk360.com/g/projects/20230725658425551/data/dXJuOmFkc2sud2lwcHJvZDpmcy5mb2xkZXI6Y28ueGd3b3lNM2lUS0drOFgyQ05lYmlyUQ==) to that folder. The most current schematics are not for the current board, however, so below are the changes made:
- Changed the 5V linear voltage regulator to a 5V switching voltage regulator. The current board has a drop-in replacement for that: [Murata Power Solutions Regulator](https://www.digikey.com/en/products/detail/murata-power-solutions-inc/OKI-78SR-5-1-5-W36-C/2259781).
- Added 10K pull-down resistors in parallel with the power resistors at the receiving end of the outputs. The current board has 10K through-hole resistors stacked on top of the power resistors. This ensures a known state even when an output signal may be disconnected.
- Fixed the incorrect footprint for the three CD74HC4514M, where Y14 and Y15 were swapped. The current board has these connections corrected, affecting the input signals fifteen, sixteen, thirty-one, and thirty-two. To mitigate this issue, I swapped the input cables and made a note of this in the Cable Assembly spreadsheet.




