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

Solar Powered Webserver: https://solar.lowtechmagazine.com/2023/06/rebuilding-a-solar-powered-website/ Lowtech Magazine recently benchmarked the website generation times for their solar powered website, and has compared the generation times between Hugo and Pelican:

"The times displayed are the average time of three runs on both the solar server (an A20 processor with two 1 GHz cores and 1 GB of RAM) and a modern laptop (an Intel i7-8650U Processor with four cores at 1.9 GHz and 32 GB of RAM). Generating the Hugo site on the solar server without cached assets is not possible to do in one go because the process either runs out of memory or exceeds the timeout limit of Hugo. In that case, the command has to be run several times in a row. While it seems as if Hugo is slower than Pelican on the laptop, that is likely explained by the Hugo site running both a dithering logic and another compression logic for the images. In Pelican, images are only dithered and originals not recompressed.

Hugo	                                                             Pelican
Solar Server (first run)	-	                                       100 minutes, 47 seconds
Modern Laptop (first run)	13 minutes, 31 seconds	                 12 minutes, 53 seconds
Solar Server (cached)	11 minutes, 57 seconds	                     68 minutes, 47 seconds
Modern Laptop (cached)	46 seconds	                                04 minutes, 57 seconds"

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/61fe538b-bff1-42ea-8166-28335c140c8e)

https://github.com/lowtechmag/solar_v2
https://github.com/lowtechmag/solar (archived)


Recently encountering an actual copy of Paint Shop Pro, I was relieved to find a very simple image image tool that calculates the size of the converted file prior to conversion. For example, a 1MB 24-bit color file could be converted to 16 colors and 50KB, drastically reducing the page loading times for simple content. This can be one of the most convenient tools for generating webpage content, and doesn't require using guesswork in MSPaint or websites that do the conversion for you.

https://en.wikipedia.org/wiki/PaintShop_Pro

I also was able to select 1 bit dithering, which converts 24 bit into monochrone (Black and white), but quite well, along with 16 color. It compressed a 1MB file to 50KB using 16 colors and dithering. 

In this example, it converts a 4.45MB file into a 706KB 1-bit file:

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/f8e085ec-c1e4-4aea-85c7-6b9f34111abd)

![20110725_Castello_Sforzesco_Milan_5557](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/15805cbf-2a17-466c-a287-6086c3fb296c)

Original: https://en.wikipedia.org/wiki/Castello_Sforzesco#/media/File:20110725_Castello_Sforzesco_Milan_5557.jpg

Opting for 4 color, one can achieve a slightly more balanced palette at just 1MB:

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/18e1d010-44cb-4392-8a9e-d26458b830be)

Opting for 16-color, one can compress the file to 2.6MB:

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/28029a15-0c35-4c82-95e0-9dc300861f1a)

Using Optimized Octree, the image can be reduced to 1.7MB (page 65 of user manual)

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/20004778-4de6-4fd1-accf-2d88dde8530f)

![20110725_Castello_Sforzesco_Milan_5557 optimized](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/e6239c57-69b0-4663-80a3-300109270ed8)

While JPEG can compress the file quite a bit more, the quality can appear quite degraded. Nonetheless, I was able to compress the file to just 95KB:

![20110725_Castello_Sforzesco_Milan_5557 100](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/d74b0d5c-0e92-40d5-aef0-4d8a2191d01c)


While there are many other tools and formats that may be able to achieve higher compression rates with far less loss in quality (e.g. webp, APNG), a simple tool like the above can allow file attachments to be sized under the limits of many applications and sites (25MB, 10MB, etc).

Wikipedia's own resized files are better compressed while still maintaining good color and resolution. It can be argued that certain images preserve more information with fewer colors and a higher, uncompressed resolutions (e.g. in cases where outlines are more important than palette such as pencil marks in Paint). However, some files may require special codecs that are not always viewable (e.g. JPEG2000 codec, not applicable here). 

BPG
https://en.wikipedia.org/wiki/Better_Portable_Graphics
http://www.smohanty.org/Publications_Conferences/2015/Mohanty_IEEE-iNIS-2015_BPG-Architecture.pdf
http://www.smohanty.org/Publications_Conferences/2016/Mohanty_ISVLSI-2016_SBPG-Architecture.pdf

AVIF:
https://en.wikipedia.org/wiki/AVIF
https://medium.com/vimeo-engineering-blog/upgrading-images-on-vimeo-620f79da8605

APNG
https://en.wikipedia.org/wiki/APNG


![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/6a174783-0a3f-4b1d-a216-5da26a2c4388)


![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/5409ce4c-b481-4dd7-9642-f1d85ca28e4d)

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/943de570-280a-4e7e-9ddd-a6370e1d4c0d)

Method of Buoying Vessels Over Shoals, 1849: 

https://americanhistory.si.edu/collections/search/object/nmah_213141 (6.3MB) 

https://ids.si.edu/ids/deliveryService?id=NMAH-2008-10155&max=1000

7-Color, Optimized Median Cut, 903KB

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/41bf6fe7-034a-44f7-ad36-ad3c2a89e97d)


![NMAH-2008-10155 (1)](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/b464d2e0-17d2-4726-a7e2-4e89f5ed5d45)

Some e-paper manufacturers such as Waveshare sell 7-color displays, which have a low refresh rate, but allow dithering in a way that can actually create rich colors (600x448 Inky Impression 5.7 by Pimoroni): https://www.youtube.com/watch?v=daO46JaVHOs
https://core-electronics.com.au/guides/raspberry-pi/colour-e-ink-display-raspberry-pi/ 

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/273a1deb-f665-41f6-bccc-067f7cb2b636)

Also https://goodereader.com/blog/e-paper/des-display-electronic-slurry-is-next-generation-e-paper 

While the larger sizes look great on larger monitors, it will not be as portable on smaller screens, especially ones that do not need large previews. Resizing to 25%, shrunk the original file to 63KB, and the dithering was only 3KB less, using 4 color dithering (60KB): Whether it would be less costly to produce displays with fewer colors is unclear, since much of the LED technologies are mature. The power consumption of displays is an avenue that would be far more benefiecial for a low power computer than the number of colors. That said, Many of the monitors prior to the 1990s had at least 256 colors, and were still quite capable.

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/a3650206-122e-4604-9bd0-70e9abe38460)


![NMAH-2008-10155 (4) 25 resize 4 color](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/352273aa-6273-4d21-9fe5-792ee546586f)

Similar to greyscale and black and white film, dithering can look sharper, if only the relevant colors are displayed. While the 24-bit color file is far more balanced in terms of colors and pixel accuracy, it can appear softer and less sharp:

![NMAH-2008-10155 (4) 25](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/2134d663-e3c1-4905-8b5a-830a6753d97f)


![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/075ab45d-6126-43d6-a900-9d96e4a95474)



https://gohugo.io/tools/frontends/

https://gohugo.io/tools/editors/

https://github.com/julianoappelklein/hokus

https://github.com/greghendershott/frog

Saving a webpage often takes far longer than the number of bytes per second as depicted here:

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/becd6d22-e5e9-4f0e-b806-179c65487e71)

https://superuser.com/questions/1745770/saving-webpages-on-chrome-takes-longer-than-expected-and-downloaded-filesize-is
Since most sites have a folder of scripts to download when saving a cached page, the page will download much slower than an advertised ISP's speeds (in the tens/hundreds or Gbps). Having a faster harddrive (such as PCI-e Gen3 or Gen4) will help with the 4KQD1 random write speeds for the small script files it needs to save the page to disk, but a far simpler solution would be for the page to minimize its scripts needed to display, at least for a non-Javascript version. Thus static site generators, or very simplified dynamic site generators can fit the bill far better when designed well. https://github.com/gohugoio/hugo

RAM:
https://www.apmemory.com/products/psram-iot-ram/ (Density is 2MB-32MB in QSPI & OPI)

https://www.eejournal.com/industry_news/ambiq-and-ap-memory-partner-to-enable-richer-experiences-in-intelligent-endpoints/
"AP Memory solutions offer low signal pin count (6 for QSPI, 11 for OPI), low power (standby from 20µA to 80µA, active from 3mA to 8mA), and high transfer rate options needed to meet the demanding power and space constraints of wearable and other battery-powered smart consumer devices."

One approach is to run linux via external memory, using XIP:
https://en.wikipedia.org/wiki/Execute_in_place
https://www.embeddedcomputing.com/technology/storage/execute-in-place-xip-an-external-flash-architecture-ideal-for-the-code-and-performance-requirements-of-edge-iot-and-ai
of which Apollo3 has 64MB-96MB of aperture:


CPU and background:
----
NTV & STV:
---

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
https://fuse.wikichip.org/news/1119/isscc-2018-intels-self-powered-intelligent-iot-edge-mote/

Neuromorphic:
https://www.cnx-software.com/2021/07/16/innatera-neuromorphic-ai-accelerator-for-spiking-neural-networks-snn-enables-sub-mw-ai-inference/
https://arxiv.org/abs/2104.13983

uClinux
https://elinux.org/UClinux_Shared_Library#FDPIC_ELF
https://bootlin.com/doc/legacy/uclinux/uclinux_introduction.pdf

Super-H/J-Core (runs uClinux)
https://j-core.org/
https://en.wikipedia.org/wiki/SuperH#J_Core "
https://j-core.org/ 
https://github.com/CoreSemi/jcore-jx
https://www.coresemi.io/products/overview/cx100-secure-soc
https://www.coresemi.io/products/overview/j32-cpu-core
https://www.youtube.com/watch?v=GHORpXNRJiE
https://j-core.org/talks/ELC-2016.pdf
https://web.eece.maine.edu/~vweaver/papers/iccd09/ll_document.pdf
https://j-core.org/talks/japan-2015.pdf
https://web.eece.maine.edu/~vweaver/papers/iccd09/iccd09_density.pdf
https://lists.j-core.org/pipermail/j-core/

Quark
https://en.wikipedia.org/wiki/Intel_Quark
https://en.wikipedia.org/wiki/Intel_Quark#List_of_processors  "Atlas Peak" Quark SE C1000 
https://elinux.org/images/c/c6/Guedes.pdf
https://ark.intel.com/content/www/us/en/ark/products/91949/intel-quark-se-c1000-microcontroller.html

https://docs.zephyrproject.org/1.14.0/boards/x86/quark_se_c1000_devboard/doc/index.html
http://www.elektronikjk.com/elementy_czynne/IC/INTEL-QUARK-SE-MICROCONTROLLER-C1000.pdf
https://www.anandtech.com/show/13888/intel-discontinues-quark-socs-and-microcontrollers

https://www.electronicsdatasheets.com/datasheet/Intel%20Quark%20SE%20Microcontroller%20C1000%20Evaluation%20Kit.pdf
https://www.intel.com/content/www/us/en/developer/articles/technical/intel-quark-se-microcontroller-c1000-documentation.html
https://cdrdv2.intel.com/v1/dl/getContent/335158
https://cdrdv2.intel.com/v1/dl/getContent/334715
https://cdrdv2.intel.com/v1/dl/getContent/335278

Blackberry OS/RIM/
https://www.gsmarena.com/blackberry_7100x-1013.php
https://www.phonearena.com/phones/BlackBerry-7100g_id1099
https://www.engadget.com/blackberry-os-devices-january-4th-service-shutdown-220421328.html
https://en.wikipedia.org/wiki/BlackBerry_OS#Release_history
https://en.wikipedia.org/wiki/BlackBerry_950#RIM_OS
https://the-gadgeteer.com/2001/02/26/rim_blackberry_950_review/
https://www.youtube.com/watch?v=sObUeJZx_5c
https://www.theglobeandmail.com/technology/youve-come-a-long-way-blackberry/article637388/
https://www.cnbc.com/video/2022/11/19/what-happened-to-blackberry.html

AMD
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

RISC-V history (& ARM developments)
----
https://thechipletter.substack.com/p/risc-v-part-1-origins-and-architecture
https://www.semianalysis.com/p/arm-and-a-leg-arms-quest-to-extract

---

https://theopenroadproject.org/
https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts/blob/master/README.md
"OpenROAD Flow is a full RTL-to-GDS flow built entirely on open-source tools. The project aims for automated, no-human-in-the-loop digital circuit design with 24-hour turnaround time."
https://openroad-flow-scripts.readthedocs.io/en/latest/user/UserGuide.html
"The OpenROAD Project uses three tools to perform automated RTL-to-GDS layout generation:

yosys : Logic Synthesis

OpenROAD App : Floorplanning through Detailed Routing

KLayout : GDS merge, DRC and LVS (public PDKs)"

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

https://www.data-modul.com/en/products/product-catalogue/mip-displays

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

Harvesters (an inexhaustive list):
https://www.sony-semicon.com/en/news/2023/2023090701.html
https://e-peas.com/
https://news.utdallas.edu/science-technology/thermoelectric-generators-2020/
https://www.ti.com/tool/TIDA-00246

Wireless Modems:

https://www.everythingrf.com/news/details/17193-qorvo-introduces-new-cellular-iot-transmit-module-for-nb-iot1-2-and-lte-cat-m1-2-operation
https://www.qorvo.com/products/p/QM55011 (smaller, no datasheet posted yet) 3mmx3mm
https://www.qorvo.com/products/p/QM55001 4mmx4mm
https://www.qorvo.com/products/p/QM55003 4mmx433

https://en.wikipedia.org/wiki/Narrowband_IoT#3GPP_LPWAN_standards

https://www.ted.com/talks/danny_hillis_the_internet_could_crash_we_need_a_plan_b/transcript?language=ur

https://www.lowtechmagazine.com/2015/10/how-to-build-a-low-tech-internet.html


If you're a hedge fund manager like Michael Burry or a billionaire reading this and are considering investing $50 million, please call the CEOs of each company that makes each of these motherboard components to develop a platform power consumption under 12mW (1-3mW for CPU, 3-5 mw for display, and 2mW for wireless) for continuous use: an nB-Iot or Cat M2 modem, a MIPS display, a credit card solar panel, a lithium ion capacitor, a sub-threshold processor, and ask them to build a Raspberry Pi-like board with a display that uses less than 12millwatts of power instead of 12 watts TDP: 
https://hackaday.io/project/177716-the-open-source-autarkic-motherboard
https://www.raspberrypi.com/news/introducing-raspberry-pi-5/ 
You can sell millions anywhere in the world once it is produced and if you're early you could corner the market before you get lots of copy cats.
https://www.theregister.com/2023/09/28/raspberry_pi_5_revealed/

Consider it like building the 1984 Macintosh again. And that Super Bowl commercial? The sledgehammer tossed throught the projector screen? That's the USB cable that this board won't need (optional charging mode). Where we're going, we won't need batteries. https://www.hackster.io/news/where-we-re-going-we-don-t-need-batteries-8e9074457779 (link used mainly for figure of speech, rather than the actual content)

Schottky junctions (1.2eV instead of p-n junctions at 1.1eV)
https://en.wikipedia.org/wiki/Schottky_junction_solar_cell
https://solar.lowtechmagazine.com/2021/10/how-to-build-a-low-tech-solar-panel.html (website powered by a solar panel)
https://lowtechmagazine.com/2021/10/how-to-build-a-low-tech-solar-panel.html (same article as previous link, non-solar powered website alternative)

https://en.wikipedia.org/wiki/Thermionic_emission
"Although vulnerable to higher rates of thermionic emission, manufacturing of Schottky barrier solar cells proves to be cost-effective and industrially scalable.[4]"

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

Slackware 1.1.2 on 3MB RAM (1994) w/ TCP/IP support  running at 40Mhz on a 386SX (Linux kernel 0.99.15)

https://www.youtube.com/watch?v=5DBPuZHWEXc
https://mirrors.slackware.com/slackware/slackware-1.1.2/ mirror  of slackware files.
https://en.wikipedia.org/wiki/Slackware


Also on Linux <1.0: binutils 1.94
https://www.mirrorservice.org/sites/sources.redhat.com/pub/binutils/old-releases/
https://sourceware.org/bugzilla/show_bug.cgi?id=22831

various software packages- old versions from early 90s:https://www.mirrorservice.org/sites/sources.redhat.com/pub/?C=M;O=A

https://mirrors.slackware.com/slackware/slackware-1.01/a1/


https://news.ycombinator.com/item?id=26857669
"Here’s an unpopular opinion:
A language like PostScript would have been a much better foundation for the web than HTML+CSS+JS.'

"	goto11 on April 19, 2021 | root | parent | prev | next [–]

Alan Kay is opposed to the "principle of least power" and instead believes the web should consist of turing-complete "objects" which manage their own rendering.
Basically he wants a web consisting purely of "black box" Java Applets rather than of web pages. I think this vision have failed multiple times for obvious reasons."
https://news.ycombinator.com/item?id=26860831
https://en.wikipedia.org/wiki/WorldWideWeb#Features Native PostScript Support in Browser:
https://twitter.com/kocienda/status/1355344814166876163?s=21
"Ken Kocienda
@kocienda
Web browsers are not operating systems or application development environments. They’re document viewers. The effort to make them into something more than that has been one of the biggest wrong turns in the history of computing.
8:39 PM · Jan 29, 2021"
https://web.archive.org/web/20110106041256/http://www.computer.org/portal/web/computingnow/ic-cailliau
![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/bbfa5319-05d1-486b-b857-54fbaa9cf64d)

https://www.w3.org/People/Berners-Lee/FAQ.html#browser 

https://www.w3.org/History/1991-WWW-NeXT/Implementation/

Symbian OS and Psion's earlier OS
https://en.wikipedia.org/wiki/EPOC_(operating_system) 16 & 32-bit
https://en.wikipedia.org/wiki/EKA2 32-bit

https://raymii.org/s/blog/My_24_year_old_HP_Jornada_can_do_things_your_modern_iPhone_still_cant_do.html

https://en.wikipedia.org/wiki/Jlime

https://github.com/vvaltchev/tilck

https://en.wikipedia.org/wiki/Minix
https://wiki.minix3.org/doku.php?id=developersguide:portingnetbsduserland
https://www.youtube.com/watch?v=86_BkFsb4eI&t=1s
https://groups.google.com/g/alt.os.development/c/9qXsgge4b6w
https://en.wikipedia.org/wiki/A_Commentary_on_the_UNIX_Operating_System

https://github.com/vvaltchev/tilck

https://wiki.osdev.org/Projects

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

http://cowlark.com/2021-10-05-emutos-dana/
https://github.com/davidgiven/emutos/tree/dana
https://emutos.sourceforge.io/
https://www.christenseninstitute.org/wp-content/uploads/2013/04/AlphaSmart.pdf
https://en.wikipedia.org/wiki/Hercules_(emulator)

http://eschatologist.net/blog/?p=314
https://en.wikipedia.org/wiki/Clascal

https://en.wikipedia.org/wiki/Capability-based_security
https://en.wikipedia.org/wiki/CapROS
https://en.wikipedia.org/wiki/Smalltalk

https://www.vitanuova.com/inferno/docs.html
https://dboddie.gitlab.io/inferno-diary/2023-08-22.html
https://github.com/dboddie/inferno-os/tree/apollo3
https://www.youtube.com/watch?v=3d1SHOCCDn0
http://doc.cat-v.org/inferno/4th_edition/limbo_language/limbo

https://drive.google.com/file/d/1CD3CSYefHzrhmKAMiCMr0bcJLKvqwj3r/view

Plan 9 and related Resources

https://en.wikipedia.org/wiki/Plan_9_from_Bell_Labs

"A later retrospective comparison of Plan 9, Sprite and a third contemporary distributed research operating system, Amoeba, found that
the environments they [Amoeba and Sprite] build are tightly coupled within the OS, making communication with external services difficult. Such systems suffer from the radical departure from the UNIX model, which also discourages portability of already existing software to the platform (...). The lack of developers, the very small range of supported hardware and the small, even compared to Plan 9, user base have also significantly slowed the adoption of those systems (...). In retrospect, Plan 9 was the only research distributed OS from that time which managed to attract developers and be used in commercial projects long enough to warrant its survival to this day.

— Mirtchovski, Simmonds and Minnich[62]"


http://wiki.c2.com/?WhatIsNotInPlanNine

https://9p.io/wiki/plan9/what_do_people_like_about_plan_9/index.html

https://www.youtube.com/watch?v=Ltpa2tqjZdk

https://www.youtube.com/watch?v=rTQe3W37RBA (2021 tour of 9legacy & 9front)
http://fqa.9front.org/dash1.emailschaden.pdf
https://fqa.9front.org/appendixl.pdf
http://wiki.c2.com/?NameSpace
http://doc.cat-v.org/bell_labs/structural_regexps/se.pdf
http://sam.cat-v.org/cheatsheet/sam-refcard.pdf
http://doc.cat-v.org/plan_9/4th_edition/papers/sam/

https://boxbase.org/entries/2021/jan/1/plan9-on-epaper/

OpenMoko port of Inferno


https://github.com/Plan9-Archive/inferno-openmoko

https://www.youtube.com/watch?v=dF_-jQc53jw "This is a demonstration of Inferno running on an Android phone. Sandia National Labs has adapted the Inferno operating system to act as a more phone-oriented OS, allowing us to make calls, send and receive SMS, and use the phone data network. For more information, see https://bitbucket.org/floren/inferno/..."  Sep 17, 2011 on 128MB RAM.


https://mobile.slashdot.org/story/11/09/17/2050200/inferno-os-running-on-android-phones

https://en.wikipedia.org/wiki/Inferno_(operating_system)#cite_note-21

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

---
PCB Design:
---


https://en.wikipedia.org/wiki/ATX

https://en.wikipedia.org/wiki/De_facto_standard

https://en.wikipedia.org/wiki/Harmonization_(standards)

"The US Government Office of Management and Budget published CircularA-119[11] instructing its agencies to adopt voluntary consensus standards before relying upon private standards. The circular mandates standard harmonization by eliminating or reducing US agency use of private standards and government standards. The priority for governments to adopt voluntary consensus standards is supported by international standards such as ISO supporting public policy initiatives.[12]"

https://www.whitehouse.gov/wp-content/uploads/2017/11/Circular-119-1.pdf
https://onlinelibrary.wiley.com/doi/10.1111/j.1468-5965.1987.tb00294.x
https://www.sciencedirect.com/science/article/abs/pii/S1386505697001214?via%3Dihub

https://semiengineering.com/knowledge_centers/packaging/advanced-packaging/chiplets/ History

https://en.wikipedia.org/wiki/Network_effect any harmonized or standardized platform needs a network effect for it to be affordable and attractive 

"Open (For Business): Big Tech, Concentrated Power, and the Political Economy of Open AI" https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4543807

[https://semiengineering.com/knowledge_centers/packaging/advanced-packaging/chiplets/](https://semiengineering.com/many-chiplet-challenges-ahead/)

https://www.techradar.com/news/phone-and-communications/mobile-phones/why-our-phones-still-aren-t-powered-by-the-sun-1329646

https://www.techradar.com/features/the-quest-for-the-solar-powered-gaming-console

----
ISA
https://en.wikipedia.org/wiki/SuperH#J_Core
https://lwn.net/Articles/647636/
https://www.coresemi.io/products/overview/j32-cpu-core
-----
https://alc.sparkfun.com/

https://forum.sparkfun.com/viewtopic.php?f=170&t=51685

https://oshpark.com/

http://wiki.mlab.cz/

https://raw.githubusercontent.com/TUDSSL/ENGAGE/master/doc-images/hw-overview.png

RT/OSes & Tools of interest:

https://computerhistory.org/blog/the-lisa-apples-most-influential-failure/ Lisa Source Code released by Apple & Computer History Museum 1/19/2023 (40th Anniv).
https://info.computerhistory.org/apple-lisa-code
https://hbr.org/2012/04/the-real-leadership-lessons-of-steve-jobs
https://blog.adafruit.com/2021/05/05/elk-a-tiny-js-engine-for-embedded-systems-embedded-javascript/
https://coder-mike.com/blog/2022/06/11/microvium-is-very-small/


http://www.primrosebank.net/computers/pda/psion3a/psion3a_software_emulators.htm
http://www.inference.org.uk/mackay/psion/part5.htm

FreeRTOS is one of the common OSes used on Ambiq Micro. The advantage to using FreeRTOS over uClinux is a smaller kernel:
https://www.freertos.org/FreeRTOS_Support_Forum_Archive/November_2016/freertos_Free_RTOS_Memory_Management_59ed41adj.html
The disadvantage is more development time. However, with limited onboard flash & RAM, a microkernel would provide lower power consumption than a larger linux kernel, unless using an older linux kernel such as 2.4, but since there would be security risks with an older kernel, its functionality would be limited to off-line use. See https://doc.slitaz.org/en:guides:pxe#why-use-pxe-the-vnc-example
https://tiny.slitaz.org/index.php Using a uClinux version for Cortex M4 may have advantages, provided there is enough space for individual apps.

https://en.wikipedia.org/wiki/FatFs
https://en.wikipedia.org/wiki/Cramfs
https://github.com/jcmvbkbc/linux-xtensa (runs on 3MB+ of RAM)
https://hackaday.com/2023/08/19/linux-running-on-not-a-lot/
https://www.youtube.com/watch?v=MpjRqMPWrAg

https://en.wikipedia.org/wiki/Contiki
https://github.com/embox/embox

https://github.com/cleverca22/not-os

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

https://en.wikipedia.org/wiki/Graph_database
https://github.com/franzinc
https://franz.com/about/company.history.lhtml

https://neo4j.com/

https://memgraph.com/

https://github.com/gephi/gephi-plugins

https://github.com/jQAssistant/jqassistant

https://github.com/terminusdb/terminusdb

---
The true innovation of the Apple I (1976)
---
https://en.wikipedia.org/wiki/Apple_I

http://www.righto.com/2012/02/apple-didnt-revolutionize-power.html

https://electronics.stackexchange.com/questions/196379/understanding-the-apple-1-power-supply

https://boingboing.net/2012/08/09/kottke.html "The Altairs, the Cromemcos, all of that generation were heavy metal boxes. It was brilliant of Steve to find Rod Holt to make a switching power supply, which was a lightweight power supply with no big heavy transformers, and to put the plastic case on it.

So you could actually take the Apple ][ under your arm and carry it somewhere. We never really advertised that but it was part of the appeal. And Steve never forgot that."

"You can trace the portability aspect into the Macintosh, which had a handle built right into it; that was pretty obvious. Steve also paid a lot of attention to and took a lot of inspiration from Hartmut Esslinger, the founder of Frog Design. The mouse for the Lisa was by Frog Design and they were mocking up Macintosh cases for us in 1982. Then Steve left Apple and Apple lost its way into a profusion of beige boxes.

If you remember the history the next big thing on the landscape was the Macintosh IIcx. That was a highly modular, highly manufacturable computer and that was a landmark. But it wasn't about portability and it wasn't about industrial design, it was about manufacturability. At the same time Compaq was a big success making the PC highly manufacturable and highly modular, and so the Mac IIcx was kind of Apple's answer to that."

Portablility, manufacturability, and now power consumption (with the new possibilities due to to Koomey's Law) remain the three most imporant design considerations. 

1990 "A Bicylcle of the Mind" https://youtu.be/L40B08nWoMk?t=869 "Well, the Macintosh, when it first came out, we called it the computer for the rest of us." -Steve Jobs, with a grin, 1990.

1997 (comparing Mac to a Cessna) https://www.youtube.com/watch?v=QhhFQ-3w5tE&t=0s

https://www.theonion.com/last-american-who-knew-what-the-fuck-he-was-doing-dies-1819573021 (pardon the profanity, not my French)

https://litverse.substack.com/p/steve-jobs-vs-the-haters

from https://www.linkedin.com/pulse/can-silicon-valley-find-its-way-back-michael-s-malone

https://hbr.org/2012/04/the-real-leadership-lessons-of-steve-jobs#:~:text=Jobs%20went%20to%20a%20whiteboard,booting%20up%2028%20seconds%20faster.

https://archive.nytimes.com/www.nytimes.com/books/first/m/malone-loop.html

https://landley.net/history/mirror/gui.html "The Real History of the GUI Mike Tuck"

Interview with John Sculley, ex-CEO of Apple:  https://landley.net/history/mirror/apple2/2008-7351-5085423.html

Steve Jobs bought Pixar from George Lucas for $10 million in 1986 https://landley.net/history/mirror/apple2/lucaspixar.html

https://www.apple2history.org/museum-a-l/ads/

Book: Apple Confidential 2.0: The Definitive History of the World's Most Colorful Company

https://landley.net/history/mirror/index.html

----


"At first, the project was just to allow high school and university students to purchase a single-board computer similar to the Raspberry Pi, which (for many reasons) can cost more than $120 in Brazil." from https://www.linux-magazine.com/Issues/2019/218/maddog-s-Doghouse why $120??

http://mail-index.netbsd.org/port-mips/2022/08/07/msg001222.html

https://www.rhizomatica.org/hermes/

https://www.trade.gov/market-intelligence/brazil-computer-and-telecommunications-import-tariffs

https://ustr.gov/sites/default/files/Brazil_0.pdf "Brazil applies a 60 percent flat import tax on most
manufactured retail goods imported by individuals via mail and express shipment, which go through a
simplified customs clearance procedure called RTS (simplified tax regime). Goods with a value of over
$3,000 cannot be imported using this regime."

https://journals.uic.edu/ojs/index.php/fm/article/view/2186/2062 Ubuntuism, commodification, and the software dialectic, by Mike Chege

----


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
https://www.mwrf.com/technologies/communications/wireless/article/21273819/microwaves-rf-the-lorawan-distance-world-record-now-over-1300-kilometers


https://sourceware.org/pipermail/gas2/1994/thread.html

https://en.wikipedia.org/wiki/Howard_Zinn
https://www.zinnedproject.org/materials/neutral-on-a-moving-train-dvd 
https://www.goodreads.com/work/quotes/878739-you-can-t-be-neutral-on-a-moving-train-a-personal-history-of-our-times 
"“You can’t be neutral on a moving train,” I would tell them. Some were baffled by the metaphor, especially if they took it literally and tried to dissect its meaning. Others immediately saw what I meant: that events are already moving in certain deadly directions, and to be neutral means to accept that.”
― Howard Zinn, You Can't Be Neutral on a Moving Train: A Personal History of Our Times"

What the Fork: A Study of Inefficient and Efficient
Forking Practices in Social Coding 
https://cmustrudel.github.io/papers/fse19forks.pdf
