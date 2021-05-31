Low-power-E-Paper-OS Working Group

=====================

**Name:** Low-power E-Paper OS

**Objective:**  The goal of this project is to run an OS on an ultra low-power CPU/MCU that can output terminal or a window manager to an e-paper display.

**Members:** @scrunch, @alexsotodev open to new members, including after project started.

**Contact:** giovanni.lostumbo@gmail.com

**URL:** https://forum.ei2030.org/t/low-power-e-paper-os/138

https://forum.ei2030.org/t/research-porting-linux-to-ultra-low-power-microcontroller/151

https://alexsoto.dev/static/community-built-eink-laptop-project/slides.pdf (Slides 45-49)

https://ei2030.zulipchat.com/register/

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

Technology that optimizes low-power cpus for both sleep and active modes has a benefit for not only wearables and IoT, but also user interface applications. This avenue (Cortex A series processors, as opposed to Cortex M0 or M4) has rarely been developed for, due to the likely power needs of the most performance-hungry apps.


**Items:** Microcontrollers, e-paper display (no minimum resolution, but should be capable of displaying terminal)

For a microcontroller, microprocessor, display, external memory/storage, and OS to be considered for this project, it must meet the Power First-Design approach](/wiki/power first.md)
