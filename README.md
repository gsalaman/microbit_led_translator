# Microbit LED Translator

The microbit can drive strings of LED lights, but it does so with a 3v control line.  The LED strips themselves are current-hungry, and run off 5v.  The goals of this project are as follows:

* Translate the Microbit control signals from 3v to 5v.
* Provide a single 5v power jack that can provide enough current to drive multiple LED strings at high brightness.
* Provide power to the Microbit.


In addition, it's desirable to power the Microbit *either* from the 5v jack *or* a USB cable for programming.  Because of this, we're gonna want a switch for "programming"...in addition to our standard "power switch".
