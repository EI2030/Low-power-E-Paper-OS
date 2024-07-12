Mobile Motherboard standards
-

7-12-2024[ New standards proposed](https://hackaday.io/project/177716/details/
):

Brainstorming Draft Specs to develop "FemtoTX" and "AttoTX" form factor

https://en.wikipedia.org/wiki/Small_Form_Factor_Special_Interest_Group

"FemtoTX" (fTX) could be used for tablets and laptops, whereas "AttoTX" (aTX) could be for cell phones, or at least small enough to be in a keycard or usb drive. Though there could be an overlap so that attoTX can also fit on a femtoTX mounting holes (similar to mini-ITX fitting on 4 of 9 Micro holes.

micro	μ	10−6	0.000001	1873

nano	n	10−9	0.000000001	1960

pico	p	10−12	0.000000000001

femto	f	10−15	0.000000000000001	1964

atto	a	10−18	0.000000000000000001

https://en.wikipedia.org/wiki/Metric_prefix#List_of_SI_prefixes (chosen for easy reference, rather than arbitrarily small form factor concept)

Modules and [Stackable](https://archive.ph/20130127190655/http://www.linuxfordevices.com/c/a/News/SUMIT-aims-to-unify-SBC-expansion/) PCBs are typically the most common form factors at sizes under NanoITX. I think this reasoning is not ideal for this standard, because both require or emphazing extra vertical spacing and boards. While this might apppear to ensure a secure connectivity, it appears to increase the minimum number of "boards" to 2.

What if there was a way to use flexible wires that do not get easily disconnected inside a secure enclosure? The ribbons of ATA IDE drives and SATA drives, along with AC97 audio and internal usb headers, are all examples of durable standards cables- they also provide an easy plug an play way to connect disparate components. The same principles could be applied to a square or rectangular standard. A ribbon that connects to an LCD screen could use an FPC connector, while another one connects to a keyboard. A laptop such as the Pi-Top gets a lot right. What I think could be improved is a standard keyboard connector, even a USB, but a low power PS/2 like mini-adapter would actually be more compact than either. Something like a DC plug without the large handle. The smallest DC plugs are less than 1mm:  - .7mm I.D. - 2.35mm O.D: https://www.showmecables.com/dc-power-male-solder-connector-7mm-i-d-2-35mm-o-d
