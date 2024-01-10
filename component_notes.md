# Component Notes

## Power connector

Want a standard barrel jack for power.  Should have slots on the PCB that allow it to be either soldered in directly or provide for wires going to a power source.

Bunch of choices here from Amazon:
(doesn't list amperage rating)
https://www.amazon.com/PATIKIL-5-5x2-5mm-Connector-Mounting-Female/dp/B0CLHW3SPB/?_encoding=UTF8&pd_rd_w=bud3w&content-id=amzn1.sym.35cab78c-35e3-4fc1-aab0-27eaa6c86063%3Aamzn1.symc.e5c80209-769f-4ade-a325-2eaec14b8e0e&pf_rd_p=35cab78c-35e3-4fc1-aab0-27eaa6c86063&pf_rd_r=YXCYZ27HZY17TC3D5RAS&pd_rd_wg=EpPZ4&pd_rd_r=29c2366d-478b-466c-8510-573a40c88742&ref_=pd_gw_ci_mcx_mr_hp_atf_m

These are rated 1A:
https://www.amazon.com/AiTrip-20pcs-Connector-Female-5-5x2-1mm/dp/B081DYQSC9/?_encoding=UTF8&pd_rd_w=bud3w&content-id=amzn1.sym.35cab78c-35e3-4fc1-aab0-27eaa6c86063%3Aamzn1.symc.e5c80209-769f-4ade-a325-2eaec14b8e0e&pf_rd_p=35cab78c-35e3-4fc1-aab0-27eaa6c86063&pf_rd_r=YXCYZ27HZY17TC3D5RAS&pd_rd_wg=EpPZ4&pd_rd_r=29c2366d-478b-466c-8510-573a40c88742&ref_=pd_gw_ci_mcx_mr_hp_atf_m

Adafruits got these for 5A:
https://www.adafruit.com/product/373?gad_source=1&gclid=Cj0KCQiAnfmsBhDfARIsAM7MKi22_cj1LK69mG-a5fh6ibPmw4IDtMVQDoazttaAAHgiK1sb4Vnr6-YaApn-EALw_wcB

Here's a 10A from digikey:
https://www.digikey.com/en/products/detail/globtek,-inc./JACK-C-SMT-10A-RA(R)/9837778?utm_adgroup=General&utm_source=google&utm_medium=cpc&utm_campaign=PMax%20Shopping_Product_Zombie%20SKUs&utm_term=&utm_content=General&utm_id=go_cmp-17815035045_adg-_ad-__dev-c_ext-_prd-9837778_sig-Cj0KCQiAnfmsBhDfARIsAM7MKi3oIJ9IoLC3USMjrOdi0Vcz3ng31LfNQRFXefewLY8DuIB42_oSc-caAlX2EALw_wcB&gad_source=1&gclid=Cj0KCQiAnfmsBhDfARIsAM7MKi3oIJ9IoLC3USMjrOdi0Vcz3ng31LfNQRFXefewLY8DuIB42_oSc-caAlX2EALw_wcB

Sparkfun has these 2.5A:
https://www.sparkfun.com/products/119

## Level Translator
Need a 1-bit 3v-to-5v translator.  Could use a 74245, but that's 8 bits (overkill).  I think the 74145 is a one-bit version.

## LED Interface
Want a port for LED interface:  data, 5v, and ground.  Same as with the barrel-jack...slots for either soldering a connector or pig-tail wires to the connector.

## Voltage Regulator
Need a voltage regulator that goes from 5v to the 3v power source on the microbit, and the associated glue-hardware.

I'm leaning towards the 1117-3.3...I've used it before.  Datasheet here:
https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/5011/AMS1117.pdf

Circuit looks like it wants a 22uF tantalum cap at the output, and a 10uF cap on input.  Note that on my old tiny-stick project I didn't include that 10uF..but I will with this one.

And, then looking at JLCPCBs site, this one is no longer manufactured.  :(

They've got a bunch of LD1117DT33TR's.  Downloaded the data sheet; checking out whether they'll work.


## Microbit interface
Ideally, have a right-angle connector that goes into the 25-pin interface on the microbit.  TBD as to whether we do through-hole and solder this in ourselves, or do surface-mount, and have the factory deal with it.

Want to pull out those 25 pins to a through-hole "bus", just in case someone wants access to other pins...and the nice thing here is that if we DON'T populate the connector, the user can wire the microbit away from the translation board.
