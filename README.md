# AN930
J1939 C Library for CAN-Enabled PICmicro® Microcontrollers

## 1. Introduction
The goal of the ECAN (Enhanced Control Area Network) Based J1939 Module is to supply the designer with a library containing all necessary code to quickly develop a J1939 based application running on top of a CAN Protocol.
Designed to encapsulate implementation details it contains several functions and variables that Initialize, Read, Write and return the status of messages transferred in a CAN network.
The library can be used in a pooling based designs as well as on Interrupt-driven ones, which provides additional benefits of parallel processing. The C code is both linkable and relocatable, allowing easy integration into existing application code.
## 2. Module Features
* Supports user-defined setup of CAN and ECAN parameters like baud rate, maximum message size, number of reception/transmission buffers.
* Incorporates interrupt-driven transmission and reception capabilities, allowing users to run other tasks in the foreground.
* Simple function based Interface, which enables easy read, write and communications management.
* Supports for PIC18 family devices containing both CAN and ECAN modules.
## 3. List of Component Modules
| File | Description | 
|--|--|
| \examples\example1a\main.c <br> \examples\example1b\main.c <br> \examples\example2a\main.c <br> \examples\example2b\main.c <br> \examples\example3a\main.c <br> \examples\example3b\main.c <br> \examples\example4a\main.c <br> \examples\example4b\main.c <br> \examples\example5a\main.c <br> \examples\example5b\main.c | This are the main test files developed to demonstrate the usage of the library functions. They here originally designed to run in pairs (ex: ex1a <-> ex1b) using a PICDEM CANLIN board although the adaptation to another environment should prove straighforward. (These files are compressed in the examples.zip file) | 
| j1939.c | J1939 C-code source file. Contains the variables and functions. __One needs include this file in their project.__|
| j1939.h | This file contains the prototype of the functions, definition of macros, unions, structures, constants and definition of external references. __One needs include this file in all source files of it's project who access LIN.__ |
| j1939.def | This file contains the set-up definition of all parameters necessary to customize the driver. |

## 4. Using the Library Module in a Project
Please follow below steps to use this library module in your project.
1. Use Application Maestro to configure your code as required.
2. At the Generate Files step, save the output to the directory where your code source files reside.
3. Launch MPLAB, and open the project’s workspace.
4. Verify that the Microchip language tool suite is selected (Project>Select Language Toolsuite).
5. In the Workspace view, right-click on the “Source Files” node. Select the “Add Files” option. Select J1939.C and click OK.
6. Now right-click on the “Linker Scripts” node and select “Add Files”. Add the appropriate linker file ( ) for the project’s target microcontroller.
7. Add any other files that the project may require. Save and close the project.
8. In the source files (C) that interact with the module add an include directive at the head of the code listing to include J1939.H. By doing so, all files required to make the generated code work in your project will be included by reference when you build the project.
9. To use the module in your application, invoke the Functions as needed.
## 5. List of Shared Parameters
Shared Functions[^1]
[^1]: For a complete description of all functions and variables please refer to AN930 Application Note.

|USAGE|NAME|BRIEF DESCRYPTION|
|--|--|--|
|Reception|J1939_DequeueMessage|Copy received message from queue to buffer|
|Transmission|J1939_EnqueueMessage|Copy message from RAM to transmission queue|
|Initialization|J1939_Initialization|Starts all necessary variables, CAN module and claiming address|
|Transmission<br>/Reception|J1939_ISR|Interrupt Based reception and transmission Routine|
|Transmission<br>/Reception|J1939_Poll|Checks for Reception, Check for Address Contention|
