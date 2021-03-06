Using the MCP23S17 I/O expander 
===============================

This folder contains the source files for working with the GPIO pins of the
MCP23S17 16-bit I/O expander via SPI bus, which is available e.g. on the 
Raspberry Pi minicomputer. The example is based on the REXLANG user-programmable 
function block of REX. 

The GPIO port A is used as digital outputs, the GPIO port B is used as digital
inputs with the internal pull-up resistors enabled. 

See the source **.c* file for details on SPI communication.

## Timing of the project ##

The algorithm runs each 200 milliseconds (0.2 s). See the EXEC function block,  
tick x ntick0 = 0.1 x 2 = 0.2 

## Prerequisities ##
- RexCore must be installed and running on the target device (e.g. Raspberry Pi).
- SPI bus must be enabled and available (e.g. /dev/spidev0.0).
- The wiring must comply with the attached datasheet. 

## Running the example ##
- The **exec.mdl* file is the project main file.
- Open it with *RexDraw*.
- Specify the SPI bus by the p0 parameter of the REXLANG function block.
- Compile and download it to the target device.
- Switch to online mode and watch the algorithm.
- Enable online monitoring of the CNB_GPA blocks (Target->Watch Selection) and 
the BDOCT_GPIOB block.
- Toggle the CNB_GPA constants and observe the pins of the MCP23S17 I/O 
expander.
- Apply external voltage to GPIOB pins and observe the outputs of BDOCT_GPIOB 
block.  

## Documentation ##

- **Press F1 for help** on the selected function block in the *RexDraw* program.
- [Getting started with REX on the Raspberry Pi minicomputer](https://www.rexcontrols.com/media/2.50.4/doc/ENGLISH/MANUALS/RexGettingStarted/RexGettingStarted_RasPi_ENG.html)
- [Function blocks of REX](https://www.rexcontrols.com/media/2.50.4/doc/ENGLISH/MANUALS/BRef/BRef_ENG.html)
- MCP23S17 datasheet (attached)
- [RexDraw User Guide](https://www.rexcontrols.com/media/2.50.4/doc/ENGLISH/MANUALS/RexDraw/RexDraw_ENG.html)
- [Complete documentation of REX](http://www.rexcontrols.com/documentation-and-support)

## Additional information ##

- Raspberry Pi is a trademark of the [Raspberry Pi Foundation](http://www.raspberrypi.org).
- Visit the [REX Controls company webpage](http://www.rexcontrols.com) 
for more information about the example projects and developing advanced 
automation and control solutions using REX.