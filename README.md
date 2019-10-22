# Open Glider Network Receiver Station Hardware

This project shows a concrete implementation of the ideas and goals on the 
[Open Glider Network](https://www.glidernet.org/) wiki page discussing how to build an 
[OGN receiver](http://wiki.glidernet.org/ogn-receiver-hardware-and-software#hardware).

Below is my current reference design which incorporates more than 12 receiver-years
worth of experience.
The receivers are located outdoors, in the moderately harsh environment of the Western Cape,
South Africa.


The CAD file for the below diagrams are in their respective directories.

All dimensions are in millimetres.

# Bill of Materials

Item   | Description
---: | :---
Raspberry Pi | Version 3B, 3B+, or 4
FlightAware USB	| With built-in Low Noise Amplifier (LNA), but without the 1090 MHz bandpass filter
SD card | 8 GB, or greater
Backplane | See description below
Outdoor Enclosure | See description below
PoE splitter | Active, standards compliant (IEEE 802.3af)
Antenna-to-SDR adaptor | Male N-type to male SMA adaptor
Antenna | 868 Mhz depending on your location. Available online from China.
PoE injector | Active, standards compliant (IEEE 802.3af)
Ethernet cable | Rated for outdoor usage
Cable/zip-ties | width less than 5 mm


# Backplane

##### Material: ~3 mm plywood, with ~5 mm drilled holes.

The backplane is used to mount the Raspberry Pi and other components on.
It provides strain relief, and durability due to its rigidity.
One may be tempted to drill only those holes that are immediately required, by in my experience,
a re-configurable backplane, decoupled from the immediate components choice, is a better long-term solution.
For example, the Raspberry Pi 4 upgrade swapped the USB and Ethernet positions,
implying that the lower holes [only!] now need to be mirrored.
Other rigid, non-conductive material may be used instead of wood.

![Wooden backplane](backplane/backplane.png)


# Weather-proof Outdoor Enclosure
##### Material: white, 110 mm PVC pipe, and matching commercial, off-the-shelf plumbing fittings.

![PVC pipe enclosure](enclosure/enclosure.png)

Unless the end-cap is holding up the enclosure (on, say, an internal mounting), it stays on tighly enough 
without adhesive, and makes future upgrades easier.


# Assembly

Raspberry Pi on backplane installed in enclosure.

<img src="assy/all.png" height="800">

Parts not shown in CAD drawing:

* PoE splitter, with 5V USB power output (RPi4 requires Type-C plug, the rest, micro-USB)
* Ethernet cable
* FlightAware USB RTL SDR
* Male N-type to male SMA connector (one piece, not a pig-tail)
* Antenna cable


# Receiver's Internal Components
Assembling and securing the internal components.
![Receiver components](assy/rx_int.jpg)


# Receiver Mounted
Final installation, as high up as possible.
<img src="assy/rx.jpg" height="800">


# Thanks

To [PicoJump](https://www.picojump.com) for providing remote SSH and HTTP access, and up-time monitoring.


Please contact me, or open an issue, if you have any questions or suggestions.

