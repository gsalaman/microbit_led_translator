# Microbit LED Translator

The microbit can drive strings of LED lights, but it does so with a 3v control line.  The LED strips themselves are current-hungry, and run off 5v.  The goals of this project are as follows:

* Translate the Microbit control signals from 3v to 5v.
* Provide a single 5v power jack that can provide enough current to drive multiple LED strings at high brightness.
* Provide power to the Microbit.


In addition, it's desirable to power the Microbit *either* from the 5v jack *or* a USB cable for programming.  Because of this, we've added a switch for "programming"...in addition to our standard "power switch".

## Board Overview

The basic connections are shown in the diagram below:
![basic_connections](https://github.com/gsalaman/microbit_led_translator/assets/43499190/6d60134f-ddb6-49f2-bba4-7fb4bb62e5ec)

A copule soldering preps are needed for basic operation:
* Solder a barrell connector to the barrell connector jack.
* Solder a switch into both the power connector and the programming connector.
* Solder the microbit connector onto the backside of the board in the microbit jack.  Note it's easier if you trim the two rows of top pins (closest to the microbit itself) before soldering the bottom two rows.
* The LEDs themselves can either be soldered to the appropriate P0, P1 or P2 outlet, or a 3-pin header can be used.

## Operation
You'll want a 5v power source with enough amperage to drive the number of LEDs for your project.  A 2-amp source should drive a little more than 150 lights; if you have more than that, you want a beefier power supply.

The board will route 5v to each of the LED headers, as well as providing 3.3v to the microbit itself.  No USB connetion to the microbit is needed for stanadard operation.  The power switch will gate this power on and off.

If the microbit is powered from this source, it won't recognize programming coming from the USB connector, so if you want to program the microbit whilst connected to the board, flip the programming switch down.  This cuts the 3.3v from the barrel jack, and instead lets the microbit be powered through USB...allowing for it to be programmed. 
