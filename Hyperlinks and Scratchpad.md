#Notes

This project has a lot of goals, but it can only accomplish a few goals at a time. To better elucidate what this project is, I think it is best to ask oneself, What is a Low-Power OS?

To start, it could be any level of low-power, since power consumption is a relative term. It could refer to 0.5mA consumption, 0.5mA, 5mA, 50mA, 500mA, or 5A. 

Therefore, before it is possible to organize a group around a low power OS, it is best to select a thermal power envelope before embarking. 

I will select 0.5mA for the MCU alone (96mhz@ 4uA/mhz= 384uA)= Turbo Speed  (192mhz) is 768uA.

Finding the available tools and hardware is the first half of the battle. Before starting this project, I did a few Google searches- "solar powered cpu"  by doing this, I was able to unearth a lot of research from early 2011: https://hexus.net/tech/news/cpu/31745-intel-shows-solar-powered-cpu-experiment/ 
https://www.theregister.com/2011/09/16/claremont_near_voltage_processor/
"Near-threshold voltage" (and near-threshold computing) are terms rarely used in the mainstream market. 
The origins of NTV are earlier, from the Phoenix processor: https://news.umich.edu/microchip-sets-low-power-record-with-extreme-sleep-mode/ 

https://web.cse.ohio-state.edu/~teodorescu.1/download/slides/radu_cmu_may2013.pdf

But what if not every person needed an app that uses lots of bandwidth and cpu utilization? See this article for reference: 
http://rhombus-tech.net/whitepapers/ecocomputing_07sep2015/

At least one company in recent news claims to operate an application processor in the NTV range: http://www.micromagic.com/news/eeNewsAnalog_Santoro_Interview.pdf

https://github.com/kragen/dernocua/blob/master/intro.md 

http://canonical.org/~kragen/dernocua/dernocua-020211231.pdf 

The current issue here is that there is not much demand right now. However, as more research and development goes into products that can easily be recharged by solar, the demand to avoid long charging cycles for app-hungry phones will increase. Instead of waiting for an application processor to be released using NTV, it may be more practical to port linux to the Ambiq Apollo4, which uses  Sub-threshold Power Optimized Technology: https://www.electronicdesign.com/technologies/microcontrollers/article/21800524/subthreshold-cortexm4f-design-sips-less-power-than-cortexm3 With the Apollo4 being released Q2 2021, Ambiq has lowered uA/mhz from 30uA/mhz in the Apollo1 to 3uA/mhz in the Apollo4. Furthermore, Sparkfun's Artemis boards which use the Apollo3 running 6uA/mhz, use so little power than I was able to solar power the LED for an Adafruit boost charger, along with the Red and blue power LEDs on the Artemis.

Furthermore, the definition of "high-tech" and "low-tech" is due for a re-examination: https://en.wikipedia.org/wiki/High_tech This subject will be examined more in detail in a future analysis. 

http://www.paperterm.org/notes.html (low bandwidth, low power, pixel perfect ASCII-like text (1 bit per pixel?) interface over SSH and remote clients using low powered microcontrollers. Kind of like SteamLink, but for 2D/TUI interfaces.

RAM:
https://www.apmemory.com/products/psram-iot-ram/ (Density is 2MB-32MB in QSPI & OPI)

https://www.eejournal.com/industry_news/ambiq-and-ap-memory-partner-to-enable-richer-experiences-in-intelligent-endpoints/
"AP Memory solutions offer low signal pin count (6 for QSPI, 11 for OPI), low power (standby from 20µA to 80µA, active from 3mA to 8mA), and high transfer rate options needed to meet the demanding power and space constraints of wearable and other battery-powered smart consumer devices."

One approach is to run linux via external memory, using XIP:
https://en.wikipedia.org/wiki/Execute_in_place
https://www.embeddedcomputing.com/technology/storage/execute-in-place-xip-an-external-flash-architecture-ideal-for-the-code-and-performance-requirements-of-edge-iot-and-ai
of which Apollo3 has 64MB-96MB of aperture:

CPU and background:
https://www.electronicdesign.com/technologies/analog/article/21807652/whats-all-this-subthreshold-stuff-anyhow
https://courses.grainger.illinois.edu/cs598jt/fa2019/reading_list/5a.pdf
https://ieeexplore.ieee.org/document/4586001
http://blaauw.engin.umich.edu/wp-content/uploads/sites/342/2018/02/Mingoo-Seok-The-Phoenix-Processor-A-30pW-Platform-for-Sensor-Applications.pdf
https://www.ee.columbia.edu/~mgseok/pdfs/phoenix_isscc_dac_design_contest.pdf
https://semiengineering.com/dealing-with-sub-threshold-variation/
https://www.eetimes.com/arm-preps-near-threshold-processor-for-iot/#
 https://semiaccurate.com/2012/12/20/intel-explains-claremont-the-near-threshold-solar-pentium/ 
https://www.theregister.com/2012/02/19/intel_isscc_ntv_digital_radio/
https://www.engadget.com/2011-09-15-intel-reveals-claremont-near-threshold-voltage-processor-othe.html 
https://www.anandtech.com/show/13888/intel-discontinues-quark-socs-and-microcontrollers
https://fuse.wikichip.org/news/1119/isscc-2018-intels-self-powered-intelligent-iot-edge-mote/

https://www.cnx-software.com/2021/07/16/innatera-neuromorphic-ai-accelerator-for-spiking-neural-networks-snn-enables-sub-mw-ai-inference/
https://arxiv.org/abs/2104.13983

https://elinux.org/UClinux_Shared_Library#FDPIC_ELF
https://en.wikipedia.org/wiki/Intel_Quark

https://en.wikipedia.org/wiki/Geode_(processor)
https://www.computerworld.com/article/2530500/amd-sees-no-geode-chip-replacement-in-sight.html
"Geode was a nice niche market for them, but we are in a very different environment. You can't split your attention too many ways," he said. Geode doesn't contribute to AMD's bottom line like the mainstream chips.

from https://wiki.laptop.org/go/Gen2_CPU_Ideas :
"Candidate Processors
This section (indeed, the whole page) is all about ideas -- not about deals with chip vendors, plans for products, or anything so concrete. Add your own ideas.

X86
AMD Geode family extensions (SSE1)
Intel "Diamondville" (SSE1, SSE2, SSE3, 64-bit, virtualization, 2 cores, some (2?) threads per core)
VIA Isaiah (SSE1, SSE2, SSE3, 64-bit, virtualization)
EE Times on Intel and AMD system-on-chip progress https://www.eetimes.com/latest-32-bit-risc-architecture-for-automotive-expands-functionality/?articleid=204702686
non-X86
Sun UltraSPARC T2 core. GPL'd hardware module implements 64-bit SPARC instruction set, memory controller, in 1x to 8x cores with up to 8 threads apiece. Designed for servers, we'd spin down the cores, threads and clock rate for low absolute power consumption. (64-bit, virtualization, 8 cores, 8 threads per core)
OpenRISC CPU and other System-on-chip design  https://www.oracle.com/servers/technologies/opensparc-overview.html
LEON SPARC. GPL'd 32bit CPU core https://opencores.org/ https://www.gaisler.com/
Talk to Transmeta, they don't make X86 chips anymore, they license low power technology though. The Crusoe was used extensively in Toshiba Libretto line and let's not forget they did more than most to support Linux by writing a paycheck to Torvalds for years. Who knows what they've got up their sleeves.

Marvel ARM/Xscale All-in-one System-On-Chip: low cost, low power, more reliable, simpler design (USA).
Aday All-in-one System-on-module with Pentium core: low cost (Taiwan).
Culturecom V-Dragon PowerPC 405 based CPU: low cost (Hong Kong).
BLX Godson series MIPS look alike CPU: low cost (China).
Texas Instruments ARM Cortex A8 System-On-Chip: most powerful ARM, HD video and 3D acceleration as well.
Qualcomm Snapdraon ARM
Freescale ARM Cortex
Softcore FPGAs with multicore / multichip architecture and power management ( 4 x Altera cyclone III for cpu + 1 Xilinx spartan 3an for gpu/io with tmds /dvi and lvds output )
Vortex DX / MX - vortex86dx.com, vortex86mx.com"

--------------------------------------------------

"The Apollo3 Blue Plus adds two additional MSPI modules (3 total), and increases the external memory execute-in-place (XiP) aperture from 64MB to 96MB (32MB/ MSPI instance). Additionally, internal flash increases from IMB to 2MB, SRAM from 384KB to 768KB (TCM size remains at 64KB) and the GPIO count increases from 50 to 74."
https://www.top-electronics.com/en/apollo3-blue-plus-mcu-768kb-108pin-bga
MSPI: Dual/Quad/Octal-SPI Master (3x) 48Mhz SDR ISO7816 Master

Apollo4: https://ambiq.com/wp-content/uploads/2020/10/Apollo-MCU-SoC-Selector-Guide.pdf
MSPI: Dual/Quad/Octal-SPI Master (3x) 96Mhz SDR 48Mhz DDR

https://www.cnx-software.com/2020/09/17/ambiq-apollo-4-mcu-3%C2%B5a-mhz/
"Ultra-Low Supply Current
4 μA/MHz executing from MRAM (with cache)
4 μA/MHz executing from SRAM
1.5 μA low power sleep mode with RTC and 8KB SRAM retention"

Displays:

4.4" 640x480 MIP runs at 5.4mW without backlight: http://www.koe.j-display.com/upload/product/TX11D200VM1AAA.pdf
http://www.koe.j-display.com/index.php?option=product&task=showpage&cur=1&id=251
https://github.com/Gbertaz/JDI_MIP_Display


Transflective (non-backlit): https://www.youtube.com/watch?v=L-GJjOucBNY 

Thin Film Diode: https://corporate.epson/en/about/history/milestone-products/2000-11-md19.html
https://twitter.com/zephray_wenting/status/1580022380382285825 
https://en.wikipedia.org/wiki/Thin-film_diode
https://www.amorphyx.com/
https://archive.ph/20120913223847/http://www.mobile-phone-directory.org/Glossary/T/TFD.html
https://download.epson-europe.com/pub/electronics-de/ld/d%20tfd%20brochure.pdf

2.7" runs 180uW at 6.5fps:
https://www.j-display.com/product/pdf/Leaflet/2LL_2.7_rectagular_LPM027M128B.pdf
https://www.j-display.com/english/product/reflective.html 

https://www.j-display.com/english/product/reflective.html

Solar Power Managers (integrated):
https://www.epishine.com/pr/joint-webinar-with-three-leading-actors scaled up to IXolar sizes: 
https://www.digikey.com/en/products/detail/anysolar-ltd/SM262K10L/9990466

Solar calculators & history
https://en.wikipedia.org/wiki/Calculator#:~:text=The%20first%20truly%20pocket%2Dsized,was%20marketed%20early%20in%201971
http://www.vintagecalculators.com/html/busicom_le-120a_-_le-120s.html 
http://www.vintagecalculators.com/html/sharp_el-8026.html
https://www.nationalgeographic.com/science/article/160225-solar-calculator-history-energy-objects 
https://tedium.co/2017/08/09/calculators-fake-solar-charging/ 
https://www.aps.org/publications/apsnews/200904/physicshistory.cfm

https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/Microcontroller%20to%20Application%20Processor%20comparisons.ods

https://www.eejournal.com/article/a-history-of-early-microcontrollers-part-1-calculator-chips-came-first/
https://ethw.org/Oral-History:Gary_Boone

Li-ion capacitors:
https://en.wikipedia.org/wiki/Lithium-ion_capacitor
https://www.mdpi.com/1420-3049/27/10/3119
https://www.sciencedirect.com/science/article/abs/pii/S2468606917302873?via%3Dihub
https://www.farnell.com/datasheets/3816250.pdf
https://www.tindie.com/products/jaspersikken/solar-harvesting-into-lithium-ion-capacitor/
https://hackaday.io/project/178177-solar-harvesting-into-lithium-ion-capacitor/log/203869-leakage-current-of-lithium-ion-capacitors-vs-supercapacitors
https://www.digikey.nl/en/products/detail/eaton-electronics-division/HS1016-3R8306-R/12179237
https://www.digikey.com/en/blog/lithium-ion-capacitors-can-help-you-provide-high-quality-power
"While standard EDLCs typically discharge in about 30 seconds (s), LICs discharge over a few minutes; an important distinction in power quality solutions on the edge."
https://www.youtube.com/watch?v=YwnfT665Ns8
**Looking for:** Microcontrollers
E-paper display drivers

RTOS/Linux OS development:

Symbian OS and Psion's earlier OS
https://en.wikipedia.org/wiki/EPOC_(operating_system) 16 & 32-bit
https://en.wikipedia.org/wiki/EKA2 32-bit

https://github.com/vvaltchev/tilck

https://github.com/hundredrabbits/awesome-uxn
https://100r.co/site/uxn.html
https://playb.it

https://en.wikipedia.org/wiki/BareMetal 
http://returninfinity.com

https://en.wikipedia.org/wiki/Single_address_space_operating_system

https://en.wikipedia.org/wiki/Unikernel
https://github.com/unikraft/unikraft
https://dl.acm.org/doi/pdf/10.1145/3447786.3456248

https://arxiv.org/pdf/2112.06566.pdf
https://github.com/project-flexos

"ClickOS and the Art of Network
Function Virtualization": https://www.usenix.org/system/files/conference/nsdi14/nsdi14-paper-martins.pdf 

Towards Highly Specialized, POSIX-compliant
Software Stacks with Unikraft: Work-in-Progress: https://owl.eu.com/papers/unikraft-emsoft20.pdf


https://www.techrepublic.com/article/how-pcgeos-found-a-5th-life-as-an-open-source-dos-shell/
https://www.osnews.com/story/15223/geos-the-graphical-environment-operating-system/
https://en.wikipedia.org/wiki/GEOS_(16-bit_operating_system)
https://github.com/bluewaysw

https://en.wikipedia.org/wiki/GEOS_(8-bit_operating_system)
https://en.wikipedia.org/wiki/GEOS_(8-bit_operating_system)#cite_note-9
https://github.com/mist64/geos

https://bootlin.com/pub/conferences/2015/captronic/captronic-porting-linux-on-arm.pdf

https://www.youtube.com/watch?v=Sk9TatW9ino

https://en.wikipedia.org/wiki/Embeddable_Linux_Kernel_Subset

https://www.youtube.com/watch?v=eooviN1SdQ8
"ELKS (Embeddable Linux Kernel Subset, a 16-bit no-MMU Linux) on customized Amstrad PC 2086"

https://github.com/AcceleratedLinux/accelerated-linux
https://events19.linuxfoundation.org/wp-content/uploads/2017/12/BoF-Accelerated-Linux-Build-System-Jeff-Shaw-Digi-International.pdf

U-boot https://medium.com/@sdivcom/%D0%BD%D0%B5%D0%BC%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BE-u-boot-%D1%87%D0%B0%D1%81%D1%82%D1%8C-3-%D0%BF%D0%BE%D0%B3%D0%BE%D0%B2%D0%BE%D1%80%D0%B8%D0%BC-%D0%BE-%D0%B0%D1%85%D1%80%D0%B8%D1%82%D0%B5%D0%BA%D1%82%D1%83%D1%80%D0%B5-83b6dfd5d361 translation available via browser
https://github.com/sdivcom-dotcom/my-site

https://james-hui.com/2021/07/09/building-another-small-uboot-xip-linux-for-arm-cortex-m4/

https://en.wikipedia.org/wiki/VxWorks

https://en.wikipedia.org/wiki/NuttX

https://github.com/oasislinux/oasis

http://www.sase.com.ar/2013/files/2013/09/SASE2013-Linux-BobBoys.pdf

https://fctorial.github.io/posts/zircon_standalone.html

https://rebble.io/ https://github.com/pebble-dev/RebbleOS

https://github.com/tock/tock/pull/1857

https://elinux.org/images/d/d4/Optimize_uClinux_for_ARM_Cortex-M4.pdf

PCB Design:
https://semiengineering.com/knowledge_centers/packaging/advanced-packaging/chiplets/ History

[https://semiengineering.com/knowledge_centers/packaging/advanced-packaging/chiplets/](https://semiengineering.com/many-chiplet-challenges-ahead/)



https://alc.sparkfun.com/

https://forum.sparkfun.com/viewtopic.php?f=170&t=51685

https://oshpark.com/

https://raw.githubusercontent.com/TUDSSL/ENGAGE/master/doc-images/hw-overview.png

RT/OSes & Tools of interest:

https://blog.adafruit.com/2021/05/05/elk-a-tiny-js-engine-for-embedded-systems-embedded-javascript/
https://coder-mike.com/blog/2022/06/11/microvium-is-very-small/


http://www.primrosebank.net/computers/pda/psion3a/psion3a_software_emulators.htm
http://www.inference.org.uk/mackay/psion/part5.htm

FreeRTOS is one of the common OSes used on Ambiq Micro. The advantage to using FreeRTOS over uClinux is a smaller kernel:
https://www.freertos.org/FreeRTOS_Support_Forum_Archive/November_2016/freertos_Free_RTOS_Memory_Management_59ed41adj.html
The disadvantage is more development time. However, with limited onboard flash & RAM, a microkernel would provide lower power consumption than a larger linux kernel, unless using an older linux kernel such as 2.4, but since there would be security risks with an older kernel, its functionality would be limited to off-line use. See https://doc.slitaz.org/en:guides:pxe#why-use-pxe-the-vnc-example
https://tiny.slitaz.org/index.php Using a uClinux version for Cortex M4 may have advantages, provided there is enough space for individual apps.

https://en.wikipedia.org/wiki/Contiki
https://github.com/embox/embox

https://mudita.com/products/pure/muditaos/
Mudita uses a 600mhz M7, which could be NXP iMXRT1062: 
https://www.sparkfun.com/products/16771

Therefore, porting the open source MuditaOS to Ambiq Micro Apollo4 seems feasible (Cortex M7 to M4)

https://tiny.wiki.kernel.org/use_cases 
https://youtu.be/mysM-V5h9z8?t=1913 (Zephyr & modular linux)

https://www.coreboot.org/

Similar projects/ of interest:

https://www.kickstarter.com/projects/170743596/ripple-the-most-advanced-solar-watch-strap-for-peb
https://www.youtube.com/watch?v=EZDyDHFXKio

https://www.crowdsupply.com/sqfmi/watchy

http://jk.ozlabs.org/projects/petitboot/
https://forum.odroid.com/viewtopic.php?t=33873

https://linuxgazette.net/issue01to08/linuxita_mar96.html 

http://lfs.mirror.fileplanet.com/

https://tldp.org/LDP/tlk/tlk-title.html

https://lwn.net/Kernel/LDD3/ 

https://bootlin.com/pub/conferences/2013/elc/arm-soc-checklist/arm-soc-checklist.pdf

https://bootlin.com/pub/conferences/2017/jdll/opdenacker-embedded-linux-in-less-than-4mb-of-ram/opdenacker-embedded-linux-in-less-than-4mb-of-ram.pdf

https://bootlin.com/doc/legacy/elfs/embedded_lfs.pdf

https://nixos.org/

https://bits.p1x.in/floppinux-an-embedded-linux-on-a-single-floppy/

https://www.elinux.org/images/6/67/Linux_In_a_Lightbulb-Where_are_we_on_tinification-ELCE2015.pdf

https://tiny.wiki.kernel.org/

https://elinux.org/Kernel_Size_Reduction_Work

https://www.elinux.org/images/9/90/Linux_for_Microcontrollers-_From_Marginal_to_Mainstream.pdf

https://electronics.stackexchange.com/questions/27594/what-operating-systems-have-been-ported-to-cortex-m3

Window Managers: 
https://github.com/mackstann/tinywm (0.2MB RAM)
https://unauthorised.org/dhog/9wm.html 
https://en.wikipedia.org/wiki/Twm
https://forums.freebsd.org/threads/window-manager-resident-ram-usage.81914/

Display Driver
https://github.com/8l/fbui
[Linux framebuffer - Wikipedia](https://en.wikipedia.org/wiki/Linux_framebuffer)
https://github.com/directfb2
https://github.com/Bareflank/hypervisor
https://static.sched.com/hosted_files/osseu2022/2c/Trading_Fbdev_for_DRM_no_returns_accepted_Handouts.pdf
https://www.x.org/releases/X11R7.6/doc/man/man4/fbdev.4.xhtml
https://github.com/TheNeuronProject/ef.qt

DOS + GUISs

https://github.com/Microsoft/MS-DOS (fully open source on Github since 2018)
https://web.archive.org/web/20170506152047/http://www.patersontech.com/dos/byte%E2%80%93inside-look.aspx

http://theguiblog.com/guipedia.php

https://costa.jacobpalm.dk/development.html
https://github.com/jacobpalm/costa

http://www.mevis-research.de/~ritter/awakeideas/desktop.html
https://news.ycombinator.com/item?id=28803911
https://github.com/mattiasgustavsson/dos-like (not for dos though)

http://setedit.sourceforge.net/
https://os.ghalkes.nl/tilde/
https://github.com/vinibiavatti1/TuiCss
https://en.wikipedia.org/wiki/Turbo_Vision
https://github.com/magiblot/tvision
https://en.wikipedia.org/wiki/Ncurses
http://elmon.sourceforge.net/
http://nmon.sourceforge.net/pmwiki.php
https://github.com/Textualize/textual

https://dl.acm.org/doi/pdf/10.1145/5684.5687
https://en.wikipedia.org/wiki/Wang_Laboratories#Word_processors

History:
https://www.amazon.com/Infinite-Loop-Michael-Malone/dp/0385486847
https://books.google.com/books?id=lzgOduibRJgC&pg=PT27&source=gbs_toc_r&cad=2#v=onepage&q&f=false
https://archive.nytimes.com/www.nytimes.com/books/99/04/04/reviews/990404.04poguet.html
https://innowiki.org/personal-computer-xerox-alto-the-interim-dynabook/

Miscellaneous and unrelated links:

"At first, the project was just to allow high school and university students to purchase a single-board computer similar to the Raspberry Pi, which (for many reasons) can cost more than $120 in Brazil." from https://www.linux-magazine.com/Issues/2019/218/maddog-s-Doghouse why $120??

https://journals.uic.edu/ojs/index.php/fm/article/view/2186/2062 Ubuntuism, commodification, and the software dialectic, by Mike Chege

https://en.wikipedia.org/wiki/Steal_This_Book by Abbie Hoffman

Early GNU ld working set pre-swap http://www.mirrorservice.org/sites/sources.redhat.com/pub/binutils/old-releases/ 
https://sourceware.org/bugzilla/show_bug.cgi?id=22831

https://lateblt.tripod.com/cpudes.htm

https://lateblt.tripod.com/directsb.htm

Wireless projects: https://wirelesschallenge.mozilla.org/#winners

https://www.lantern.works/

https://www.rhizomatica.org/about/
https://www.rhizomatica.org/keeping-it-analog-a-framework-for-opting-out-of-connectivity/
https://developer.servalproject.org/dokuwiki/doku.php
http://www.servalproject.org/
https://en.wikipedia.org/wiki/FreeSWITCH
https://en.wikipedia.org/wiki/Osmocom

https://imeshyou.gotennamesh.com/

http://emergencell.cs.washington.edu/

https://github.com/jilu7883/Off_The_Grid

https://guardianproject.info/code/wind/

https://github.com/kovesdy/portable-cell-initiative

https://othernet.is/

https://commotionwireless.github.io/rave/
https://github.com/commotionwireless/rave

https://www.youtube.com/watch?v=wA_hsSf8uiw
https://www.tindie.com/products/bobricius/armachat-lora-messenger-with-raspberry-pi-pico/
https://unsigned.io/private-messaging-over-lora/
https://hackaday.com/2022/05/25/long-distance-text-communication-with-lora/



https://sourceware.org/pipermail/gas2/1994/thread.html

https://en.wikipedia.org/wiki/Howard_Zinn
https://www.zinnedproject.org/materials/neutral-on-a-moving-train-dvd 
https://www.goodreads.com/work/quotes/878739-you-can-t-be-neutral-on-a-moving-train-a-personal-history-of-our-times 
"“You can’t be neutral on a moving train,” I would tell them. Some were baffled by the metaphor, especially if they took it literally and tried to dissect its meaning. Others immediately saw what I meant: that events are already moving in certain deadly directions, and to be neutral means to accept that.”
― Howard Zinn, You Can't Be Neutral on a Moving Train: A Personal History of Our Times"

What the Fork: A Study of Inefficient and Efficient
Forking Practices in Social Coding 
https://cmustrudel.github.io/papers/fse19forks.pdf
