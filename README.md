Low-power-E-Paper-OS Working Group

=====================

**Status:** Approved

**Name:** Low-power E-Paper OS

**Objective:**  The goal of this project is to run an OS on an ultra low-power CPU/MCU that can output terminal or a window manager to an e-paper display.

**Timeline:** 3/14/2021-4/13/2021

**Members:** @scrunch, @alexsotodev open to new members, including after project started.

**Contact:** giovanni.lostumbo@gmail.com

**URL:** https://forum.ei2030.org/t/low-power-e-paper-os/138

https://alexsoto.dev/static/community-built-eink-laptop-project/slides.pdf (Slides 45-49)

https://discord.com/invite/nnxKnxh 

**Hardware:** Redboard Artemis, SAMD51, Dialog 14695, ESP32, STM32, other MCUs/MPUs with can be used, including ones with E-paper already connected, like M5Paper, or LILYGO® TTGO T5.

Looking for:

"At this point, we need other people interested in the idea of this super-low-power device with its “I’m not a regular laptop” aspiration. You can help us figure out the key important areas for us to focus on. No special skills needed! If you like the sound of such a device, email us and join! No required time-commitment and no contribution is too small and no worries of all of this microcontroller-type talk goes over your head. We need you!"
from: https://forum.ei2030.org/t/paperterm-project-definition-and-marketing-materials/146

If you do have experience (and it is welcome), these fields are of particular help:

"Embedded Development

Electrical Engineering

Software Developers

Reverse-Engineering

Writers/Researchers"
from: https://forum.ei2030.org/t/research-drivers-for-eink-displays/150

This may sound like a purely high-tech project (read: hard/inaccessible), but it is not, since leading edge hardware/tech is now available in the open-source community. The Sparkfun company (which makes the Artemis boards with Apollo3) helped changed that perception, because if NASA used Sparkfun's altimeter, then it means open-source tech can (and has been) designed to be both leading tech and accessible. Other technology companies like Adafruit, Digikey & Mouser also provide high-quality electronics to non-business entities (i.e hobbyists).

Source: https://spectrum.ieee.org/automaton/aerospace/robotic-exploration/nasa-designed-perseverance-helicopter-rover-fly-autonomously-mars
Finding the available tools and hardware is the first half of the battle. Before starting this project, I did a few Google searches- "solar powered cpu"  by doing this, I was able to unearth a lot of research from early 2011: https://hexus.net/tech/news/cpu/31745-intel-shows-solar-powered-cpu-experiment/ 
https://www.theregister.com/2011/09/16/claremont_near_voltage_processor/
"Near-threshold voltage" (and near-threshold computing) are terms rarely used in the mainstream market. 
The origins of NTV are earlier, from the Phoenix processor: https://news.umich.edu/microchip-sets-low-power-record-with-extreme-sleep-mode/ 

Technology that optimizes low-power cpus for both sleep and active modes has a benefit for not only wearables and IoT, but also user interface applications. This avenue (Cortex A series processors, as opposed to Cortex M0 or M4) has rarely been developed for, due to the likely power needs of the most performance-hungry apps.

But what if not every person needed an app that uses lots of bandwidth and cpu utilization? See this article for reference: 
http://rhombus-tech.net/whitepapers/ecocomputing_07sep2015/

At least one company in recent news claims to operate an application processor in the NTV range: http://www.micromagic.com/news/eeNewsAnalog_Santoro_Interview.pdf

The current issue here is that there is not much demand right now. However, as more research and development goes into products that can easily be recharged by solar, the demand to avoid long charging cycles for app-hungry phones will increase. Instead of waiting for an application processor to be released using NTV, it may be more practical to port linux to the Ambiq Apollo4, which uses  Sub-threshold Power Optimized Technology: https://www.electronicdesign.com/technologies/microcontrollers/article/21800524/subthreshold-cortexm4f-design-sips-less-power-than-cortexm3 With the Apollo4 being released Q2 2021, Ambiq has lowered uA/mhz from 30uA/mhz in the Apollo1 to 3uA/mhz in the Apollo4. Furthermore, Sparkfun's Artemis boards which use 6uA/mhz, use so little power than I was able to solar power the LED for an Adafruit boost charger, along with the Red and blue power LEDs on the Artemis.

RAM:
https://www.apmemory.com/products/psram-iot-ram/ (Density is 2MB-32MB in QSPI & OPI)

https://www.eejournal.com/industry_news/ambiq-and-ap-memory-partner-to-enable-richer-experiences-in-intelligent-endpoints/
"AP Memory solutions offer low signal pin count (6 for QSPI, 11 for OPI), low power (standby from 20µA to 80µA, active from 3mA to 8mA), and high transfer rate options needed to meet the demanding power and space constraints of wearable and other battery-powered smart consumer devices."

One approach is to run linux via external memory, using XIP:
https://en.wikipedia.org/wiki/Execute_in_place
https://www.embeddedcomputing.com/technology/storage/execute-in-place-xip-an-external-flash-architecture-ideal-for-the-code-and-performance-requirements-of-edge-iot-and-ai
of which Apollo3 has 64MB-96MB of aperture:

"The Apollo3 Blue Plus adds two additional MSPI modules (3 total), and increases the external memory execute-in-place (XiP) aperture from 64MB to 96MB (32MB/ MSPI instance). Additionally, internal flash increases from IMB to 2MB, SRAM from 384KB to 768KB (TCM size remains at 64KB) and the GPIO count increases from 50 to 74."
https://www.top-electronics.com/en/apollo3-blue-plus-mcu-768kb-108pin-bga
MSPI: Dual/Quad/Octal-SPI Master (3x) 48Mhz SDR ISO7816 Master

Apollo4: https://ambiq.com/wp-content/uploads/2020/10/Apollo-MCU-SoC-Selector-Guide.pdf
MSPI: Dual/Quad/Octal-SPI Master (3x) 96Mhz SDR 48Mhz DDR

https://www.cnx-software.com/2020/09/17/ambiq-apollo-4-mcu-3%C2%B5a-mhz/
"Ultra-Low Supply Current
3 μA/MHz executing from MRAM (with cache)
3 μA/MHz executing from SRAM
1.5 μA low power sleep mode with RTC and 8KB SRAM retention"

Solar Power Managers (integrated):
https://www.epishine.com/pr/joint-webinar-with-three-leading-actors scaled up to IXolar sizes: 
https://www.digikey.com/en/products/detail/anysolar-ltd/SM262K10L/9990466

**Looking for:** Microcontrollers
E-paper display drivers
RTOS/Linux OS development

https://github.com/tock/tock/pull/1857

https://elinux.org/images/d/d4/Optimize_uClinux_for_ARM_Cortex-M4.pdf

PCB Design:
https://alc.sparkfun.com/

https://forum.sparkfun.com/viewtopic.php?f=170&t=51685

https://oshpark.com/

https://raw.githubusercontent.com/TUDSSL/ENGAGE/master/doc-images/hw-overview.png

RT/OSes & Tools of interest:
https://en.wikipedia.org/wiki/Contiki
https://github.com/embox/embox

https://tiny.wiki.kernel.org/use_cases

https://www.coreboot.org/

http://jk.ozlabs.org/projects/petitboot/
https://forum.odroid.com/viewtopic.php?t=33873

https://linuxgazette.net/issue01to08/linuxita_mar96.html 

http://lfs.mirror.fileplanet.com/

https://lwn.net/Kernel/LDD3/

https://bootlin.com/pub/conferences/2013/elc/arm-soc-checklist/arm-soc-checklist.pdf

https://bootlin.com/pub/conferences/2017/jdll/opdenacker-embedded-linux-in-less-than-4mb-of-ram/opdenacker-embedded-linux-in-less-than-4mb-of-ram.pdf


https://www.elinux.org/images/6/67/Linux_In_a_Lightbulb-Where_are_we_on_tinification-ELCE2015.pdf

https://tiny.wiki.kernel.org/

https://elinux.org/Kernel_Size_Reduction_Work

https://www.elinux.org/images/9/90/Linux_for_Microcontrollers-_From_Marginal_to_Mainstream.pdf

https://electronics.stackexchange.com/questions/27594/what-operating-systems-have-been-ported-to-cortex-m3

Window Managers: 
https://github.com/mackstann/tinywm (0.2MB RAM)
https://unauthorised.org/dhog/9wm.html 
https://en.wikipedia.org/wiki/Twm

**Items:** Microcontrollers, e-paper display (no minimum resolution, but should be capable of displaying terminal)

For a microcontroller, microprocessor, display, external memory/storage, and OS to be considered for this project, it must meet the [Tri-Design approach](/wiki/tri-design-approach.md)

# Collaboration Tools
This repository contains templates for **agendas**, **notes** and a **wiki**.

All meetings occur via video conference. Check the [`agendas/`](./agendas) for the exact date and time of upcoming meetings.

## Discourse

EI-2030 maintains a [Discourse](https://forum.ei2030.org/) forum and has a [Working Groups](https://forum.ei2030.org/c/working-groups/26) section. Each working group, upon approval, will have a topic in Discourse to post updates on the progress made and a channel created in Discourse.

## Discord

EI-2030 maintains a [Discord](https://discord.com/invite/nnxKnxh) for communication and collaboration, which is open for anyone to join. Once you join [Discord](https://discord.com/invite/nnxKnxh), you can participate in any public channels.

## Calendars

TBD

# Participation guidelines

Meetings with many participants, especially over video, can easily get hard to
follow or run off course. When we talk about issues we care about, it's easy to
get into heated debate. In order to respect everyone's time, and arrive to
worthwhile outcomes, consider a few guidelines:

### Participate

Being in the room when decisions are being made is exciting, but meetings with
large groups of people are much more difficult to follow. Only attend if an
agenda item directly concerns you and your work, and you expect to participate.

### Don't talk too much

The biggest distraction with many people on a video call is interruption, and
interruptions are frequent when someone is talking for too long. Only speak up
if you have something important to add to the discussion and be courteous of
others and avoid interruption.

### Volunteer to take notes

The rest of the community follows along with the group's discussion by reading
the meeting notes. Volunteering to take notes is a great service to that
community and a great way to participate if you don't have an agenda item.

### Have an outcome in mind

Know what you and your group wish to accomplish from the meeting and make
that clear to the group to keep discussion focused on what's valuable to your
agenda item. Complex or challenging outcomes might take intermediate goals
across multiple meetings.

### Contribute

Projects succeed when their leaders are active contributors more than passive participants. Follow up on your discussion with pull requests to projects, or planned events.

### Choose your battles

There are many ways to solve a problem and you won't always agree with all of them. Express your views but don't argue about a topic that is not relevant to your goals.

### Champion alternatives

Sometimes you'll disagree with someone but will find it difficult or
impossible to convince them of the problems you see. Instead of spending your
energy fighting, commit to developing an alternative proposal so future
discussion can be about substance.

https://berjon.com/w3c-open-license/

### Block progress as a last resort

This working group is only effective when consensus can be reached, even though
there may be disagreements along the way. You should avoid blocking progress if
possible, otherwise you may be seen as hostile to the group. However, if you
have a serious issue with a proposed agenda item outcome, you must make
it clear.
