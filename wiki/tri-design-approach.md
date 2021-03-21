# Tri-design Approach

The aim of the Low-power E-Paper OS is ideally to be able to run on solar panels that can fit on a laptop chassis such as the Pi-Top & be able to be recharged indoors, rather than outdoors. This design choice is intentional, and while I understand the much more difficult task of harvesting from indoor light, I am also aware that most computing is done indoors, rather than at an outdoor cafe that may be exposed to sunny conditions. For each hardware choice (e.g E-Paper/RLCD,MCU & Memory) and software (OS) to be considered for this project, they should, at least in the long term, be a microcontroller or microprocessor family capable of being solar powered using ambient indoor light by meeting three criteria: Power, memory and size.

1. Power refers to the thermal design power of the MCU, SRAM & Display. In Sparkfun Artemis, for example (not limited to the Artemis), the Ambiq Apollo3 uses 6uA/mhz, and 576uA at 96mhz. Therefore, at 3.3V, the MCU alone uses around 1.9mW and w/SRAM & peripherals around 5mW. A 5 watt solar panel is able to power 5mW with a single 10.5W LED bulb without any outdoor sunlight. https://www.youtube.com/watch?v=txj-0iy4xJw In Epaper, the power consumption for each refresh of a Waveshare display can be as low as 26mW: https://www.waveshare.com/5.83inch-e-Paper.htm Other displays such as SHARP Memory or MIP (Memory-In-Pixel) displays may use an overall lower average consumption for more frequent refreshes: https://www.adafruit.com/product/4694

2. Memory refers to the total SRAM and any RAM activity that the OS uses during normal utilization. In the Sparkfun Artemis Nano (Apollo3), it is 384KB. The solar panel does not require extra power to run an RTOS, therefore an RTOS can be fully solar powered with an indoor light. If wanting to choose a larger OS that requires 2-8MB of RAM, the added or included RAM (such as on the Apollo4) must be low power enough so that the extra power consumption (whether it is 3mA-20mA) can be powered by a single light bulb. Possible considerations include MRAM and FRAM via QSPI/OPI.

3. Size refers to the disk space of the onboard flash and any additional external storage added. The criteria mentioned in #2 also apply. If the external storage medium uses a power consumption exceeding the amount of power that a solar panel on a laptop can produce, then it cannot be chosen to be as the permanent storage device for the solar laptop to be fully ambient-light harvesting. The energy harvested from a solar panel such as an ANYSOLAR SM262K10L (which has a Voc larger than than the 4V maximum of the AEM10941 and is not immediately compatible) onto an integrated power manager such as the Epishine Evaluation Kit or similar integrated manager from a typical day of exposure to indoor light should equal twice the amount of daily power (assuming 8-12hrs of light & operation) consumed by the MCU, RAM, Storage & Display combined, so that it can be operated daily along with topping-up the battery via pass-through charging.

A mathematical representation of this can be expressed as (Power) x/1 + (Memory) y/1 + (Size) z/1 =1/1, where x refers to the power consumption of MCU, display, keyboard, trackpad and must be a value less than 1. y refers to the power consumption of the RAM, and is <1. z refers to the power consumption of the storage, and must also be <1. 

It may be possible to further separate the hardware into w/1 for the display since it might represent a larger fraction of the consumption, but at a higher level, the hardware  (including the RAM) is best considered just 1.5 categories, since the software has an equal focus in the design, and is therefore is weighed more evenly with RAM (0.5) & Storage criteria (1).

Also, as (x+y+z)/1 should equal 1, assume 1 also represents half of the Amp hours harvested in an 8-12 hr period of ambient light.   


                                                            
https://www.brainyquote.com/quotes/saul_alinsky_138507 "Change means movement. Movement means friction. Only in the frictionless vacuum of a nonexistent abstract world can movement or change occur without that abrasive friction of conflict."

My belief is that laptops, compared to standardized ATX desktop, cases are largely wasted and non-reusable plastic.

On a deeper level, these constraints are designed to change what we think of a mobile device chassis- raw materials that, being non-recyclable bricks after their planned obsolescence, can now be reused as a shell since its decomposition is effectively non-existent. https://www.npr.org/2020/09/11/897692090/how-big-oil-misled-the-public-into-believing-plastic-would-be-recycled The alernative is to use materials that can be recycled, however, this would typically apply to the chassis, and not the electronics. Additional research is also needed for organic electronics.

Other projects that  this include https://www.crowdsupply.com/eoma68/micro-desktop 

http://rhombus-tech.net/whitepapers/ecocomputing_07sep2015/

https://ploum.net/the-computer-built-to-last-50-years/ A great background on computing and typewriters.
