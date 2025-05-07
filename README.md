# Microbit LED Translator

The microbit can drive strings of LED lights, but it does so with a 3v control line.  The LED strips themselves typically require a 5v control line.  In addition, they are currnent-hungry, and come in both 5v and 12v versions.  The goals of this project are as follows:

* Translate the Microbit control signals from 3v to 5v.
* Provide a single 5v or 12v power jack that can provide enough current to drive multiple LED strings at high brightness.
* Provide power to the Microbit.

## Board Overview
We currently support two versions of the Microbit Translator board:  a version for 5v LED strips (white) and for 12v LED strips (Blue).  The purple version is an old version of the 5v board...you can find notes on it [here](https://github.com/gsalaman/microbit_led_translator/blob/main/version1_info.md)

The basic connections are shown in the diagram below (5v version shown):
![Image](https://github.com/user-attachments/assets/5e936c8c-3823-47f5-8cc9-354c99500317)

## Soldering for Basic Operation
A couple soldering preps are needed for basic operation:
* Solder a barrell connector for power.  You want this on the side of the board that has the chips on it, so that it doesn't interfere with plugging in and out the microbit.
* Solder a switch into the power connector.  This can face either side of the board; most folks like it to be facing the side AWAY from the chips (so that you can see the built-in LEDs on the microbit.
* Solder the microbit connector onto the side of the board *without* the chips.  Note it's easier if you trim the two rows of top pins (closest to the microbit itself) before soldering the bottom two rows.
* The LEDs themselves can either be soldered to the appropriate P0, P1 or P2 outlet, or a 3-pin header can be used.

Populated 5v board:
![Image](https://github.com/user-attachments/assets/8883fae2-e30e-4b85-b696-7de554077681)

Populated 12v board:
![Image](https://github.com/user-attachments/assets/31ad0c0c-cf7c-488a-a22b-8fdc5f1d918a)

You'll want a 5v or 12v power source with enough amperage to drive the number of LEDs for your project.  A 2-amp source should drive a little more than 150 lights; if you have more than that, you want a beefier power supply.

The board will route either 5v or 12v to each of the LED headers, as well as providing 3.3v to the microbit itself.  No USB connetion to the microbit is needed for stanadard operation.  The power switch will gate power to the entire system on and off.

## Advanced Operation

### Direct Power Connection
Instead of using a barrel jack connector, you can hook power directy to the pins on the board as shown below:
![Image](https://github.com/user-attachments/assets/abcf005d-9dc8-4885-9bcb-a4684e206cfd)

### Power Switch Bypass

### External Power Switch

### Auxilliary Power and Ground

### Auxilliary Microbit Pin Access

### Level Translation


All of the microbit pins are accessible through the bottom header as shown below:

![vo_bottom_connector](https://github.com/gsalaman/microbit_led_translator/assets/43499190/4ef784af-96f0-4d4e-aea7-f7f57547f29f)

This can be useful if you want to hook into I2C, or pull button A or button B out to a different place in your project.  

In addition, we've made five pins available for translating any 3.3v signals (coming from the microbit) to a 5v signal (if needed from an exteral device).  You'll need to run a wire from the bottom connector to the pins you want to translate...and also note that these only go from 3.3v to 5v....you can't translate from 5v back to 3.3v.  The connector is a little wonky (doesn't go straight accross in V1...this will be fixed in the next version.  See below:

![v0_translation_pins](https://github.com/gsalaman/microbit_led_translator/assets/43499190/47d63c1c-f689-45ef-b097-c1fbfef39a25)

