# CAN-tactorR

### Introduction

CAN based EV contactor controller with built in pre-charge circuit and pre-charge Completed detection.

![CAN-tactor](https://github.com/mackelec/CAN-tactorR/blob/main/images/CAN-tactorR_3d_3.PNG)



### Features

 *  CAN bus interface.
 *  Two high curent mosfet outputs to drive Main Contactors.
 *  On-Board precharge ciruit.
 *  Pre-charge complete comparator. 
 *  STM32F103C8 microprocessor.  (BluePill compatible)
 *  Arduino IDE - stm32Duino
 *  Two digital inputs.
 *  HSTS21 current sensor input (not required)
 *  Aux serial port.
 *  Contactor Lock circuit.  If enganged - only removal or power will deenergise the contactors.
 
### Description

This controller - programmable under the Arduino IDE, uses CAN messages to initiate a full contactor turn on sequence including "Pre-Charge".  Pre-charge is so important that many interlocks have been incorporated.  If a Nissan CAN based controller, eg  [N.I.C.E controller!](https://github.com/mackelec/NICE),  is being used then the voltage reported back from the inverter could be one such interlock.  On-board is a comparitor circuit sensing the voltage accross the Pre-Charge resistor, with a threshold of approximately 10V will give a >95% pre-charge completed signal.

The Controller uses Heavy Duty Mosfets to energise the Contactors.  These Mosfet have more current carrying capabilities than most PCB mount relays.

Contactor Lock Circuit.  While individual outputs can be operated normally, if the Lock signal is triggered, both outputs will remain on even upon reset, only powering down will release the LOCK.

Two digital inputs are included because the EV200 contactors have auxiliary contacts and perhaps they could be used for confirmation that the contactor has operated.  They could also be used as general purpose inputs.


 
