---
Origins of this Project - to my best recollection (and occasionally updated, as recently done here)
---
I first conceived of this project after visiting and [reviewing](https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/2011%20Maker%20Faire%20%E2%80%93%20Queens%2C%20NYC%20_%20Fujimoto.pdf
) the Maker Faire in 2011, seeing both the Raspberry Pi and a booth with a kit for solar powerable electronics, solar power managers  (similar to Adafruit kits [now sold](https://www.adafruit.com/product/4755)) called [BootStrap Solar](https://www.instructables.com/Assembling-a-BootstrapSolar-Chi-qoo-Solar-Battery-/).

I wrote about it weeks [later](https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/Theoretically%20assembling%20a%20solar%20laptop%20_%20Fujimoto.pdf). 

A year later I [posted](https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/solar-powered%20raspberry%20pi%20with%20fast%20e-ink%20refresh%20display%20-%20Raspberry%20Pi%20Forums.pdf) about it again in [2012](https://forums.raspberrypi.com/viewtopic.php?p=206323#p206323).

I resumed interest in 2020 on the Raspberry Pi [Forums](https://forums.raspberrypi.com/viewtopic.php?p=1753787#p1753787
) after seeing the Solar Gameboy in the [news](https://hypebeast.com/2020/9/battery-free-game-boy-solar-power-northwestern-university): 

This project then migrated across a few informal forum posts (EI2030-defunct, Raspberry Pi Forum), to [Hackaday](https://hackaday.io/project/177716-the-open-source-autarkic-motherboard) in 2021. From there, it has remained, although Github also provides an efficient mechanism for storing and and cloning projects. 

Though technically the concept of a solar powered computer existed as a solar calculator before that, which also influenced my interest, I can't think of any time before 2011 that I had wanted to solar power a device like a small PC, although I had been aware of the [OLPC](https://en.wikipedia.org/wiki/OLPC_XO) since the mid 00s. 

In "A [Conversation](https://dl.acm.org/doi/pdf/10.1145/1331287.1331291) with Mary Lou Jepsen What’s behind that funky green machine?" (11/2007, ACM QUEUE), then CTO Jepsen describes the power consumption:

"It’s pretty hot in much of the developing world, so we’ve designed a laptop that can take extreme heat. Part of that is an artifact of it being so low powered. We don’t need big electrolytic capacitors whose lifetimes halve every 10 degrees hotter you get. We get to use little tiny capacitors because we’ve got so little power to deal with, and that’s quite helpful.

Also, half the kids in the world don’t have electricity at home. Half the kids. Eighty percent of the schools that we’re going into don’t have electricity. So we had to design a laptop that was also the infrastructure. It has mesh networking, which is the last mile, 10 miles, 100-mile Internet solution. The solar repeaters and active antennas that we’ve added into the mix cost about $10 a piece and help to relay the Internet. If one laptop in a village is connected to the Internet, they all are.

Yes, it might be just a trickle, a low-bandwidth connection from the Internet to the laptop, but between the laptops is a high-bandwidth connection through the mesh network. We use 802.11s, which is the standard for mesh. The standard isn’t actually complete, but we will be compatible with it when it’s completed. We’ve had to make it up as we go along, so we’re a little ahead of that. There’s truly so little power in the developing world. If a school is wired, it tends to be on a generator, and there’s one 60-watt light bulb per classroom. Generators make really weird power. Usually what comes out of the wall in most countries is 50 or 60 hertz, or somewhere in between. With generators, the frequency of the AC power can go down to 35 hertz. We therefore had to do really interesting power conditioning on the AC adapter. The laptop itself can take between negative 32 volts to 40 volts, and work well with anything from 11 to 18 volts. You can plug a car battery into it. You can plug a solar panel into it."


-----
History on Marketing for Apple
-----


"Of all the great companies of recent memory, there is only one
that seemed to have no character, but only an attitude, a style, a
collection of mannerisms. It constructed a brilliant simulacrum of
character, in the way a man without empathy or conscience can
pretend to have those traits. But it was never really there--even
though two generations of employees convinced themselves
otherwise. It was only when that character was finally tested did the
essential hollowness of the enterprise finally stand exposed, and the
employees and customers shrieked with betrayal.

This was Apple Computer Inc., and there has never been a
company like it. It was founded by two young men, one a genius
with no allegiance to any institution but his own mind; the other a
protean, inconstant figure who seemed composed of nothing but
charm and a pure will to power. The company they built seemed to
have everything: great technology, superb products, talented
employees, rabidly loyal customers, an arresting vision, even a lock
on the zeitgeist. But, like its founders, it lacked character. And
because of that, from the first minute of the first meeting of Steve
Jobs and Steve Wozniak, a decade before the company's founding,
Apple Computer was set on a path from which it could not escape,
even after those founders were gone. And that path would in time
lead to the company's destruction.

More than any other great company, the seeds of Apple's future
glory and its subsequent humiliation were planted long before the
company ever began. And bend and prune as it might, Apple
Computer could never free itself of its roots.

2.0 SEED

It was Regis McKenna, the Silicon Valley marketing guru, who first
saw the horrible truth: "The mistake everyone makes is assuming
that Apple is a real company. But it is not. It never has been."
He was too much of a businessman (after all, Apple could prove
to be a once and future client) to draw the final inference: "And it
never will be."

Nobody alive knew Apple better than Regis McKenna--at least
nobody who had been affected by the notorious "reality distortion
field" that emanated from Steve Jobs;. After fifteen years of
handling the company, Regis had remained unwarped and
unconverted because no matter how successful Regis McKenna Inc.
had become, and no matter how far it had left the publicity game
behind for the more rarefied climes of marketing and business
development, Regis still remained a PR man at heart. He still upheld
the flack's first law: never, ever believe the hot air you put out about
your client.

Not that it was easy. When you watched your client land on the
cover of Time magazine and knew you got the credit for getting him
there; when you stood in the convention centers and giant
auditoriums and felt the waves of adoration rolling around you; and
when the calls came late at night and you heard Jobs the Seducer
telling you how much he depended upon you, it would have been so
simple to surrender to the undertow, to lose yourself in the Apple
Will.

But every time Regis thought of doing so there would be a
meeting to remind him that Apple was a kind of collective madness.
He would bring in an expert on marketing, or branding, or
organizational theory--anything that might give the company some
order, some strategic planning, some simulation of real business
discipline--and he would watch in dismay as that person was
humiliated, ignored or driven away. As for his own advice--well,
nobody blew off the mighty Regis McKenna. Instead, they'd listen
intently, nodding, foreheads pinched in concentration, even the
seraphic Jobs himself making those unreadable and delicate motions
with his fingers on the tabletop as if he was taking seriously what
Regis was saying ... and then the Apple Corps would leave the room
and never think about Regis's message again.

In the end, after fifteen years advising the company he'd helped to
create, McKenna walked away from Apple Computer. And not just
from Apple, but from PR itself" 

-Excerpt from the 1999 book "Infinite Loop How the World's Most Insanely Great Computer Company Went Insane" by Michael S. Malone

------

https://litverse.substack.com/p/steve-jobs-vs-the-haters

Imagine an open source project, that, uses a unified design until each milestone is complete. Job's logic here could be like the Cathedreal in the Bazaar. The Bazaar houses the Cathedral, but temporarily cannot access the Cathedral.

​
"Certainly all historical experience confirms the truth - that man would not have attained the possible unless time and again he had reached out for the impossible." -Max Weber


Update 8/10/22 This working group has been inactive for 1+ yr, therefore I have decided to update with some renewed interest. First, the Apollo4 has a revised EVB, the Apollo4 Plus: [https://www.top-electronics.com/en/apollo4-blue-plus-192mhz-ble-5-1-bga](https://www.top-electronicsusa.com/ambiq-mf-76.html)
"The Apollo4 Blue Plus is purpose-built to serve as both an application processor and a coprocessor for battery-powered endpoint devices, including smartwatches, children’s watches, fitness bands, animal trackers, far-field voice remotes, predictive health and maintenance, and the smart home.'

[https://www.top-electronicsusa.com/ama4b2kl-kxr-apollo4-blue-lite-bga--p-18127.html
](https://www.top-electronicsusa.com/ama4b2kl-kxr-apollo4-blue-lite-bga--p-18127.html)

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

**Members:** hatonthecat, @alexsotodev open to new members, including after project started.

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

Non-Code contributors welcome:
https://github.com/readme/featured/open-source-non-code-contributions

Some interesting new processor finds:

https://nanopowersemi.com/

https://perceive.io/product/ergo/

https://www.st.com/resource/en/datasheet/stm32u585ai.pdf

Some very early low power microcontrollers that catalogued back in 2011 and forgot about:

https://elinux.org/RaspberryPi_Laptop

https://www.radiolocman.com/news/new.html?di=64911
https://en.wikipedia.org/wiki/EFM32

---
Ambiq Roadmap
----
![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/84264e2a-edab-47a0-8731-054d0bc3d53b) 

Ambiq Update, March 2023 (p.10) 

----
7-27-23
---
A newsletter at Substack has a great piece on the early days of Xerox PARC, called ChipLetter:
https://thechipletter.substack.com/p/chip-letter-links-no-21-xerox-parc Part of it is paywalled, but there is substantial content, including a reference to LA Times writer Michael Hiltzik in his 1999 book, "The Dealers of Lightning". Written just 1 year before the dot com bubble burst, a biography on a company with such unfettered access to frank employee interviews today would be highly unusual, as brands have many more trade secrets to protect in an ultra-competitive market. Nonetheless, the book reads with a much more activist tone than the fluff today in the Wirecutter section of the NYT. https://en.wikipedia.org/wiki/PARC_(company)#The_GUI  
