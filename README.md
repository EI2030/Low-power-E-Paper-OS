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
Looking for: People with experience in:

RAM:
https://www.apmemory.com/products/psram-iot-ram/

https://www.eejournal.com/industry_news/ambiq-and-ap-memory-partner-to-enable-richer-experiences-in-intelligent-endpoints/
"AP Memory solutions offer low signal pin count (6 for QSPI, 11 for OPI), low power (standby from 20µA to 80µA, active from 3mA to 8mA), and high transfer rate options needed to meet the demanding power and space constraints of wearable and other battery-powered smart consumer devices."

One approach is to run linux via external memory, using XiP, of which Apollo3 has 64MB-96MB of aperture:

"The Apollo3 Blue Plus adds two additional MSPI modules (3 total), and increases the external memory execute-in-place (XiP) aperture from 64MB to 96MB (32MB/ MSPI instance). Additionally, internal flash increases from IMB to 2MB, SRAM from 384KB to 768KB (TCM size remains at 64KB) and the GPIO count increases from 50 to 74."
https://www.top-electronics.com/en/apollo3-blue-plus-mcu-768kb-108pin-bga

Solar Power Managers (integrated):
https://www.epishine.com/pr/joint-webinar-with-three-leading-actors scaled up to IXolar sizes: 
https://www.digikey.com/en/products/detail/anysolar-ltd/SM262K10L/9990466

**Looking for:** Microcontrollers
E-paper display drivers
RTOS/Linux OS development

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

https://linuxgazette.net/issue01to08/linuxita_mar96.html 

http://lfs.mirror.fileplanet.com/

https://lwn.net/Kernel/LDD3/

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

### Block progress as a last resort

This working group is only effective when consensus can be reached, even though
there may be disagreements along the way. You should avoid blocking progress if
possible, otherwise you may be seen as hostile to the group. However, if you
have a serious issue with a proposed agenda item outcome, you must make
it clear.
