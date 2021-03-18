Low-power-E-Paper-OS Working Group

=====================

**Status:** Approved

**Name:** Low-power E-Paper OS

**Objective:**  The goal of this project is to run an OS on an ultra low-power CPU/MCU that can output terminal or a window manager to an e-paper display.

**Timeline:** 3/14/2021-4/13/2021

**Members:** @scrunch, @alexsotodev open to new members, including after project started.

**Contact:** giovanni.lostumbo@gmail.com

**URL:** https://forum.ei2030.org/t/low-power-e-paper-os/138

https://discord.com/invite/nnxKnxh 

**Hardware:** Redboard Artemis, SAMD51, Dialog 14695, ESP32, STM32, other MCUs/MPUs with can be used, including ones with E-paper already connected, like M5Paper, or LILYGO® TTGO T5.
Looking for: People with experience in:

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

RT/OSes of interest:
https://www.tockos.org/documentation/walkthrough
https://github.com/embox/embox

Window Managers: 
https://github.com/mackstann/tinywm (0.2MB RAM)
https://unauthorised.org/dhog/9wm.html 
https://en.wikipedia.org/wiki/Twm

**Items:** Microcontrollers, e-paper display (no minimum resolution, but should be capable of displaying terminal)

Tri-Design approach

The aim of the Low-power E-Paper is ideally to be able to run on solar panels that can fit on a laptop chassis such as the Pi-Top. Therefore, for each consideration of hardware choice (e.g E-Paper/RLCD,,MCU & Memory) and software (OS), they should, at least in the long term, be chosen only if they can be solar powered using ambient indoor light by meeting three criteria: Power, memory and size.

1. Power refers to the thermal design power of the MCU, SRAM & Display. In Sparkfun Artemis, for example (not limited to the Artemis), the Ambiq Apollo3 uses 6uA/mhz,  and 576uA at 96mhz. Therefore, at 3.3V, the MCU alone uses around 1.9mW and w/SRAM & peripherals around 5mW. A 5 watt solar panel is able to power 5mW with a single 10.5W LED bulb without any outdoor sunlight. https://www.youtube.com/watch?v=txj-0iy4xJw In Epaper, the power consumption for each refresh of a Waveshare display can be as low as 26mW: https://www.waveshare.com/5.83inch-e-Paper.htm Other displays such as SHARP Memory or MIP (Memory-In-Pixel) displays may use an overall lower average consumption for more frequent refreshes: https://www.adafruit.com/product/4694

2. Memory refers to the total SRAM and any storage actvity that the OS uses during normal utilization. In the Sparkfun Artemis Nano (Apollo3), it is 384KB. The solar panel does not require extra power to run an RTOS, therefore an RTOS can be fully solar powered with an indoor light. If wanting to choose a larger OS that requires 2-8MB of RAM, the added or included RAM (such as on the Apollo4) must be low power enough so that the extra power consumption (whether it is 3mA-20mA) can be powered by a single light bulb. Possible considerations include MRAM and FRAM via QSPI/OPI.

3. Size refers to the disk space of the onboard flash and any additional external storage added. The criteria mentioned in #2 also apply. If the external storage medium uses a power consumption exceeding the amount of power that a solar panel on a laptop can produce, then it cannot be chosen to be as the permanent storage device for the solar laptop to be fully ambient-light harvesting. The energy harvested from the solar panel onto an integrated battery such as the Epishine Evaluation Kit from a typical day of exposure to indoor light should equal twice the amount of power consumed by the MCU, RAM, Storage & Display, so that it can be recharged daily along with topping-up the battery via pass-through charging.

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
