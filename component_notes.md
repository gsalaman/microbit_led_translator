# Component Notes
Want a standard barrel jack for power.  Should have slots on the PCB that allow it to be either soldered in directly or provide for wires going to a power source.

Need a 1-bit 3v-to-5v translator.  Could use a 74245, but that's 8 bits (overkill).  I think the 74145 is a one-bit version.

Want a port for LED interface:  data, 5v, and ground.  Same as with the barrel-jack...slots for either soldering a connector or pig-tail wires to the connector.

Need a voltage regulator that goes from 5v to the 3v power source on the microbit, and the associated glue-hardware.

Ideally, have a right-angle connector that goes into the 25-pin interface on the microbit.  TBD as to whether we do through-hole and solder this in ourselves, or do surface-mount, and have the factory deal with it.

Want to pull out those 25 pins to a through-hole "bus", just in case someone wants access to other pins.
