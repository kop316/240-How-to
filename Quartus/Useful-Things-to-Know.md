## How to compile your design
(You can use any of the following methods):
* Click Processing &rarr; Start Compilation
* CTRL+L
* Click the purple triangle play button in the toolbar

## How to Import Pin Assignments
Download the `DE0_CV_Stormchaser.qsf` file from Canvas. Click Assignments &rarr; 
Import Assignments and select the file you just downloaded. Note that **this step is
critical** in getting your design to do something. If you forget to import pin
assignments then *nothing will happen* and you will be sad.

## How to synthesize your design and program the FPGA
1. Check your FPGA
   * A USB cable should be connected to the top left. There are two sockets and
     **the cable should be in the left socket labeled "Blaster".**
   * A power cable should be connected to the top left near the big red button.
   * The Run/Prog slide switch in the bottom left should be set to "Run."
   * Press the red button to turn on the board. You should see blinking lights,
     counting numbers and the message "Welcome to the Altera DE2-115" on the LCD
     display.
2. Open the Programmer window in Quartus using one of the following ways:
   * Click Tools &rarr; Programmer
   * Double-click on "Program Device (Open Programmer)" in the Task pane.
   * Click on the purple bacon icon in the toolbar
![Quartus programmer](img/quartus_prog.png)
3. Check that the Hardware Setup field says "USB-Blaster." If it doesn't, click
   on on Hardware Setup. In the Currently selected hardware field, choose
   "USB-Blaster" and close the window.
4. If the Start button is grayed out, click Add File, then in the `output_files`
   folder there should be a .sof file. Include that. If there isn't one, you
   haven't compiled successfully.
5. Press the Start button on the left side of the Programmer window.
6. You should see a green progress bar display 100% (Successful). You can close
   the Programmer window now.

## How to find the Compilation Report
If compilation is successful, a Compilation Report will automatically pop up as
a new tab to display information about logic elements, memory bits, and more.
You can also bring up the compilation report with Processing &rarr; Compilation
Report or pressing CTRL+R.

## How to look at Errors and Warnings
The Message pane at the bottom of the window displays errors and warnings. Click
the red circle to show Error Messages, the purple triangle to show Critical
Warnings, and the yellow triangle to show Warnings.

## How to create a file using the built in editor
Click File &rarr; New &rarr; SystemVerilog HDL File &rarr; OK. Press CTRL+S to
save your new file. Name the file and ensure that the "Add file to current
project" checkmark is selected before clicking save.

## How to change editor preferences
![Quartus editor preferences](img/quartus_editorprefs.png)

## About the FPGA board
   * Switches and LEDs are *active high*. A switch that is up means logic 1 and
     an LED lights up when it receives a logic 1.
   * Keys are *active low*. A key that is pressed means logic 0.
   * When you program the FPGA using the instructions described, your design
     only stays in the FPGA while power is available. Turning off the FPGA means
     you have to reprogram it!
