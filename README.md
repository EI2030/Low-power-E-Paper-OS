Update 8/10/10 This working group has been inactive for 1+ yr, therefore I have decided to update with some renewed interest. First, the Apollo4 has a revised EVB, the Apollo4 Plus: https://www.top-electronics.com/en/apollo4-blue-plus-hexspi-192mhz-ble-5-1
"The Apollo4 Blue Plus is purpose-built to serve as both an application processor and a coprocessor for battery-powered endpoint devices, including smartwatches, children’s watches, fitness bands, animal trackers, far-field voice remotes, predictive health and maintenance, and the smart home.'

https://www.top-electronicsusa.com/apollo4-192-mhz-cortex-m4f-141-pin-bga-p-18066.html 
"Although not discontinued, this device is no longer recommended for new designs.
Customers should use the AMAP42KP-KBR Apollo4 Plus for improved support and performance."

Porting linux or BSD to a microcontroller would require a lot of effort, yet it seems the path of least resistance when compared to trying to develop a sub 30nm application processor designed for extremely low power consumption (less than 2mW. With the Apollo4 Plus running at 4uA/mhz, that presents a fast enough processor for basic applications while still retaining a low power profile. 

One of the first goals is to select an OS that would be versatile to basic, low-RAM applications. Another step would be to have a bootloader, via buildroot or Yocto development. a third step would be to run the current application only in RAM.

"Its embedded 4.75MB of memory delivers power-efficient display performance by storing images on-chip to avoid exhausting resources by fetching data from external memory.' https://embeddedcomputing.com/technology/iot/wireless-sensor-networks/ambiq-enables-audio-radio-and-graphics-for-always-connected-iot-endpoints

One of the key differences from this project and the Raspberry Pi is that micro-SD loaded OSes like Raspberry Pi OS are extremely slow, and do not compare to the true, baremetal capabilities of even the armv6 in the Raspberry Pi Zero. loading Raspup Buster 8.2.1  or Tinycore linux on a Raspberry Pi 3 on 512 MB RAM is an amazing experience. 

The early Nokia phones had immediate response times when navigating the Symbian OS. The modern operating systems of today adopt an omnibus of kernel modules, that prevent replicating the user experience of earlier phones and desktops. Phones attempt to run at even faster speeds to keep up with the hundreds of processes, yet lag behind the simplified OS of a generation ago.

What would be ideal is to focus efforts on operating systems that feature HMI and userspace applications while retaining the benefits of the RTOS task scheduling. An analogy would be the UDP vs TDP comparison. UDP is a connectionless protocol- it does not require connections to restart after losing a byte to a corrupt transmission packet. Rather than have hundrds of process IDS waiting to be completed, the user could wait for a kernel task to complete, and if not busy, the syscall could complete the user's request. I call it the "use it or lose it" concept. Which the kernel would be programmed to skip a task that would take too long to process. It would be better to have real time notifications of kernel tasks (likea sysmonitor) rather than an hourglass (or no indicator at all) to observe system health- this would significantly benefit microcontrollers that have limited RAM (2-4MB usable).

Another focus is to perhaps limit the amount of POSIX compliance in an OS to further reduce OS size. 

A third focus is compatibility with plug and play screens that do not emit a backlight, to save power and to reduce eyestrain.
A reflective display with a variable refresh rate- 1-30hz, toggled by the user, would be a desirable feature in such a system.

The addition of solar panels is would certainly be a goal, but would need to be implemented at a later stage.

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

For a microcontroller, microprocessor, display, external memory/storage, and OS to be considered for this project, it must meet the Power First-Design approach: [https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/wiki/tri-design-approach.md] (Link reverted to prevent broken links). 
