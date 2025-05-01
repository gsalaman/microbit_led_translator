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

## Basic Operation
You'll want a 5v power source with enough amperage to drive the number of LEDs for your project.  A 2-amp source should drive a little more than 150 lights; if you have more than that, you want a beefier power supply.

The board will route 5v to each of the LED headers, as well as providing 3.3v to the microbit itself.  No USB connetion to the microbit is needed for stanadard operation.  The power switch will gate this power on and off.

If the microbit is powered from this source, it won't recognize programming coming from the USB connector, so if you want to program the microbit whilst connected to the board, flip the programming switch down.  This cuts the 3.3v from the barrel jack, and instead lets the microbit be powered through USB...allowing for it to be programmed. 

LED header connections are shown below.

![v0_just_leds](https://github.com/gsalaman/microbit_led_translator/assets/43499190/855e4c6d-17d1-4fa2-ae7b-10f8b7fa8499)

Note that you don't have to use those connectors on the translator board directly...if it makes more sense, you can run lines out to different components in your project...for example, if you want the power switch somewhere external.

## Advanced Operation
All of the microbit pins are accessible through the bottom header as shown below:

![vo_bottom_connector](https://github.com/gsalaman/microbit_led_translator/assets/43499190/4ef784af-96f0-4d4e-aea7-f7f57547f29f)

This can be useful if you want to hook into I2C, or pull button A or button B out to a different place in your project.  Note that if you need additional grounds, you can pull from an unused LED connector.

In addition, we've made five pins available for translating any 3.3v signals (coming from the microbit) to a 5v signal (if needed from an exteral device).  You'll need to run a wire from the bottom connector to the pins you want to translate...and also note that these only go from 3.3v to 5v....you can't translate from 5v back to 3.3v.  The connector is a little wonky (doesn't go straight accross in V1...this will be fixed in the next version.  See below:

![v0_translation_pins](https://github.com/gsalaman/microbit_led_translator/assets/43499190/47d63c1c-f689-45ef-b097-c1fbfef39a25)

