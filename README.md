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

"The [cubane](https://en.wikipedia.org/wiki/Cubane) name derives from the cube-shaped geometry of the molecule. Since carbon normally bonds at angles of 109.5 degrees, the forced 90-degree angles of the cube framework introduce a high degree of strain into the molecule—so much so that prior to Eaton’s seminal synthesis, most chemists and theoreticians deemed the very existence of the molecule impossible.

“Not only did Phil synthesize cubane, but he did so by a very creative strategy that used photochemistry to excite the molecule into a cage structure and a ring contracting reaction to attain the desired carbon framework,” said Rawal."

https://news.uchicago.edu/story/philip-eaton-renowned-chemist-and-founder-cubane-1936-2023

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/f9b867b1-b9dd-4683-a409-c18113258db5)

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/b84d93ce-0e6b-4721-8da4-552cd9f8233f)

-----
Influences
-----

I think it's important to not understate my early influences. When I was an undergraduate majoring In Biology, my introductory organic chemistry class had a lecture on synthesis of chemical structures. "“To this day, it’s a landmark. If you look up a textbook on organic synthesis, Eaton’s cubane synthesis will be showcased,” said Prof. Viresh Rawal, Eaton’s colleague and chair of the UChicago Department of Chemistry. “It is often used to demonstrate the power of chemical synthesis and the ingenuity that such molecules inspire.”'

As I reflect on my research interests, I can't help but think of comparing the relatively boring field of chemistry to the hot field of semiconductors (it's obvious who gets all the press).

“Phil said one thing to me that I remember to this day,” said Chuan He, Eaton’s colleague and the John T. Wilson Distinguished Service Professor of Chemistry. “He said: ‘So many people work on natural products; I decided to work on unnatural products.’ I think that captures the essence of the University of Chicago. We strive to work on things that are different, unique or sometimes unpopular.”

Semiconductors are unnatural products, so what difference does it make on which types of electronics are paired together? 

If you browse though all my repositories, you may notice a pattern.

All this time, I've been trying to "pack" efficient components- be it pre-built linux distros such as DietPi into 256MB RAM or hardware (currently in the concept stage) into a box- or you could say a cube. But this cube is a circuit design, for a PCB.

The atoms C (Carbon), N (Nitrogen) represent components. The traditional PCB sees power input on a 2D planar- (not in the literal sense, but figurative). A flat compound is cyclohexene (of [cycloalkenes](https://en.wikipedia.org/wiki/Cycloalkene)). Consider the aromatic double bond the circuit where electricity flows. This is considered the "traditional" PCB. Now, the era of [3D stacked memory](https://ieeexplore.ieee.org/document/4556747) is popular. PCBs have always had layers (2, 4, 6, etc), but power is usually viewed in a 2-dimensional plane (in that it is a given that it is an input, but rarely makes any consideration into the source of that power, and what type of PCB is needed for it to work.

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/27706e69-141a-4d02-a518-36fc38ae4ee0)

from https://github.com/TUDSSL/ENGAGE#system-design-game-boy-emulation-and-system-state-checkpointing

In other words, the design of engineering is capable of thinking in 3D terms when it comes to memory and CPU (e.g. Ryzen 7 [5800X3D](https://www.amd.com/en/products/cpu/amd-ryzen-7-5800x3d)), so why not solar [power](https://e-peas.com/product/aem10941/) integration? Energy harvesting shifts the utility of the design into what can be perceived as having to "work" to generate power, because holding a tablet or phone to collect sunlight would appear to be a "chore" for the consumer. But that is not really a universal belief.

Some manufacturers are "subtly" including solar charging into products again:

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/e6d45003-16cc-4ff4-9342-8b0e6e981e7f)

Most technological development involves some amount of efficiency advancements for it to be marketable. What this project seeks to do, is integrate all of those highly efficient technologies into one "cube." You can call it disruptive, in the same way [cubane](https://en.wikipedia.org/wiki/Cubane) can be considered disruptive.

"The resulting high energy density means a large amount of energy can be stored in a comparably smaller amount of space, an important consideration for applications in fuel storage and energy transport."

By integrating a high efficiency solar DC-DC charger, such as the TI [BQ24074](https://www.adafruit.com/product/4755): "Automatic charging current tracking for high efficiency use of any wattage solar panel"...

...and the most efficient microcontroller in terms of microamp per megahertz (uA/mhz), the Ambiq Apollo4, you have a very compact "box." One that can be shipped. 

Step 1: Design Box

Step 2: ???

Step 3: Ship Box. Profit $$$

Carbon, Meet Nitrogen (or hydrogen, take your pick). I didn't invent this pairing. Countless others before me actually built a working prototype. I'm just explaining the trend. Now a cube requires 10 bonds (plus 8 more for H) (C8H8). To ship this "box", it needs a display. Enter memory in pixel. For it to be ubiquitous, it probably needs a long-range modem, such as LoRa or nB-IoT.

So far that's only 4. But enough for a diagram:

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/533e9896-1697-4729-8128-9ec58e889ac9)

It just so "happens" that ~~Moore's~~ [Koomey's Law](https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/1885_Demonstration_Model.jpg) has progressed to a stage where the amount of power on a small solar panel is enough to power all four of those components. Powering a keyboard, mouse/touchscreen, and/or voice recognition are additional challenges, but the basic circuit has been described.

The bi-directional flow of the electricity in a cubic circuit isn't meant to be taken literally- it would need to follow the standard solar charging circuit designs (or anyother energy harvesting circuit).

If you think this project impossible, then it's like saying cubane is impossible. 

On a side note, the phrase "be there or be [square](https://en.wikipedia.org/wiki/Square_(slang))" originated in the 1940s:

"The sense of square as a derogatory reference to someone conventional or old-fashioned dates to the jazz scene of the 1940s; the first known reference is from 1944. There it applied to someone who failed to appreciate the medium of jazz, or more broadly, someone whose tastes were out of date and out of touch."

So there you have it - cubane is to jazz as flat pcbs are to "being square".

-----

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
