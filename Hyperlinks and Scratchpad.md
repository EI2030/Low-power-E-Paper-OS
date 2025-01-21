#Notes

This project has a lot of goals, but it can only accomplish a few goals at a time. To better elucidate what this project is, I think it is best to ask oneself, What is a Low-Power OS?

To start, it could be any level of low-power, since power consumption is a relative term. It could refer to 0.5mA consumption, 0.5mA, 5mA, 50mA, 500mA, or 5A. 

Therefore, before it is possible to organize a group around a low power OS, it is best to select a thermal power envelope before embarking. 

I will select 0.5mA for the MCU alone (96mhz@ 4uA/mhz= 384uA)= Turbo Speed  (192mhz) is 768uA.

See also: https://en.wikipedia.org/wiki/3M_computer
https://en.wikipedia.org/wiki/PERQ#/media/File:Spy_text_editor_running_on_a_PERQ_workstation.jpg
https://www.youtube.com/watch?v=92NNyd3m79I
https://vimeo.com/30110130

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

Another aspect of system design is whether a program/OS uses more resources than needed:


http://www.catb.org/jargon/html/H/hog.html

http://www.catb.org/jargon/html/E/elephantine.html

http://www.catb.org/jargon/html/M/monstrosity.html

The current issue here is that there is not much demand right now. However, as more research and development goes into products that can easily be recharged by solar, the demand to avoid long charging cycles for app-hungry phones will increase. Instead of waiting for an application processor to be released using NTV, 
it may be more practical to port linux to the Ambiq Apollo4, which uses  Sub-threshold Power Optimized Technology: 
https://www.electronicdesign.com/technologies/microcontrollers/article/21800524/subthreshold-cortexm4f-design-sips-less-power-than-cortexm3 With the Apollo4 being released Q2 2021, Ambiq has lowered uA/mhz from 30uA/mhz in the Apollo1 to 3uA/mhz in the Apollo4. Furthermore, Sparkfun's Artemis boards which use the
Apollo3 running 6uA/mhz, use so little power than I was able to solar power the LED for an Adafruit boost charger, along with the Red and blue power LEDs on the Artemis.

Furthermore, the definition of "high-tech" and "low-tech" is due for a re-examination: https://en.wikipedia.org/wiki/High_tech This subject will be examined more in detail in a future analysis. 

https://news.asu.edu/20240617-science-and-technology-asu-study-points-origin-cumulative-culture-human-evolution

http://www.paperterm.org/notes.html (low bandwidth, low power, pixel perfect ASCII-like text (1 bit per pixel?) interface over SSH and remote clients using low powered microcontrollers. Kind of like SteamLink, but for 2D/TUI interfaces.

Solar Powered Webserver: https://solar.lowtechmagazine.com/2023/06/rebuilding-a-solar-powered-website/ Lowtech Magazine recently benchmarked the website generation times for their solar powered website, and has compared the generation times between Hugo and Pelican:

"The times displayed are the average time of three runs on both the solar server (an A20 processor with two 1 GHz cores and 1 GB of RAM) and a modern laptop (an Intel i7-8650U Processor with four cores at 1.9 GHz and 32 GB of RAM). Generating the Hugo site on the solar server without cached assets is not 
possible to do in one go because the process either runs out of memory or exceeds the timeout limit of Hugo. In that case,
the command has to be run several times in a row. While it seems as if Hugo is slower than Pelican on the laptop, that is likely explained by the Hugo site running both a dithering logic and another compression logic for the images. In Pelican, images are only dithered and originals not recompressed.

Hugo	                                                             Pelican
Solar Server (first run)	-	                                       100 minutes, 47 seconds
Modern Laptop (first run)	13 minutes, 31 seconds	                 12 minutes, 53 seconds
Solar Server (cached)	11 minutes, 57 seconds	                     68 minutes, 47 seconds
Modern Laptop (cached)	46 seconds	                                04 minutes, 57 seconds"

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/61fe538b-bff1-42ea-8166-28335c140c8e)

https://github.com/lowtechmag/solar_v2
https://github.com/lowtechmag/solar (archived)


Recently encountering an actual copy of Paint Shop Pro, I was relieved to find a very simple image image tool that calculates the size of the converted file prior to conversion. For example, a 1MB 24-bit color file could be converted to 16 colors and 50KB, drastically reducing the page loading times for 
simple content. This can be one of the most convenient tools for generating webpage content, and doesn't require using guesswork in MSPaint or websites that do the conversion for you.

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

Wikipedia's own resized files are better compressed while still maintaining good color and resolution. It can be argued that certain images preserve more information with fewer colors and a higher, uncompressed resolutions (e.g. in cases where outlines are more important than palette such as
pencil marks in Paint). However, some files may require special codecs that are not always viewable (e.g. JPEG2000 codec, not applicable here). 

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/d7302bee-22f0-42a0-a868-2e6e5655b6d5)

Smallest file size for 1 pixel image

BPG
https://en.wikipedia.org/wiki/Better_Portable_Graphics
http://www.smohanty.org/Publications_Conferences/2015/Mohanty_IEEE-iNIS-2015_BPG-Architecture.pdf
http://www.smohanty.org/Publications_Conferences/2016/Mohanty_ISVLSI-2016_SBPG-Architecture.pdf

AVIF:
https://en.wikipedia.org/wiki/AVIF
https://medium.com/vimeo-engineering-blog/upgrading-images-on-vimeo-620f79da8605

APNG
https://en.wikipedia.org/wiki/APNG

JXL
https://en.wikipedia.org/wiki/JPEG_XL
https://shkspr.mobi/blog/wp-content/uploads/2024/01/1.jxl
https://cloudinary.com/blog/jpeg-xl-and-the-pareto-front

QOI:
https://qoiformat.org/
https://shkspr.mobi/blog/wp-content/uploads/2024/01/1.qoi
https://shkspr.mobi/blog/2024/01/whats-the-smallest-file-size-for-a-1-pixel-image/

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

While the larger sizes look great on larger monitors, it will not be as portable on smaller screens, especially ones that do not need large previews. Resizing to 25%, shrunk the original file to 63KB, and the dithering was only 3KB less, using 4 color dithering (60KB): Whether it would be less costly 
to produce displays with fewer colors is unclear, since much of the LED technologies are mature. The power consumption of displays is an avenue that would be far more benefiecial for a low power computer than the number of colors. That said, Many of the monitors prior to the 1990s had at least 256 colors, and were still quite capable.

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
Since most sites have a folder of scripts to download when saving a cached page, the page will download much slower than an advertised ISP's speeds (in the tens/hundreds or Gbps). Having a faster harddrive (such as PCI-e Gen3 or Gen4) will help with the 4KQD1 random write speeds for the small 
script files it needs to save the page to disk, but a far simpler solution would be for the page to minimize its scripts needed to display, at least for a non-Javascript version. Thus static site generators, or very simplified dynamic site generators can fit the bill far better when designed well. https://github.com/gohugoio/hugo

64K demoscene
---
https://www.youtube.com/watch?v=QqHTwtXvYW4

https://www.youtube.com/watch?v=JZ6ZzJeWgpY&t=2s

---

Video Compression
--
https://mlumiste.com/technical/liveportrait-compression/ 22Kb/s

RAM:
---
https://www.micron.com/about/blog/memory/dram/how-dram-changed-the-world

https://raaam-tech.com/technology/
https://www.eenewseurope.com/en/nxp-partners-with-raaam-for-sram-replacement/
https://www.eenewseurope.com/en/raaam-signs-lead-licensee-for-sram-replacement-technology/

https://www.eenewseurope.com/en/imec-asml-show-logic-and-dram-built-with-high-na-euv-lithography/ 

https://www.nature.com/articles/s41586-022-04992-8 "A compute-in-memory chip based on resistive random-access memory" 2022 

https://en.wikipedia.org/wiki/Resistive_random-access_memory 

https://ieeexplore.ieee.org/document/4796677 "Low power and high speed bipolar switching with a thin reactive Ti buffer layer in robust HfO2 based RRAM" 2008

https://arxiv.org/pdf/1605.04897 "Well-Posed Models of Memristive Devices" 2016

https://ieeexplore.ieee.org/document/9439623 "A Comprehensive Oxide-Based ReRAM TCAD Model with Experimental Verification" 2021

https://www.eenewseurope.com/en/efabless-to-offer-weebit-reram-memory-at-130nm/

 https://www.eenewseurope.com/en/fujitsu-takes-nuvoton-reram-to-12mbit/ This article reveals some interesting power consumption numbers: 150uA at 5MHz is great. Seems like a large, quadratic(?) leap from 5 to 10mHz: it's 1mA at double the speed.

https://www.eenewseurope.com/en/reram-sees-high-temperature-qualification-first-22nm-wafers/

https://www.cnx-software.com/2024/06/21/nuvoton-numicro-m2l31-arm-cortex-m23-mcu-embeds-up-to-512kb-high-durability-reram-168kb-sram/

https://direct.nuvoton.com/en/numaker-m2l31ki

https://www.eenewseurope.com/en/surecore-optimises-ai-memory-ip-for-low-power/

https://www.sure-core.com/new-wp/wp-content/uploads/2022/05/PowerMiser.pdf 22 ULL

https://www.sure-core.com/new-wp/wp-content/uploads/2022/05/EverOn.pdf

https://www.eenewseurope.com/en/ultra-low-power-memory-ip-optimised-for-ai/

https://www.eenewseurope.com/en/ceo-interview-paul-wells-of-surecore-on-low-power-memory-and-china/

https://www.eenewseurope.com/en/surecore-takes-sram-below-0-5v-for-the-first-time/

https://semiengineering.com/sram-scaling-issues-and-what-comes-next/

https://www.design-reuse.com/news/55554/itri-tsmc-sot-mram.html
"The SOT-MRAM array chip showcases innovative computing in memory architecture and boasts a power consumption of merely one percent of an STT-MRAM product."

https://www.apmemory.com/products/psram-iot-ram/ (Density is 2MB-32MB in QSPI & OPI)

https://www.eejournal.com/industry_news/ambiq-and-ap-memory-partner-to-enable-richer-experiences-in-intelligent-endpoints/
"AP Memory solutions offer low signal pin count (6 for QSPI, 11 for OPI), low power (standby from 20µA to 80µA, active from 3mA to 8mA), and high transfer rate options needed to meet the demanding power and space constraints of wearable and other battery-powered smart consumer devices."

One approach is to run linux via external memory, using XIP:
https://en.wikipedia.org/wiki/Execute_in_place
https://www.embeddedcomputing.com/technology/storage/execute-in-place-xip-an-external-flash-architecture-ideal-for-the-code-and-performance-requirements-of-edge-iot-and-ai
of which Apollo3 has 64MB-96MB of aperture:

https://en.wikipedia.org/wiki/DDR_SDRAM#History 

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/d84fa78e-09e4-40f1-9d6d-2a030e67f1b8)

Linux 6.1 on 8MB: https://twitter.com/ReimuNotMoe/status/1787146317594321241/photo/1

A Samsung DDR SDRAM 64 Mbit chip

In the late 1980s IBM had built DRAMs using a dual-edge clocking feature and presented their results at the International Solid-State Circuits Convention in 1990.[6][7]

Samsung demonstrated the first DDR memory prototype in 1997,[1] and released the first commercial DDR SDRAM chip (64 Mbit) in June 1998,[8][2][3] followed soon after by Hyundai Electronics (now SK Hynix) the same year.[9] The development of DDR began in 1996, before its specification was
finalized by JEDEC in June 2000 (JESD79).[10] JEDEC has set standards for the data rates of DDR SDRAM, 
divided into two parts. The first specification is for memory chips, and the second is for memory modules. The first retail PC motherboard using DDR SDRAM was released in August 2000.[11]

Larger size:
[https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/SAMSUNG%40DDR-SDRAM%4064MBit%40K4D62323HA-QC60_Stack-DSC03491-DSC03518_-_ZS-DMap.jpg/220px-SAMSUNG%40DDR-SDRAM%4064MBit%40K4D62323HA-QC60_Stack-DSC03491-DSC03518_-_ZS-DMap.jpg 
](https://en.wikipedia.org/wiki/DDR_SDRAM#/media/File:SAMSUNG@DDR-SDRAM@64MBit@K4D62323HA-QC60_Stack-DSC03491-DSC03518_-_ZS-DMap.jpg)

https://koreajoongangdaily.joins.com/2003/01/04/economy/Samsung-Electronics-Superfast-16M-DDR-SGRAMs-available/1869671.html 

"Samsung Electronics Co. now has commercial samples available for the 16M Double Data Rate Synchronous Graphics Random Access Memory (DDR SGRAM) chip, which is receiving attention as a next-generation, super-fast graphics memory device, the company announced on September 16.
The samples are being shipped to makers of dedicated graphics controllers.
According to the company, this product supports graphic images at up to 286Mbps, twice the speed of the regular 16M SGRAM."

https://ieeexplore.ieee.org/document/62132/ 

Abstract:
"A high-speed 16-Mb DRAM chip with on-chip error-correcting code (ECC), which supports either 11/11 or 12/0 RAS/CAS addressing and operates on a 3.3- or 5-V power supply, is described. It can be packaged as a 2-Mb*8, 4-Mb*4, 8-Mb*2, or 16-Mb*1 DRAM, And is capable of operating in fast page mode, 
static column mode, or toggle mode. Speed and flexibility are achieved by a pipeline layout and on-chip SRAMs that buffer entire ECC words. The use of redundant word and bit lines in conjunction with the ECC produces a synergistic fault-tolerance effect.< >
Published in: IEEE Journal of Solid-State Circuits ( Volume: 25, Issue: 5, October 1990)"
Page(s): 1118 - 1128 DOI: 10.1109/4.62132

Using the SGRAM rate, could deliver 35.75Mbps per single 2Mb DDR chip

Maximum frame buffer using least overhead? Perhaps https://en.wikipedia.org/wiki/Linux_framebuffer 

On an STM32F7-Discovery microcontroller: 

"The screen is 480x272, so if we want to use a 4-byte pixel format, it will need about 512KB of RAM. Our chip has 320kB RAM, so we have to use external RAM. On the other hand, we can use the 16 bits per pixel format, so less than 256KB of RAM is required, and therefore we can try to use the internal RAM."

https://alexkalmuk.medium.com/a-little-about-graphics-subsystem-internals-on-microcontrollers-d952cfd0966a 

Who needs 32bit? The [MIP is 8 color](https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/lineup_from_draft_rev3_jdi_gr_mip_reflective_color_lcd_and_standard_products_20180219-3.pdf) (1bit SRAM per pixel)

https://www.adafruit.com/product/4694 Adafruit 2.7" 400x240 SHARP Memory Display Breakout- "The display is 'write only' which means that it only needs 3 pins to send data. However, the downside of a write-only display is that the entire 400x240 bits (13.5 KB) must be buffered by the microcontroller driver. 
That means you cannot use this with an ATmega328 (e.g. Arduino UNO) or ATmega32u4 (Feather 32u4, etc). You must use a high-RAM chip such as ATSAMD21 (Feather M0), Teensy, ESP8266, ESP32, etc. On those chips, this display works great and looks fantastic."

54KB Video RAM could produce quite a large resolution - 1600x960 at 1 bit-write only. Read and write might need double, or more. Add in a couple bytes and could still be less than 2Mb DDR chip.  

AMD's :
https://en.wikichip.org/wiki/amd/infinity_fabric
The DRAM is attached to the DDR4 interface which is attached to the Unified Memory Controller (UMC). There are two Unified Memory Controllers (UMC) for each of the DDR channels which are also directly connected to the SDF. It's worth noting that all SDF components run at the DRAM's MEMCLK frequency. 
For example, a system using DDR4-2133 would have the entire SDF plane operating at 1066 MHz. This is a fundamental design choice made by AMD in order to eliminate clock-domain latency.

CAKE
The workhorse mechanism that interfaces between the SDF and the various SerDes that link both multiple dies together and multiple chips together is the CAKE. The Coherent AMD socKet Extender (CAKE) module encodes local SDF requests onto 128-bit serialized packets each cycle and ships them over any SerDes interface.
Responses are also decoded by the CAKE back to the SDF. As with everything else that is attached to the SDF, the CAKEs operate at DRAM’s MEMCLK frequency in order to eliminate clock-domain crossing latency.

https://escholarship.org/uc/item/99f6q9c9 "A 64 kb Differential Single-Port 12T SRAM Design with a Bit-Interleaving Scheme for LowVoltage Operation in 32 nm SOI CMOS" (2016)

https://escholarship.org/content/qt7vx9n089/qt7vx9n089_noSplash_cfc4ba479d8eb1b6ec25d7c92357bc18.pdf "STATISTICAL MODELING OF SRAMS" 2022

https://escholarship.org/uc/item/9dc0v8g3  (SRAM Design with OpenRAM in SkyWater 130nm)

https://en.wikipedia.org/wiki/Execute_in_place

"Samsung S3C2416X have 64kB embedded SRAM available on the system bus 
 
 Broadcom BCM2835 uses its Level 2 Cache as boot loader RAM before SDRAM is initialized ([128KB](https://en.wikipedia.org/wiki/Raspberry_Pi#Processor))

 US patent 4485457, Richard K. Balaska, Robert L. Hunter, and Scott S. Robinson, "Memory system including RAM and page switchable ROM", issued 1984-11-27, assigned to CBS Inc.
 
 Uebayashi, Masao (2010-04-05). "eXecute-In-Place (XIP) Support for NetBSD" (PDF). BSDCan."

https://en.wikipedia.org/wiki/AXFS

https://web.archive.org/web/20120113041854/http://ols.fedoraproject.org/OLS/Reprints-2008/hulbert-reprint.pdf Introducing the Advanced XIP File System"

https://web.archive.org/web/20100515124729/http://www.academypublisher.com/ojs/index.php/jcp/article/viewFile/03017989/370 "The Enabling of an Execute-In-Place
Architecture to Reduce the Embedded System Memory Footprint and Boot Time" -2008 

https://www.kernel.org/doc/ols/2004/ols2004v1-pages-79-88.pdf "Methods to Improve Bootup Time in Linux" 2004

https://ambiq.com/wp-content/uploads/2023/03/Apollo510-SoC-Product-Brief.pdf

---
Near threshold voltage CPU speeds = RAM speeds
--
---
Can Infinity Fabric be applied to the Low End?
---

"It's worth noting that all SDF components run at the DRAM's MEMCLK frequency."

"As with everything else that is attached to the SDF, the CAKEs operate at DRAM’s MEMCLK frequency in order to eliminate clock-domain crossing latency."

https://en.wikichip.org/wiki/amd/infinity_fabric

"Infinity Fabric (IF) is a proprietary system interconnect architecture that facilitates data and control transmission across all linked components. This architecture is utilized by AMD's recent microarchitectures for both CPU (i.e., Zen) and graphics (e.g., Vega), and any other additional accelerators they might add in the future.
The fabric was first announced and detailed in April 2017 by Mark Papermaster, AMD's SVP and CTO."



Proposed BoW update (low-clock speed variant): https://github.com/opencomputeproject/ODSA-BoW/pull/144/commits/5c268c24003a1e0f73a6a9e7c95952851fbf0b60

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/e4c83507-701e-476c-b3f9-eb1bd873f763)


|         | Mbps            | Mbps/wire     | KHz   |

+:-------:+:---------------:+:-------------:+:-----:+

| BoW-1/64| 16              | 1            | 488 

| BoW-1/32| 32              | 2            | 976    |

+:-------:+:---------------:+:-------------:+:-----:+

|         | Mbps            | Mbps/wire    | MHz    |

| BoW-1/16| 64              | 4            | 1.953  |

| BoW-1/8 | 128             | 8            | 3.906  

Can 16Mb or 64Mb DRAM run at the same speed as a near-threshold processor (50Mhz, etc)?

https://www.vogons.org/viewtopic.php?t=79632&start=20 (not DDR):

"4 x 1MB = 4MB, 45ns, FPM, Simm-30 Memory Modules are now available.

I also managed to beat my 386 overclocking record with 0WS at 51.2MHz."

Early 90s RAM had speeds around 30-50Mhz.

CPU and background:
----
NTV & STV:
---

https://cmosedu.com/cmos1/BSIM4_manual.pdf (3.1-3.2) Channel Charge and
Subthreshold Swing Models

https://nanopowersemi.com/subthreshold-ic-design-a-powerful-way-to-redefine-low-power

https://www.eenewseurope.com/en/epishine-adds-nanopower-to-power-indoor-solar-cell/

https://semiengineering.com/near-threshold-computing-gets-a-boost/

https://www.eenewseurope.com/en/power-first-some-thoughts-on-drowsy-logic-chip-design/

https://www.researchgate.net/publication/282687029_Design_and_performance_analysis_of_ultra_low_power_RISC_processor_using_hybrid_drowsy_logic_in_CMOS_technologies

https://islped.org/2014/files/ISLPED2014_FD_SOI_Philippe_Flatresse_STMicroelectronics.pdf

https://www.st.com/content/st_com/en/about/innovation---technology/FD-SOI.html

https://www.ripublication.com/ijaer10/ijaerv10n2_175.pdf

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

https://old.hotchips.org/wp-content/uploads/hc_archives/hc24/HC24-6-Tech-Scalability/HC24.29.625-IA-23-Wide-Ruhl-Intel_2012_NTV_iA.pdf

https://semiengineering.com/intels-claremont-near-threshold-voltage-ia-core/

https://theiotlearninginitiative.gitbook.io/intelcurie/hardware/processors

https://www.pcworld.com/article/482847/intel_runs_pc_on_cpu_powered_by_solar_cell-2.html

https://nordichardware.se/intel-claremont-consumes-as-little-as-0002-watt/

https://semiengineering.com/return-to-claremont/

https://www.anandtech.com/show/5555/intel-at-isscc-12-more-research-into-near-threshold-voltage

https://happytrees.org/dieshots/Intel_-_Claremont

https://www.xataka.com/componentes/intel-claremont-tener-glados-en-una-patata-no-parece-tan-lejano

https://bit-tech.net/reviews/tech/cpus/intel-solar-powered-cpu/1/ 

"Who knows, maybe one day they can use offshoots of this technology to make digital devices that are entirely powered off of solar energy. Wouldn’t that be cool? If you ever needed more power, you could simply shine more light at your computer." RIP Greg, you were right.
https://www.route-fifty.com/emerging-tech/2011/09/solar-powered-processor-raises-new-possibilities/283172/

https://hothardware.com/reviews/intel-tremont-cpu-microarchitecture-overview 

https://www.silicon.co.uk/workspace/intel-pushes-low-power-limits-with-claremont-chip-40037

https://fuse.wikichip.org/news/1119/isscc-2018-intels-self-powered-intelligent-iot-edge-mote/

https://semiengineering.com/sram-scaling-issues-and-what-comes-next/ 

https://www.movellus.com/product-overview/aeonic-connect/

https://www.inf.pucrs.br/~calazans/graduate/TSESD2/Bibliography/Surveys/2016-IEEED&T_De-etal_NTV-Computing.pdf

https://ieeexplore.ieee.org/document/7479466 Near Threshold Voltage (NTV) Computing: Computing in the Dark Silicon Era, 26 May 2016 

"When the performance need is well below the NTV operating point,
then we should operate at the minimum energy
point and then shut down completely and wake up
when the next workload arrives. When we are simply waiting for the next workload to arrive but do
not have enough time to shut off completely and
wake up on time, we can park in the minimumenergy or NTV operating point, then quickly ramp
up to the desired operating point when we need
to restart computing. For highly parallel, throughput-oriented workloads, we can use multiple units
in parallel operating at the minimum energy point
to deliver the same throughput as a single unit operating at the highest voltage/frequency. This costs us
die area, but allows us to achieve the best energy
efficiency for a target throughput for parallel workloads, limited primarily by the energy consumed by
inter-unit communications." 

Chip Design and Circuit Simulation software
--

https://www.analog.com/en/resources/design-tools-and-calculators/ltspice-simulator.html 

https://www.qorvo.com/design-hub/design-tools/interactive/qspice

https://en.wikipedia.org/wiki/Qorvo#History 

https://www.eenewseurope.com/en/re-writing-spice-for-a-digital-world/ 

https://en.wikipedia.org/wiki/Soft_microprocessor (x86 and other cores)

Neuromorphic:
--
https://www.cnx-software.com/2021/07/16/innatera-neuromorphic-ai-accelerator-for-spiking-neural-networks-snn-enables-sub-mw-ai-inference/
https://arxiv.org/abs/2104.13983

486
--
https://github.com/pc2005cz/TheUltimate486Upgrade/blob/main/main.md (+Coreboot)

ARM7
https://bmchtech.github.io/post/multiply/
https://problemkaputt.de/gbatek.htm

J-Core
---
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
https://linuxgizmos.com/who-killed-the-quark/
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
--

https://en.wikipedia.org/wiki/Transmeta_Efficeon
https://en.wikipedia.org/wiki/Transmeta_Crusoe
https://en.wikipedia.org/wiki/Sony_Vaio_C1_series#3rd_revision
https://web.archive.org/web/20090216221141/http://www.transmeta.com/tech/microip.html
https://www.eetimes.com/microsoft-brings-vista-to-developing-world-pcs/


https://en.wikipedia.org/wiki/List_of_discontinued_x86_instructions#Instructions_specific_to_ALi/Nvidia/DM&P_M6117_MCUs 


"
V.M. Technology VM386SX+ was developed by Tsukuba, Japan-based fabless microprocessor design firm V.M. Technology (VMT), founded by former Intel 4004 and Zilog Z80 microprocessor design engineer Masatoshi Shima, with its primary funding originating from ASCII Corporation. The chip was primarily marketed in East Asia, avoiding the US market deliberately.[28][29] ALi M6117 SoC contains an x86 core derived from VM386SX+."



5-16-2007

"LOS ANGELES  After a year in trials, Microsoft Corp. is fine tuning its
FlexGo initiative for developing world PCs. Partners including Advanced Micro Devices, Infineon, Intel, and Via Technologies are collaborating on new designs focused on a subscription business model through local telephone companies.

The new designs will use Windows Vista and a new security chip from Infineon. Microsoft reported on the outlook of its FlexGo program at the Windows Hardware Engineering Conference here Tuesday (May 15). FlexGo was first launched at WinHEC in 2006.

Microsoft found a subscription model working through telcos was the best approach, in part because telcos have existing relationships with many families who want but cannot afford a PC. In addition, the availability of consumer credit is on the rise in countries where Microsoft is working including Brazil, India, Mexico and Russia.

“We are going forward with both our original pay-as-you-go and subscription business models, but our main focus will be on telcos and a subscription model,” said David Foster, general manager of the program for Microsoft.

The new systems will generally be bought on credit for about $300 and paid off via a regular subscription fees. In lieu of collateral, the system will keep track of the user's account thanks to the Infineon security chip. If the subscription lapses, the system will warn the user and eventually shut down if the subscription is not renewed.


The initial FlexGo PCs were based on a Transmeta Efficeon CPU, Windows XP and BIOS from Phoenix Technologies. A second-generation of PCs in the works for late this year will use a variety of CPUs from Advanced Micro Devices, Intel and Via along with the Infineon chip.

Via has completed a board design, now available as a Gerber file, with variations for AMD Turion, Intel Celeron and Via C7M processors. It was designed to Microsoft's specifications for a basic Vista system.

Intel is preparing its own board called Cash Canyon. It uses a Celeron D processor, Intel 945GZ and ICH7 chip set and 533 MHz DDR2 memory.

The Infineon chip, loosely based on the work of the Trusted Computing Group, will be used on all the designs. The chip runs Microsoft firmware and provides a secure hardware ID, secure key storage, a random number generator and a trusted clock. The clock tracks usage of systems sold on a pay-as-you-go basis.

Foster estimated as many as a million PCs were sold worldwide through telcos last year, though he would not say how many were FlexGo systems. Microsoft hopes to expand the number of cities in which it supports FlexGo programs in 2007 though it is not disclosing sales expectations, he added.

With chip and board partners lined up, Microsoft's next big step is to get systems makers to adopt the designs and take them into developing markets. “Getting OEMs on board is exactly where we are right now,” said John Wilkes, an alliance manager with AMD.

Microsoft has modified the software used on the initial Windows XP systems so that FlexGo can now be more easily loaded and configured by OEMs to meet the needs of various telco customers. The FlexGo software now runs like an application rather than a unique image of a Windows operating system.

“I heard it loud and clear that was unacceptable,” said Martin Hall, lead FlexGo program manager at Microsoft, referring to the OS approach. “It was clear we had to make the FlexGo software much more manufacturable for OEMs,” he added.

FlexGo represents a relatively high-end approach to getting the latest PCs to people who could not otherwise afford a home computer. AMD has a separate Ultra Low Value PC design based on its Geode processor running Windows XP. A consortium of companies including AMD is working on the One Laptop Per Child project which targets a system costing as little as $100."

"Subsequent reverse engineering, published in 2004, clarifies some details of the native VLIW architecture and associated instruction set, and suggests that there are fundamental limitations that preclude porting an operating system such as Linux to it.[48][49]" 

https://www.realworldtech.com/crusoe-exposed/
https://www.realworldtech.com/crusoe-intro/
https://en.wikipedia.org/wiki/Transmeta#cite_note-RealWorldTechnologiesCrusoeExposedI-48

AMD Geode family extensions (SSE1)
Intel "Diamondville" (SSE1, SSE2, SSE3, 64-bit, virtualization, 2 cores, some (2?) threads per core)
VIA Isaiah (SSE1, SSE2, SSE3, 64-bit, virtualization)

https://www.abortretry.fail/p/a-brief-history-of-cyrix

[ Ken Shirriff's deep dive in the 386
](https://www.righto.com/2023/10/intel-386-die-versions.html)
http://www.bitsavers.org/components/intel/_dataBooks/1988_Introduction_to_Intel_Cell-Based_Design.pdf


https://www.righto.com/2024/07/pentium-standard-cells.html 
https://news.ycombinator.com/item?id=40899393
https://vimeo.com/731037615

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

https://www.vortex86.com/

https://en.wikipedia.org/wiki/Vortex86
https://www.reddit.com/r/todayilearned/comments/a23p5i/til_intels_patent_on_the_original_486_cpu_expired/

https://www.allaboutcircuits.com/news/are-designers-still-using-the-vortex86-old-cpu-ces-2018/

https://www.icop.com.tw/article/205 

https://www.cnx-software.com/2024/07/19/radxa-x4-low-cost-credit-card-sized-intel-n100-sbc-raspberry-pi-5-alternative/ 

---
SkyWater ideas
---

https://opencores.org/projects/amber

https://opencores.org/projects/storm_core

https://opencores.org/projects/v586 or even a 386 https://github.com/hatonthecat/linux_distro_tests#386

https://en.wikipedia.org/wiki/ARM_architecture_family#ARM2 

@
https://opensource.googleblog.com/2022/07/SkyWater-and-Google-expand-open-source-program-to-new-90nm-technology.html 

https://www.skywatertechnology.com/rh90-the-next-generation-stateside-strategic-rad-hard-by-process-technology/ ?

https://efabless.com/tinytapeout 

https://store.efabless.com/products/tiny-tapeout-project

https://en.wikipedia.org/wiki/Dynamic_logic_(digital_electronics)#Static_versus_dynamic_logic

"In particular, although many popular CPUs use dynamic logic,[citation needed] only static cores—CPUs designed with fully static technology—are usable in space satellites owing to their higher radiation hardness.[7][better source needed]"

ARM2aS	ARMv2a	ARM250	Integrated MEMC (MMU), graphics and I/O processor. ARMv2a added the SWP and SWPB (swap) instructions	None, MEMC1a		
ARM3	First integrated memory cache	4 KB unified	0.50 DMIPS/MHz 

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/57370646-6bd8-46eb-89b1-a3a3ba545abe)

using DVS+Body Bias Control
![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/6048c8a9-3995-42cf-bf09-de48844b4260)

https://www.micromagic.com/news/icicdt04final.pdf 

https://www.cs.umd.edu/~meesh/cmsc411/website/proj01/arm/history.html

https://websrv.cecs.uci.edu/~papers/mpr/MPR/ARTICLES/061404.pdf "Unlike the ARM610, the ARM250 has been qualified for operation at 3V. The newer chip uses about 21
mW per MHz at 5V, or 250 mW at 12 MHz. When
throttled down to 3V, power consumption goes down to a
miserly 90 mW. Although much of the chip is fully static,
portions of the IOEB are not, limiting the ability to save
power by reducing the clock speed.
This low power consumption is primarily due to the
minimal transistor count. The CPU core requires just
over 29,000 transistors, and the entire ARM250 uses
less than 100,000. The chip is built in a conservative 1.0-
micron CMOS process with two layers of metal. The die
(see Figure 3) is just 58 mm2. The ARM250 uses a 160-
pin Japanese PQFP (PJQFP)."

https://heyrick.eu/assembler/32bit.html

[https://en.wikipedia.org/wiki/Acorn_Archimedes
](https://en.wikipedia.org/wiki/Acorn_Archimedes#A5000_and_A4_laptop )
https://www.nostalgianerd.com/acorn-archimedes-a3010-review/

https://www.flickr.com/photos/acb/4715965538/in/photostream/

https://www.flickr.com/photos/acb/4715963490/in/photostream/

"Just as the processor could be slowed down to save power, so the 12 MHz RAM could be slowed to 3 MHz, with various subsystems also being switched off as appropriate, and with power saving being activated after "more than a second or so" of user inactivity. "

https://en.wikipedia.org/wiki/Static_core
https://www.semanticscholar.org/topic/Static-core/409338

http://www.riscos.com/support/developers/asm/cpu.html
http://www.riscos.com/support/developers/prm/armhw.html

https://www.abortretry.fail/p/mips-for-the-masses
https://everything2.com/title/ARM3

http://ouc.ai/zhenghaiyong/courses/dsd/20122/materials/Brief_History_of_ARM-LeeSmith.pdf

RISC-V history (& ARM developments)
----
https://thechipletter.substack.com/p/risc-v-part-1-origins-and-architecture
https://www.semianalysis.com/p/arm-and-a-leg-arms-quest-to-extract

https://theopenroadproject.org/
https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts/blob/master/README.md
"OpenROAD Flow is a full RTL-to-GDS flow built entirely on open-source tools. The project aims for automated, no-human-in-the-loop digital circuit design with 24-hour turnaround time."
https://openroad-flow-scripts.readthedocs.io/en/latest/user/UserGuide.html
"The OpenROAD Project uses three tools to perform automated RTL-to-GDS layout generation:

yosys : Logic Synthesis

OpenROAD App : Floorplanning through Detailed Routing

KLayout : GDS merge, DRC and LVS (public PDKs)"

https://www.youtube.com/watch?v=Ed8uQYT39dM 

https://efabless.com/

https://www.ihp-solutions.com/services

https://www.andestech.com/en/products-solutions/andescore-processors/riscv-a25/ 
28HPC+	A25 (WITH DSP, FPU), 28HPC+

Frequency (MHz)		1000

Dynamic power (uW/MHz)	20 

https://www.andestech.com/en/products-solutions/andeshape-platforms/ae350-axi-based-platform-pre-integrated-with-n25f-nx25f-a25-ax25/

https://semiengineering.com/risc-v-wants-all-your-cores/

https://hackaday.com/2023/05/18/an-entire-risc-v-operating-system-in-2000-lines/ 

https://github.com/yhzhang0128/egos-2000

--------------------------------------------------

Foundry
--

https://semiwiki.com/events/342309-intel-direct-connect-event/ 

"It was interesting to see Arm’s CEO Rene Haas on stage with Intel’s CEO Pat Gelsinger. Arm was described as Intel’s most important business partner, and it was noted that 80% of parts run at TSMC have Arm cores. In my view this shows how seriously Intel is taking foundry, in the past it was unthinkable for Intel to run Arm IP."

This is analogous to Apple in the 90s  licensing Microsoft Office and offering support for Microsoft products, as the latter supporting iTunes and realizing they could make more business as partners: https://www.youtube.com/watch?v=wvhW8cp15tk

----
ULL
---

https://www.tsmc.com/english/dedicatedFoundry/technology/logic/l_22nm

https://ambiq.com/blog/arm-enables-the-lowest-power-iot-devices-with-new-ambiq-apollo4-soc-on-tsmc-22nm-ulp-and-ull-libraries/

https://ambiq.com/blog/a-painless-upgrade-to-22nm-the-right-cost-with-the-available-ip/

"The Apollo3 Blue Plus adds two additional MSPI modules (3 total), and increases the external memory execute-in-place (XiP) aperture from 64MB to 96MB (32MB/ MSPI instance). Additionally, internal flash increases from IMB to 2MB, SRAM from 384KB to 768KB (TCM size remains at 64KB) and the GPIO count increases from 50 to 74."
https://www.top-electronics.com/en/apollo3-blue-plus-mcu-768kb-108pin-bga
MSPI: Dual/Quad/Octal-SPI Master (3x) 48Mhz SDR ISO7816 Master

Apollo4: https://ambiq.com/wp-content/uploads/2020/10/Apollo-MCU-SoC-Selector-Guide.pdf
MSPI: Dual/Quad/Octal-SPI Master (3x) 96Mhz SDR 48Mhz DDR

https://antmicro.com/blog/2022/08/initial-renode-support-for-ambiq-apollo4-blue/ (open source software development framework)

https://github.com/renode/renode/blob/master/platforms/cpus/ambiq-apollo4.repl

"Testing and developing physical embedded systems is difficult due to poor reproducibility and lack of insight into the current state of a system, especially in multi-node scenarios.

Renode addresses this issue by letting you run unmodified binaries identical to the ones you would normally flash onto their target hardware on a virtual board or system of boards.

One important aspect of the tool is that it simulates not only CPUs but entire SoCs (e.g., heterogeneous multicore SoCs and various peripherals) as well as the wired or wireless connections between them, allowing users to address complex scenarios and test real production software."

https://github.com/renode/renode/tree/master

https://www.cnx-software.com/2020/09/17/ambiq-apollo-4-mcu-3%C2%B5a-mhz/
"Ultra-Low Supply Current
4 μA/MHz executing from MRAM (with cache)
4 μA/MHz executing from SRAM
1.5 μA low power sleep mode with RTC and 8KB SRAM retention"

---
Displays:
----

https://www.extremetech.com/archive/47940-more-than-meets-the-eye (2001 article, goes quite into detail of many forgotten or buried technologies that died in the Active Matrix vs Passive Matrix War of 1997.

4.4" 640x480 MIP runs at 5.4mW without backlight: http://www.koe.j-display.com/upload/product/TX11D200VM1AAA.pdf
http://www.koe.j-display.com/index.php?option=product&task=showpage&cur=1&id=251
https://github.com/Gbertaz/JDI_MIP_Display

https://www.youtube.com/watch?v=I0KTnVChezE 

https://www.adafruit.com/product/4694 ("The display is 'write only' which means that it only needs 3 pins to send data." This product in 6 or 8" would be an excellent netbook if it had read pins as well

https://www.data-modul.com/en/products/distribution/displays/display-technologies/memory-pixel-technology (up to 6")

https://www.azumotech.com/resource-center/news-press-release-auo-azumo/ (3.4" Color reflective LCD 2.0 with Front Light)

https://www.e3displays.com/mlcd-displays/ (MLCD displays for custom order)

http://www.technoblogy.com/show?3YB0 "low-power monochrome 250x122 display based on the ST7302 display driver and available from suppliers such as AliExpress" (would be interesting to see these bezelless and 5x5 to form a larger screen.

https://www.data-modul.com/en/products/product-catalogue/mip-displays

 https://daylightcomputer.com/ https://www.youtube.com/watch?v=ovF3w8neDUw

https://www.modos.tech/

https://www.crowdsupply.com/soldered/inkplate-6-motion

https://www.tomshardware.com/monitors/boe-and-intels-winning-display-reduces-power-consumption-by-65-using-ai-driven-1-to-120-hz-dynamic-refresh (1HZ!)

Transflective (non-backlit): https://www.youtube.com/watch?v=L-GJjOucBNY 

Thin Film Diode: https://corporate.epson/en/about/history/milestone-products/2000-11-md19.html
https://twitter.com/zephray_wenting/status/1580022380382285825 
https://en.wikipedia.org/wiki/Thin-film_diode
https://www.amorphyx.com/
https://archive.ph/20120913223847/http://www.mobile-phone-directory.org/Glossary/T/TFD.html
https://download.epson-europe.com/pub/electronics-de/ld/d%20tfd%20brochure.pdf

https://www.youtube.com/watch?v=psYJGW7u7Sc Nokia 232 (1994)

 https://learn.adafruit.com/nokia-5110-3310-monochrome-lcd?view=all (discontinued)

 https://en.wikipedia.org/wiki/Nokia_101_%281992%29 2 line text 

2.7" runs 180uW at 6.5fps:
https://www.j-display.com/product/pdf/Leaflet/2LL_2.7_rectagular_LPM027M128B.pdf
https://www.j-display.com/english/product/reflective.html 

https://www.theverge.com/23954584/e-ink-color-tablets-ereader "Is E Ink finally ready for prime time?"

https://liliputing.com/zerowriter-ink-is-an-open-source-word-processor-with-an-e-ink-display-and-a-mechanical-keyboard-crowdfunding/

https://www.youtube.com/watch?v=EKLBpOeX97c

https://www.j-display.com/english/product/reflective.html

https://eazeye.com/
https://www.youtube.com/watch?v=m7wlQYMt9Vk

https://www.youtube.com/watch?v=BKm45Az02YE
https://newhavendisplay.com/blog/a-beginners-guide-to-active-matrix-and-passive-matrix/?srsltid=AfmBOopv_b5pOGzlagvE7k6nX9-zOVUjAsJa14VohEcEcrv3YZ9eI2I-
https://en.wikipedia.org/wiki/Passive_matrix_addressing
https://retro.swarm.cz/20170902/1143/ (why passive matrix screens use far fewer transistors)
https://retro.swarm.cz/tag/lcd/
https://en.wikipedia.org/wiki/DSTN
https://en.wikipedia.org/wiki/Game_Boy#Game_Boy_Pocket
https://en.wikipedia.org/wiki/STN_display#FSTN
https://en.wikipedia.org/wiki/High-performance_addressing
https://web.archive.org/web/20110722071900/http://users.utcluj.ro/~baruch/media/siee/lecture/Lecture-IOS07.pdf

https://rdotdisplays.com/articles/passive-matrix 
https://rdotdisplays.com/articles/how-to-drive-displays

https://hackaday.com/2025/01/18/a-pda-from-an-esp32/

Keyboards
--
https://spectrum.ieee.org/touchscreens

i3C
---
https://en.wikipedia.org/wiki/I3C_(bus)
https://www.youtube.com/watch?v=2mNpYOYL7Ss

Maybe there could be a display driver over i3C? 1-bit display wouldn't use much data...
Bitrate	
12.5 Mbit/s (SDR, standard), 25 Mbit/s (DDR), 33 Mbit/s (ternary),
legacy I²C rates
400 Kbits/s (FM),

640x480x 16fps at 1 bit is 4,915,200, or 4.8Mbps,,

a larger screen, or more frames per second could easily run under 12.5Mbit/s
https://www.nxp.com/products/interfaces/ic-spi-i3c-interface-devices:MC_41735

---
Solar Power Managers (integrated):
---

https://www.epishine.com/pr/joint-webinar-with-three-leading-actors scaled up to IXolar sizes: 
https://www.digikey.com/en/products/detail/anysolar-ltd/SM262K10L/9990466
https://www.wsj.com/tech/personal-tech/what-if-you-never-had-to-charge-your-gadgets-again-955ea960
https://www.onio.com/products/onio-zero.html

----
Energy/Solar harvesters
----

https://www.tindie.com/products/jaspersikken/solar-harvesting-into-li-ion-battery/ (AEM10941)

https://e-peas.com/product/aem10941/

https://www.st.com/en/power-management/spv1050.html 

https://www.ti.com/product/BQ25101 (battery charger only)

https://www.adafruit.com/product/4755 (bq24074)

https://www.ti.com/product/BQ25570

https://www.ti.com/product/BQ25185

https://pme.uchicago.edu/news/uchicago-prof-shirley-mengs-laboratory-energy-storage-and-conversion-creates-worlds-first

https://spectrum.ieee.org/after-the-ic-jack-kilbys-solar-misadventure (general history)

---
Multi-Source Harvesters (an inexhaustive list):
---

https://www.sony-semicon.com/en/news/2023/2023090701.html
https://e-peas.com/
https://news.utdallas.edu/science-technology/thermoelectric-generators-2020/
https://www.ti.com/tool/TIDA-00246

https://phys.org/news/2024-11-method-generating-eco-friendly-energy.html#google_vignette

Internet Infrastructure
--

https://brr.fyi/posts/engineering-for-slow-internet

https://www.lowtechmagazine.com/2015/10/how-to-build-a-low-tech-internet.html

----
Wireless Modems:
----

 "[Integrated Silicon Microwave and Millimeterwave Passive Components and Functions](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=aaaeb7cd32ae4ecaca699702f77b890248abbc82)" (2010)

https://www.eenewseurope.com/en/ultra-low-power-bluetooth-core-for-hearables/

https://www.eenewseurope.com/en/lpwa-soc-for-lte-m-nb-iot-commercially-available/ Quectel BG950S-GL LPWA https://www.quectel.com/product/lpwa-bg950s-gl-cat-m1-nb2 https://altair.sony-semicon.com/ "It features cellular connected standby mode (eDRX) connectivity at a power consumption of below 3µA,
and its overall power consumption performance achieves up to 10 times longer battery life compared to previous generations."
https://www.tekmodul.de/wp-content/uploads/2022/02/Quectel_BG950A-GLBG951A-GL_LPWA_Specification_V1.2.pdf (A, not S)
https://www.rcrwireless.com/20240222/internet-of-things-4/power-no-longer-a-concern-sony-hails-revolutionary-lte-m-nb-iot-soc 
https://iotbusinessnews.com/2024/02/22/78879-sony-semiconductor-israel-announces-commercial-availability-of-the-alt1350-lpwa-chipset/
https://www.digikey.com/en/products/detail/quectel/BG950SGL00AA-8N-TB0AA/22155939 

https://reticulum.network/ 
https://github.com/markqvist/Reticulum
https://github.com/markqvist/Reticulum/raw/master/docs/Reticulum%20Manual.pdf 

https://www.eenewseurope.com/en/neocortec-and-mikroe-make-wireless-mesh-networking-simple/

https://neocortec.com/products-2/the-neocortec-nc1000-8-wireless-mesh-network-module/

https://dl.acm.org/doi/10.1145/3628353.3628546

https://www.everythingrf.com/news/details/17193-qorvo-introduces-new-cellular-iot-transmit-module-for-nb-iot1-2-and-lte-cat-m1-2-operation
https://www.qorvo.com/products/p/QM55011 (smaller, no datasheet posted yet) 3mmx3mm
https://www.qorvo.com/products/p/QM55001 4mmx4mm
https://www.qorvo.com/products/p/QM55003 4mmx433

https://en.wikipedia.org/wiki/Narrowband_IoT#3GPP_LPWAN_standards

https://meshtastic.org/ 

https://www.eetimes.eu/murata-adds-wi-fi-halow-to-wireless-module-line-up/ (802.11ah)

https://www.eetimes.eu/open-digital-radio-broadcast-standard-provides-emergency-notifications/

https://www.ted.com/talks/danny_hillis_the_internet_could_crash_we_need_a_plan_b/transcript?language=ur

https://hackaday.com/2023/11/08/2g-or-not-2g-that-is-the-question/

https://atmosic.com/products/

If you're a hedge fund manager like Michael Burry or a billionaire reading this and are considering investing $50 million, please call the CEOs of each company that makes each of these motherboard components to develop a platform power consumption under 12mW (1-3mW for CPU, 3-5 mw for display, 
and 2mW for wireless) for continuous use: an nB-Iot or Cat M2 modem, a MIPS display, a credit card solar panel, a lithium ion capacitor, a sub-threshold processor, and ask them to build a Raspberry Pi-like board with a display that uses less than 12millwatts of power instead of 12 watts TDP: 
https://hackaday.io/project/177716-the-open-source-autarkic-motherboard
https://www.raspberrypi.com/news/introducing-raspberry-pi-5/ 
You can sell millions anywhere in the world once it is produced and if you're early you could corner the market before you get lots of copy cats.
https://www.theregister.com/2023/09/28/raspberry_pi_5_revealed/

Consider it like building the 1984 Macintosh again. And that Super Bowl commercial? The sledgehammer tossed throught the projector screen? That's the USB cable that this board won't need (optional charging mode). Where we're going, we won't need batteries.
https://www.hackster.io/news/where-we-re-going-we-don-t-need-batteries-8e9074457779 (link used mainly for figure of speech, rather than the actual content)

Schottky junctions (1.2eV instead of p-n junctions at 1.1eV)
https://en.wikipedia.org/wiki/Schottky_junction_solar_cell
https://solar.lowtechmagazine.com/2021/10/how-to-build-a-low-tech-solar-panel.html (website powered by a solar panel)
https://lowtechmagazine.com/2021/10/how-to-build-a-low-tech-solar-panel.html (same article as previous link, non-solar powered website alternative)

https://en.wikipedia.org/wiki/Thermionic_emission
"Although vulnerable to higher rates of thermionic emission, manufacturing of Schottky barrier solar cells proves to be cost-effective and industrially scalable.[4]"

----
Solar calculators & history
---
https://en.wikipedia.org/wiki/Calculator#:~:text=The%20first%20truly%20pocket%2Dsized,was%20marketed%20early%20in%201971
http://www.vintagecalculators.com/html/busicom_le-120a_-_le-120s.html 
http://www.vintagecalculators.com/html/sharp_el-8026.html
https://www.nationalgeographic.com/science/article/160225-solar-calculator-history-energy-objects 
https://tedium.co/2017/08/09/calculators-fake-solar-charging/ 
https://www.aps.org/publications/apsnews/200904/physicshistory.cfm

https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/Microcontroller%20to%20Application%20Processor%20comparisons.ods

https://www.eejournal.com/article/a-history-of-early-microcontrollers-part-1-calculator-chips-came-first/
https://ethw.org/Oral-History:Gary_Boone

Computer History
--

https://www.nsa.gov/Press-Room/Press-Releases-Statements/Press-Release-View/Article/3884041/nsa-releases-copy-of-internal-lecture-delivered-by-computing-giant-rear-adm-gra/  (8-26-2024)

https://www.youtube.com/watch?v=si9iqF5uTFk (pat 1)  Capt. Grace Hopper on Future Possibilities: Data, Hardware, Software, and People (Part One, 1982)
https://www.youtube.com/watch?v=AW7ZHpKuqZg (part 2)  Capt. Grace Hopper on Future Possibilities: Data, Hardware, Software, and People (Part Two, 1982)

https://www.geekwire.com/2024/seattles-living-computers-museum-logs-off-for-good-as-paul-allen-estate-will-auction-vintage-items/

https://news.cornell.edu/stories/2019/09/professors-perceptron-paved-way-ai-60-years-too-soon

https://culture.pl/en/article/jacek-karpinski-the-computer-genius-the-communists-couldnt-stand

https://chipsandcheese.com/2024/07/26/zen-5s-2-ahead-branch-predictor-unit-how-30-year-old-idea-allows-for-new-tricks/ 

https://dl.acm.org/doi/pdf/10.1145/237090.237169 "Multiple-block ahead branch predictors" (1996)

----
Li-ion capacitors:
-----
https://en.wikipedia.org/wiki/Lithium-ion_capacitor

https://www.mdpi.com/1420-3049/27/10/3119

https://www.sciencedirect.com/science/article/abs/pii/S2468606917302873?via%3Dihub

https://www.farnell.com/datasheets/3816250.pdf

https://www.tindie.com/products/jaspersikken/solar-harvesting-into-lithium-ion-capacitor/

https://www.sciencedirect.com/science/article/abs/pii/S2352152X19300210 

https://hackaday.io/project/178177-solar-harvesting-into-lithium-ion-capacitor/log/203869-leakage-current-of-lithium-ion-capacitors-vs-supercapacitors

https://www.digikey.nl/en/products/detail/eaton-electronics-division/HS1016-3R8306-R/12179237

https://www.digikey.com/en/blog/lithium-ion-capacitors-can-help-you-provide-high-quality-power

"While standard EDLCs typically discharge in about 30 seconds (s), LICs discharge over a few minutes; an important distinction in power quality solutions on the edge."

https://www.youtube.com/watch?v=YwnfT665Ns8

https://www.digikey.com/en/products/detail/eaton-electronics-division/HSL1020-3R8506-R/12179232 CAP LITH HYBRID 50F 20% 3.8V TH
https://www.eaton.com/content/dam/eaton/products/electronic-components/resources/data-sheet/eaton-supercapacitor-hybrid-cylindrical-cells-data-sheet.pdf

https://www.popularmechanics.com/science/a60732620/capacitor-energy-storage-breakthrough/

https://www.science.org/doi/10.1126/science.adl2835 "High energy density in artificial heterostructures through relaxation time modulation"

https://forums.raspberrypi.com/viewtopic.php?t=317884

https://hackaday.io/project/25107-single-supercapacitor-ups-for-raspberry-pi

https://www.youtube.com/watch?v=LDzxifG7VeA

https://hackaday.com/2020/11/05/a-super-ups-for-the-pi/

https://hackaday.io/project/168286-cheap-o-nas/log/173824-ok-it-works-but-i-can-do-better

Supercapacitors/Microcapacitors
--
https://www.popularmechanics.com/science/a60732620/capacitor-energy-storage-breakthrough/

https://www.eenewseurope.com/en/trench-microcapacitor-for-chip-power/



**Looking for:** Microcontrollers
E-paper display drivers

----
RTOS/Linux/Legacy OS development:
----

https://ignorethecode.net/blog/2009/04/22/oberon/
https://web.archive.org/web/20090416033922/http://stevenf.tumblr.com/post/94591835/warning-a-long-rambly-exploration-of-the-state

https://liam-on-linux.livejournal.com/73983.html
https://liam-on-linux.dreamwidth.org/
https://chrisacorns.computinghistory.org.uk/docs/Mags/PCW/PCW_Aug87_Archimedes.pdf
https://www.riscosopen.org/content/downloads

https://github.com/vocho/openqnx
https://gitlab.com/elahav/qnx-rpi-book/-/blob/master/pdf/qnx_book.pdf
https://news.ycombinator.com/item?id=42079460
https://www.qnx.com/developers/docs/6.4.1/momentics/welcome/whatis.html

https://axio.ms/projects/2024/06/16/MicroMac.html
https://macgui.com/news/article.php?t=492#:~:text=Would%20you%20believe%20that%20there,the%20Mac%20512K%20was%20released

https://github.com/sarah-walker-pcem/pcem/?tab=readme-ov-file#386-based
https://casadevall.pro/articles/2020/06/softlanding-linux-system-1.0.5/

https://www.ventoy.net/en/index.html

https://copy.sh/v86/?profile=elks

https://www.linux-distros.com/category/1993/

https://www.zdnet.com/article/what-is-immutable-linux-heres-why-youd-run-an-immutable-linux-distro/
https://archive.org/details/debian_3.1r8_i386
https://www.broadcom.com/support/knowledgebase/1211161490111/debian-linux-sarge-3.1-kernels-2.4.27-and-2.6.8
"Unlike a compressed image of a conventional file system, a cramfs image can be used as it is, i.e. without first decompressing it. For this reason, some Linux distributions use cramfs for initrd images (Debian 3.1 in particular) and installation images (SUSE Linux in particular), where there are constraints on memory and image size." https://en.wikipedia.org/wiki/Cramfs

https://www.youtube.com/watch?v=CIKHwsSQC4s
Has anyone made this theory: Benefits of uncompressed filesystem is less CPU processing utilization and therefore less power consumption (this video is part of a greater goal- solar powered systems.. :)

https://www.kernel.org/doc/Documentation/filesystems/cramfs.txt

https://docs.kernel.org/filesystems/cramfs.html

https://claroty.com/team82/research/lexmark-printers-firmware-extraction-part-b
https://en.wikipedia.org/wiki/Zlib

https://en.wikipedia.org/wiki/OpenSUSE#Historic_(1994-2005)
"Since the acquisition by Novell in 2003 and with the advent of openSUSE, this has been reversed: starting with version 9.2, an unsupported one-DVD ISO image of SUSE Professional was made available for download. "

Which version of SUSE uses cramFS? 

Maybe somewhere around 6-8.2? 

https://archive.org/details/SuSE8.2LiveEvalI386IntRC2 (I am leaning towards <2.6)

https://distrowatch.com/search.php?ostype=All&category=All&origin=All&basedon=All&notbasedon=None&desktop=All&architecture=All&package=All&rolling=All&isosize=Under+250MB&netinstall=All&language=All&defaultinit=All&status=All#simple (linux distros under 250MB) 

New DSL, released February 2024, <700MB https://www.damnsmalllinux.org/

https://github.com/ivandavidov/minimal?tab=readme-ov-file#related-projects 

https://distrowatch.com/weekly.php?issue=20170327#minimal "I found MLL generally used approximately 10MB to 40MB of RAM when no extra programs or services were running."

https://gist.github.com/ravecat/63a0d49014b6187bebc68cf855d55a83

http://www.prognosticlab.org/pisces/

Slackware 1.1.2 on 3MB RAM (1994) w/ TCP/IP support  running at 40Mhz on a 386SX (Linux kernel 0.99.15)

https://www.youtube.com/watch?v=5DBPuZHWEXc
https://mirrors.slackware.com/slackware/slackware-1.1.2/ mirror  of slackware files.
https://en.wikipedia.org/wiki/Slackware

https://unix.stackexchange.com/questions/127869/a-linux-distribution-under-8mb-ram

http://micheleandreoli.org/public/Software/mulinux/

https://fdlinux.com/about.php

https://www.asashi.net/pages/pitux.html

https://www.giannone.ch/rescue/current/

https://lwn.net/Articles/28940/ https://sourceforge.net/projects/blueflops/

https://en.wikipedia.org/wiki/Tomsrtbt https://www.linux.com/news/little-linux-distribution-could-tomsrtbt/

https://github.com/t2age/RPS/tree/master/64MB-model

Also on Linux <1.0: binutils 1.94
https://www.mirrorservice.org/sites/sources.redhat.com/pub/binutils/old-releases/
https://sourceware.org/bugzilla/show_bug.cgi?id=22831

various software packages- old versions from early 90s:https://www.mirrorservice.org/sites/sources.redhat.com/pub/?C=M;O=A

https://mirrors.slackware.com/slackware/slackware-1.01/a1/

https://krzysztofjankowski.com/floppinux/ 

http://distro.ibiblio.org/baslinux/

uClinux

https://docs.kernel.org/next/admin-guide/mm/nommu-mmap.html

https://www.design-reuse.com/news/17672/uclinux-latticemico32-embedded-soft-core-processor.html

https://github.com/vowstar/k210-linux-nommu 
https://www.dfrobot.com/product-1985.html 

https://hackaday.com/2023/10/11/tiny-linux-on-a-no-mmu-risc-v-microcontroller/

https://github.com/splinedrive/kianRiscV 

https://elinux.org/UClinux_Shared_Library#FDPIC_ELF
https://bootlin.com/doc/legacy/uclinux/uclinux_introduction.pdf


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
--

https://www.abortretry.fail/p/of-psion-and-symbian

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

https://groups.google.com/g/minix3/c/hcPVNNrEWnM

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

https://inf.ethz.ch/news-and-events/spotlights/infk-news-channel/2021/05/from-the-archives-lilith.html

https://www.theregister.com/2024/02/26/starting_over_rebooting_the_os/

https://github.com/btreut/a2
https://gitlab.inf.ethz.ch/felixf/oberon

https://squeak.org/
https://opendylan.org/

https://steve-yegge.blogspot.com/2008/11/ejacs-javascript-interpreter-for-emacs.html

https://newspeaklanguage.org/

https://steve-yegge.blogspot.com/2008/11/ejacs-javascript-interpreter-for-emacs.html

https://pretalx.com/devconf-cz-2024/talk/W3AVCT/ 
https://news.ycombinator.com/item?id=40907933

https://www.vitanuova.com/inferno/docs.html
https://dboddie.gitlab.io/inferno-diary/2023-08-22.html
https://github.com/dboddie/inferno-os/tree/apollo3
https://www.youtube.com/watch?v=3d1SHOCCDn0
http://doc.cat-v.org/inferno/4th_edition/limbo_language/limbo

https://drive.google.com/file/d/1CD3CSYefHzrhmKAMiCMr0bcJLKvqwj3r/view

https://www.youtube.com/watch?v=RkeaQNU8EtA Mac OS X Developer Preview 1 & 2 (1999-2000)

https://hcsimulator.com/ Hypercard sim 

Devuan
--

https://www.devuan.org/
https://en.wikipedia.org/wiki/Devuan
https://git.devuan.org/devuan/amprolla3
https://www.reddit.com/r/linuxquestions/comments/11a3law/is_there_a_good_reason_to_use_devuan/
https://wiki.archlinux.org/title/Systemd/Journal#Journald_in_conjunction_with_syslog
https://fossbytes.com/devuan-beowulf-3-0-0-released-a-gnulinux-debian-without-systemd/
https://www.pcworld.com/article/436680/meet-devuan-the-debian-fork-born-from-a-bitter-systemd-revolt.html
https://news.softpedia.com/news/Fork-Debian-Project-Announces-the-Systemd-less-OS-Devuan-466178.shtml
https://web.archive.org/web/20141203145909/http://www.theregister.co.uk/2014/12/01/ttsystemdtt_row_ends_with_debian_getting_forked/

https://nosystemd.org/

https://distrowatch.com/search.php?ostype=All&category=All&origin=All&basedon=All&notbasedon=None&desktop=All&architecture=All&package=All&rolling=All&isosize=All&netinstall=All&language=All&defaultinit=Not+systemd&status=Active#simple

https://distrowatch.com/table.php?distribution=star
https://sourceforge.net/projects/linnix/
https://en.wikipedia.org/wiki/Peppermint_OS

https://distrowatch.com/table.php?distribution=exe https://exegnulinux.net/

https://web.archive.org/web/20160112142830/https://devuan.org/pics/devuan-ci-graph.png

https://github.com/hatonthecat/linux_distro_tests/blob/main/README.md#devuan-daedalus-50

https://distrowatch.com/search.php?ostype=All&category=All&origin=All&basedon=All&notbasedon=None&desktop=All&architecture=All&package=All&rolling=All&isosize=Under+100MB&netinstall=All&language=All&defaultinit=Not+systemd&status=All#simple (active+inactive distros less than 100MB):

https://distrowatch.com/weekly.php?issue=20170327#minimal
https://distrowatch.com/table.php?distribution=nanolinux

https://distrowatch.com/table.php?distribution=ipcop

https://distrowatch.com/index.php?distribution=4mlinux

http://www.tinycorelinux.net/13.x/x86_64/release/

https://distrowatch.com/table.php?distribution=reactos

https://sourceforge.net/projects/reactos/ 

Raspberry Pi Video Core IV
--

https://en.wikipedia.org/wiki/ThreadX

http://www.ombertech.com/cnk/pitrex/wiki/index.php?wiki=GPU

https://www.embedded.com/bill-lamie-story-of-a-man-and-his-real-time-operating-systems/

https://web.archive.org/web/20220531105341/https://ownyourbits.com/2019/02/02/whats-wrong-with-the-raspberry-pi/

https://github.com/hermanhermitage/videocoreiv


----
Plan 9 and related Resources
----
https://en.wikipedia.org/wiki/Plan_9_from_Bell_Labs

"A later retrospective comparison of Plan 9, Sprite and a third contemporary distributed research operating system, Amoeba, found that
the environments they [Amoeba and Sprite] build are tightly coupled within the OS, making communication with external services difficult. Such systems suffer from the radical departure from the UNIX model, which also discourages portability of already existing software to the platform (...). 
The lack of developers, the very small range of supported hardware and the small, even compared to Plan 9, user base have also significantly slowed the adoption of those systems (...). In retrospect, 
Plan 9 was the only research distributed OS from that time which managed to attract developers and be used in commercial projects long enough to warrant its survival to this day.

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

https://www.youtube.com/watch?v=dF_-jQc53jw "This is a demonstration of Inferno running on an Android phone. Sandia National Labs has adapted the Inferno operating system to act as a more phone-oriented OS, allowing us to make calls, send and receive SMS, and use the phone data network.
For more information, see https://bitbucket.org/floren/inferno/..."  Sep 17, 2011 on 128MB RAM.


https://mobile.slashdot.org/story/11/09/17/2050200/inferno-os-running-on-android-phones

https://en.wikipedia.org/wiki/Inferno_(operating_system)#cite_note-21

---
Other OSes & Modules
---

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

https://github.com/David-SWUSA-RISCOS/YASDOE 
https://asmfun.riscos.fr/index.html

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
PCB & Chip Design:
---

Recommendations and Roadmap for Open-Source EDA in Europe (FOSSi Foundation)
Version: November 19, 2024 - Public Release: https://drive.google.com/file/d/1dVIi6BnwZg78IU1jd8Iq7z0UYfAnwBdW/view

https://broccolimicro.io/ https://github.com/broccolimicro

https://spectrum.ieee.org/avnet-amd-space

https://resources.altium.com/p/open-source-laptop-part-one

https://semiengineering.com/specialization-vs-generalization-in-processors

https://www.comp.nus.edu.sg/~tulika/Hycube_for_ASSCC_2019.pdf

https://semiengineering.com/knowledge_centers/standards-laws/laws/makimotos-wave/ big picture dynamics that explains market development

https://www.extremetech.com/computing/287137-how-makimotos-wave-explains-the-tsunami-of-specialized-ai-processors-headed-for-market

https://semiengineering.com/the-other-side-of-makimotos-wave/ 

https://semiengineering.com/software-defined-hardware-architectures/

https://www.darpa.mil/program/software-defined-hardware

https://sourceforge.net/projects/mmi-pd/ from a Slack thread:

" 3 years ago
TIL that Micro Magic (micromagic.com) SUE EDA tools have been open sourced: https://sourceforge.net/projects/mmi-pd  
This is the tool they used to make a 5 GHz RISC-V.

SourceForgeSourceForge
MMI Software Tools Public Domain Version
Download MMI Software Tools Public Domain Version for free. IC CAD tools, documentation, scripts, and libraries for designing high-performance ICs, including SUE for schematics, MAX for layouts, DPC for datapaths and MCC for megacells. Prebuilt binaries for Linux, Sparc-Solaris, and HP-PA."

3 years ago
"the source release tarball on sourceforge is from 2004
:sob:
1

  3 years ago
At least they have:
"Prebuilt binaries for Linux, Sparc-Solaris, and HP-PA."
I hate having to build on Solaris and HPUX. :zany_face:

  3 years ago
I tried to rebuid , (prebuilt binaries are for 32 bit, my system is 64 bit linux), however the distribution is really old, there are even pre-ANSI C files...so there are lot of edits to be done...

  3 years ago
I looked into it, but I think even pulling out a 2004's vintage 32-bit Linux, this would be very challenging.  There's no documentation on how to build it (just incoherent bits and pieces) and there's a lot of interdependencies. After a few hours it seemed unlikely that the 20+ year old code base
would be valuable enough to merit this pain (and TCL should be wiped from all known universe). (edited) "

https://opencomputeproject.github.io/ODSA-BoW/bow_specification.html

"" In your implementation you have to enable low-frequency operation so you can interoperate with devices that, by the nature of the process node, cannot go to 60 megabit per second. Some things need to stay at low data rates. They can interoperate with these circuits.”"
https://semiengineering.com/is-ucie-really-universal/"

https://semiengineering.com/chiplets-more-standards-needed/ "Analog data is often digitized with a specific bit width. This is based on the signal and application and, in many cases, is not a multiple of 8 bits. Current standards, however, work on the basis of multiples of 8 bits.
Obviously, bit padding can be used to make the data in the protocols conform to the standard, yet such space-filling bits do not contain any information, which means that a large portion of the data transfer rate is wasted. By implication, then, further standards must be created 
for applications in the field of heterogeneous integration, or existing standards must be extended to cover these kinds of specifically analog interfaces."

Sounds like the RISC-ification of data/wire power efficiency? As the instructions in RISC were optimized to send as much data in as fewest cycles possible. Similarly the electrical signals in a PCB may be wasting excess signal padding to transmit relatively small amounts of data without low-bandwidth only wire sizes.

from: https://www.landley.net/writing/mirror/fool/todo/rulemaker000224.htm 

"A man named Seymour Cray came up with the big new idea in the high end. It was called a "RISC" design, which is an acronym for "Reduced Instruction Set Computing." A RISC instruction set is simplified, with each instruction in it taking only one clock cycle to complete. 
The older designs were full of complicated instructions that took many clock cycles, and thus the acronym "CISC" (standing for "Complex Instruction Set Computing") was retroactively invented to describe them.

In a RISC design, the more complicated tasks that took many clock cycles to complete were broken up into smaller pieces, and each individual step the processor did per clock cycle was given its own instruction number. (Since these were basically the steps the chip had to do behind the scenes anyway,
this wasn't necessarily much of a change. The new instruction set was simply more explicit.) In addition, each instruction was made the exact same length, which means that on a 32-bit chip each instruction would be exactly 4 bytes long.

By itself, these changes merely reduced the complexity of decoding variable-length instructions, and allowed the instruction execution circuitry to be streamlined a bit. Not major wins. But this also opened up a whole new avenue for optimization, which is called "pipelining."

Basically, you build two complete sets of the instruction execution circuitry on the same chip. These two copies are called "Processor Cores," or "Pipelines." Since each instruction is the same length, the chip doesn't have to finish decoding the first instruction to see where the second one starts. 
Each clock cycle, the second pipeline can look at the instruction immediately following the one the first CPU core is executing, and if the second instruction doesn't depend on any results of the first, the second core can execute the second instruction
then and there, in the same clock cycle. Under ideal circumstances, the processor can literally execute two instructions each clock cycle. When circumstances aren't ideal, the second pipeline pulls a "wait state," just like the clock-doubled 486 (described yesterday) did when it ran out of prefetched instructions in the cache.

Since the end of the previous paragraph was pure, unadulterated technobabble, I'd like to step back and demonstrate the idea using a portion of a recipe to represent a computer program:

Measure 1 cup flour
Add flour to mixing bowl
Count 2 eggs
Crack eggs into bowl
Mix
If you'll notice, a lot of instructions depend on the results of previous instructions. You can't put the flour in the bowl before you've measured it; you can't crack the eggs before you've counted them; and you can't mix the ingredients before they're both in the bowl. But other pairs of instructions are independent, 
such as adding the flour to the mixing bowl and counting the eggs. If a second set of instruction execution circuitry is looking over the first's shoulder, the flour can be put in the bowl and the proper number of eggs selected at the same time, basically counting as only one step.

It works even better if the program is re-ordered to pair off independent instructions, like so:

Measure 1 cup flour
Count 2 eggs
Add flour to mixing bowl
Crack eggs into bowl
Mix
Now the measuring and counting can be done in one step, and adding both ingredients to the bowl can be done in a second step, followed by mixing. From taking five steps to finish, now the process only takes three. This is a tremendous speed improvement, achieved by rethinking and reorganizing the processor's 
instructions so that more transistors can be thrown at the problem to do more stuff at the same time, in parallel.

Of course, RISC had some downsides. Without the variable instruction length trick central to CISC instruction sets, programs took up much more memory. The chip also required twice as many transistors for two complete processor cores, which meant it took up twice as much space on the silicon wafer,
which made it twice as expensive to manufacture. And RISC programs had to have their instructions in the right order to take full advantage of the second processor core, which required more advanced program development tools that weren't available
when the first generation of RISC chips hit the market. But like all optimizations, the trade-off was considered worth it if you could execute two instructions per clock cycle, even part of the time."

https://www.opencompute.org/documents/bow-specification-v2-0d-1-pdf : 

"6.5.3. Link Controller
There shall be a Link Controller (LC) outside the PHY. This will manage initialization of the Link.
It may reside on one of the chiplets of the link, in a third chiplet in the package or outside the
package.
Communication from the Link Controller across chiplets shall be by a transport mechanism
outside the BoW link. This could be a serial link like SPI or I2C, but this is not specified at this
time.
Link initialization is described in Section 14. Clocks are described in 10.2." (p.16)

14. Reset and Initialization
14.1. External Facilities
These facilities must be provided outside the PHY:
• A Link Controller (LC) which will manage initialization of the Link. It may reside on one of
the chiplets of the Link, in a third chiplet in the package or outside the package.
• A communication path from the Link Controller to the PHY slices outside the BoW link.
This could be a serial link like SPI or I2C, but this is not specified at this time." (p.42)  

https://eps.ieee.org/images/files/TC_The_Bunch_of_Wires_rev3.pdf

https://www.youtube.com/watch?v=ywmCHQQuELc

https://www.youtube.com/watch?v=Wd5qMSnN7OE

https://www.youtube.com/watch?v=R1wyyfm2Mhk

https://www.opencompute.org/documents/ocp-odsa-cdx-proposed-standardization-of-chiplet-models-for-heterogeneous-integration-2-pdf 

https://146a55aca6f00848c565-a7635525d40ac1c70300198708936b4e.ssl.cf1.rackcdn.com/images/7eaf2db90859c46249e70e403357e7a78bf93c51.png

https://www.opencompute.org/documents/odsa-diport-controller-v0-8-16-sep-22-1-pdf 

https://github.com/opencomputeproject/ODSA-CDXML/blob/main/CDXML.pptx https://en.wikipedia.org/wiki/JEDEC_memory_standards

https://web.archive.org/web/20061002004407/http://www.jedec.org/download/search/JESD79E.pdf
 master

https://github.com/EI2030/Low-power-E-Paper-OS/commit/63be078a84b45702b58b2bcfafff2477b13ab851

https://github.com/EI2030/Low-power-E-Paper-OS/commit/c08cdeaec5a710d6adf3db0fb8fa6a7a13d1a6e6  

https://www.opencompute.org/documents/transaction-and-link-layer-specification-for-bunch-of-wires-bow-interfaces-pdf-pdf

https://www.bcanalog.com/solutions-technology/ 

https://apexsemi.com/partners/#ipp

https://moschip.com/semiconductor/semiconductor-ip/digital-ip/

https://www.kickstarter.com/projects/davewy/artemis-plus-low-power-ai-ml-processing-platform-and-dev-kit

https://github.com/SapphireCircuits/Artemis-Plus-Hardware

https://hackaday.io/page/21232-platos-ideal-world

https://www.cambridgeconsultants.com/sites/default/files/2019-10/Chiplets%20-%20The%20path%20to%20IoT%20diversity.pdf

https://gadgetversus.com/processor/texas-instruments-mad2wd1-specs/
https://en.wikipedia.org/wiki/ARM7#ARM7TDMI
https://www.silabs.com/mcu/32-bit-microcontrollers/efm32pg28-series-2

'The ARM7TDMI (ARM7 + 16 bit Thumb + JTAG Debug + fast Multiplier + enhanced ICE) processor implements the ARMv4 instruction set. It was licensed for manufacture by an array of semiconductor companies. In 2009, it was one of the most widely used ARM cores, and is found in numerous deeply embedded system designs.

Texas Instruments licensed the ARM7TDMI, which was designed into the Nokia 6110, the first ARM-powered GSM phone.[3] This led to the popular series of Nokia phones using the processor, including the 3210 and 3310.[4]" [https://www.youtube.com/watch?v=oyERJx51fgM
](https://youtu.be/oyERJx51fgM?t=595) 
Could EFM32 run ARM7+ 16bit Thumb 16 bit Thumb + JTAG Debug + fast Multiplier + enhanced ICE?

https://en.wikipedia.org/wiki/Nokia_6110
https://www.engadget.com/2011-12-20-the-engadget-interview-arm-co-founder-john-biggs.html

http://lib.tkk.fi/Diss/2004/isbn9512273209/isbn9512273209.pdf

https://www.silabs.com/mcu/32-bit-microcontrollers

Standards
----

https://web.archive.org/web/20091205032921/http://www.via.com.tw/en/resources/pressroom/pressrelease.jsp?press_release_no=4287 "VIA Mobile-ITX Brings Further Miniaturization and Greater Flexibility to Embedded Devices"

https://web.archive.org/web/20081120174810/http://www.via.com.tw/en/resources/pressroom/pressrelease.jsp?press_release_no=1310

https://web.archive.org/web/20070723203650/http://www.epiacenter.com/modules.php?name=News&file=article&sid=1108

https://www.youtube.com/watch?v=MUz_PtAt468

https://archive.ph/20130127190655/http://www.linuxfordevices.com/c/a/News/SUMIT-aims-to-unify-SBC-expansion/

https://en.wikipedia.org/wiki/Mobile-ITX
https://web.archive.org/web/20091229082529/http://www.via.com.tw/en/downloads/whitepapers/initiatives/spearhead/WP091201-ITXFormFactor.pdf

https://en.wikipedia.org/wiki/ATX

https://en.wikipedia.org/wiki/De_facto_standard

https://en.wikipedia.org/wiki/Harmonization_(standards)

https://en.wikipedia.org/wiki/Peripheral_Component_Interconnect

https://en.wikipedia.org/wiki/USB#History

https://tedium.co/2024/02/09/intel-pci-standardization-history/ In the early 90s, Intel developed PCI (1992), ATX (1995), and USB (1995). It is interesting that this circular was released in 1998:

CIRCULAR NO. A-119 Revised
February 10, 1998
MEMORANDUM FOR HEADS OF EXECUTIVE DEPARTMENTS AND AGENCIES
SUBJECT: Federal Participation in the Development and Use of Voluntary Consensus Standards and
in Conformity Assessment Activities

"The US Government Office of Management and Budget published CircularA-119[11] instructing its agencies to adopt voluntary consensus standards before relying upon private standards. The circular mandates standard harmonization by eliminating or reducing US agency use of private standards and 
government standards. The priority for governments to adopt voluntary consensus standards is supported by international standards such as ISO supporting public policy initiatives.[12]"

https://www.whitehouse.gov/wp-content/uploads/2017/11/Circular-119-1.pdf
https://onlinelibrary.wiley.com/doi/10.1111/j.1468-5965.1987.tb00294.x
https://www.sciencedirect.com/science/article/abs/pii/S1386505697001214?via%3Dihub

https://en.wikipedia.org/wiki/Network_effect any harmonized or standardized platform needs a network effect for it to be affordable and attractive 

https://paragraph.xyz/@protocolized/protocols-are-eating-the-world

https://en.wikipedia.org/wiki/Project_Ara One wonders why these projects gets cancelled. Perhaps Apple hands a bag of money to the lead developer, and nothing is heard again? How many times do modular concepts get cancelled due to greed, rather than infeasability? 

https://www.theverge.com/2014/1/29/5359068/google-keeping-motorola-advanced-technology-group-project-ara-phone 

Near Threshold Voltage & Chiplets:
--

https://semiengineering.com/knowledge_centers/packaging/advanced-packaging/chiplets/ History

https://semiengineering.com/sram-in-ai-the-future-of-memory/

https://semiengineering.com/is-your-voltage-drop-flow-obsolete/

"Open (For Business): Big Tech, Concentrated Power, and the Political Economy of Open AI" https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4543807

[https://semiengineering.com/knowledge_centers/packaging/advanced-packaging/chiplets/](https://semiengineering.com/many-chiplet-challenges-ahead/)

https://www.eetimes.com/bringing-tiny-chiplets-to-embedded-socs/

https://www.techradar.com/news/phone-and-communications/mobile-phones/why-our-phones-still-aren-t-powered-by-the-sun-1329646

https://www.techradar.com/features/the-quest-for-the-solar-powered-gaming-console

https://www.bhoite.com/sculptures/ble-satellite/ features:

Seeed Studio’s XIAO nRF52840 dev board. https://www.amazon.com/Seeed-Studio-XIAO-nRF52840-Sense/dp/B09T9VVQG7 (includes battery charger BQ25101)
Eaton 50F, 3.8V hybrid supercapacitor https://www.digikey.com/en/products/detail/eaton-electronics-division/HSL1020-3R8506-R/12179232
SM141K04LV solar cells x 2 (IXYSYS/Anysolar) https://www.digikey.com/en/products/detail/anysolar-ltd/SM141K04LV/9990461
LCD module 1x4 i2C https://www.ebay.com/itm/284843842249

https://en.wikipedia.org/wiki/ARM9#cite_note-5
https://www.allaboutcircuits.com/news/teardown-tuesday-graphing-calculator/

https://en.wikipedia.org/wiki/List_of_ARM_processors

https://www.eetimes.com/cambridge-calling-the-rise-of-the-arm-clones/

https://opencores.org/

https://forums.nesdev.org/viewtopic.php?t=14417

https://www.reddit.com/r/hardware/comments/uqnv20/what_stops_us_from_designing_an_x86_cpu_from/ 

----
ISA
----

https://en.wikipedia.org/wiki/Von_Neumann_architecture#Von_Neumann_bottleneck

https://en.wikipedia.org/wiki/Harvard_architecture

Von Neumann architecture is [not dead yet](https://youtu.be/DnBtoOAhba4?t=23), but:

"Today’s computers are horribly inefficient. The dominant “von Neumann” processor design wastes 99% of energy. This inefficiency is, unfortunately, baked deeply into their design. In von Neumann processors, programs are expressed as a sequence of simple instructions, but running programs 
in a simple sequence is unacceptably slow. Improving performance requires complex hardware to find instructions that can safely run in parallel.

Improving efficiency requires a fundamental rethinking of how we design computers. Others have approached this problem by restricting programs, i.e., limiting the processor to only run programs where parallelism is easy to find. These restrictions let designers simplify and specialize the hardware. 
While this approach improves efficiency, it gives up on general-purpose programmability, which is a huge problem. Generality is efficiency: any part of a program that runs inefficiently quickly limits energy-efficiency of the entire system. Moreover, these specialized processors ignore software, which is where the real value lies in computing.

A new approach to computer design
At Efficient, we are taking a different approach. Going back to the original research at Carnegie Mellon University with Graham and Nathan, we embraced the value of software, and have sought from the outset a general-purpose, post-von Neumann processor design that is easy to program and also extremely energy-efficient.

Our approach spans hardware and software, which is the only path to efficiency. Instead of executing a series of instructions like von Neumann designs, our architecture expresses programs as a “circuit” of instructions that shows which instructions talk to each other.
This model lets us lay out the circuit spatially across an array of extremely simple processors and execute the program in parallel, with much simpler hardware (and thus less energy!) than any existing processor."

from:
https://efficient.computer/blog/efficient-computer-raises-16m-to-solve-computings-energy-problem

The takeaway is that while there are a lot of new architectures out there, one not need to rely on post-Von Neumann architecture for everything if efficiency improvements allow for it, using conventional CMOS. Waiting 10 years to ship a project is sometimes less impactful than optimizing an old architecture to deliver improved gains. Similar to how DUV operates at 193nm

https://www.newport.com/n/deep-uv-photolithography



https://g-ram.github.io/files/gobieski_thesis.pdf

https://wow.groq.com/wp-content/uploads/2020/06/ISCA-TSP.pdf when old architectures do not make economic sense: https://artificialanalysis.ai/ ( https://www.youtube.com/watch?v=WQDMKTEgQnY)

https://en.wikipedia.org/wiki/Tensor_Processing_Unit#Comparison_to_CPUs_and_GPUs (Efficiencies in TPUs, while improved, do not necessitate the transition from Harvard/modified Harvard architecture to TSP or Domain Specific Architectures for every task. In other words, 
the utility of "general purpose" architecture still has utility for as long as Moore's law allows the Harvard architecture to be economically feasible in certain energy scarce applications- ones "too cheap to matter" (similar to an 1954 Atomic Energy Commission saying by Lewis Strauss, and a 2008 Wired artticle) https://www.mimiran.com/not-free-why-0-00-is-not-the-future-of-business/  

If I were to price computer architectures as a commodity- radiation hardening and EMI protection would have more intrinsic value than computation per joule in a microeconomy where energy is not scarce but susceptible to EMI. 

That comparison, as well as pegging von-Neumann architectures to a commodity like gold, is obviously not historically continuous. EMI protection was not needed in agrarian economies, nor in Rennaissance Europe. Likewise, the cost of compute in the 20th century was not a linear scale
from electromechanical machines (such as a Zuse Z3) that were temporarily more pegged to the cost of raw materials that weighed much more, but were not as mass produced nor as exotic as the number of materials in an EUV machine by ASML and Zeiss. However, to examine the continuation of "FLOPs" from the vacuum tube era to today is not entirely discontinuous or inaccurate:

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/48f9a3b8-b2ff-4bf0-bfde-9e838d3205e1)

The industrial revolution led to a higher commodity valuation of coal, then oil, then bytes, and now, tokens. THe interesting part about this graph is that cryptocoin is absent- while cryptocurrency is seen to be a strong special interest group with a stake in the digital economy, 
the ability of AI to compute in fewer joules per token is a driving force for subsidizing next-generation foundries ad-infinitum, pending global sustainability. The beauty of tokens as a catchall for AI is that it represents a moving target- much like how bytes are not defined by 
their energy computation, but their abstract representation to store 8 bits, the entities that 
can move or store the most bytes often have an economic advantage in trade. Tokens take this to another level, in that tokens represent an instance of a byte serving a domain-specific computation-tensors, AI, Language Processing Unit, which machines and humans alike use to intepret bytes. 
Thus it floats on a different plane than bytes- as bytes can be inefficient. Tokens, less so. Tokens are defined by a domain optimized for computing towards an output, receiving an input, and using the fewest number of operations to achieve subsequent/trained outputs, thus they are "pegged" to computation as bytes are, but in a more specific way- tensors, or low precision- 
the minimum amount of precision to complete the computation. Papers seeking even 0.8 bit floating point precision have been mentioned in recent months. https://en.wikipedia.org/wiki/Minifloat#4_bits_and_fewer Thus bytes as a shorthand for data is being redefined based on a more abstract definition of a transaction. 
While currency is converted internationally, bytes too, are inefficient when contextualized in a single dimension. By casting a wider net, the token is in essence a closer representation to a neural unit of computation, one that exists in all cultures, even if energy is exerted in different ways (traditional farming, slash and burn agriculture, 
and industrial farming). With AI and automation set to complement the human workforce in many ways, such as robotics in warehouses and delivery vehicles, computation in the form of tokens is set to become an emerging unit of value, and tokens themselves may be used as a form of compensating human work, 
or even being priced higher for an equivalent unit of organic substrate, if only because if its scarcity/abundance/longevity or ability for superintelligent integration in a larger dataset/multimode. Whether digital currencies will use tokens directly rather than as represented via a Bitcoin (which is not a token in itself but an indicator that a token was 
hashed sucessfully or traded for one), tokens procured via the lowest energy cost may represent a new paradigm shift in the economy, and could very well replace bytes as as unit of "work" or useful information, much like how the U.S. dollar was decoupled from Gold and became fiat(although somewhat for a different reason).
In other words, society determines the value of tokens based on its tendency to consume them. Thus energy efficiency becomes a motivating force to earn more by saving more (except in cases where spending/having more to make more still rings true). 

https://en.wikipedia.org/wiki/SuperH#J_Core

https://lwn.net/Articles/647636/

https://www.coresemi.io/products/overview/j32-cpu-core

-----
https://alc.sparkfun.com/

https://forum.sparkfun.com/viewtopic.php?f=170&t=51685

https://oshpark.com/

http://wiki.mlab.cz/

https://raw.githubusercontent.com/TUDSSL/ENGAGE/master/doc-images/hw-overview.png

https://doc.dustri.org/hardware/Cores%20that%20don%E2%80%99t%20count%20-%202021.pdf

https://arnaud-carre.github.io/2024-10-06-vpternlogd/

https://tomforsyth1000.github.io/papers/LRBNI%20origins%20v4%20full%20fat.pdf

https://software.intel.com/en-us/download/intel-64-and-ia-32-architectures-sdm-combined-volumes-1-2a-2b-2c-2d-3a-3b-3c-3d-and-4 (5,057 pages, covering 286, 386 and up)

https://wunkolo.github.io/post/2024/09/vecint-average-color/

---
RT/OSes & Tools of interest:
---

https://computerhistory.org/blog/the-lisa-apples-most-influential-failure/ Lisa Source Code released by Apple & Computer History Museum 1/19/2023 (40th Anniv).
https://info.computerhistory.org/apple-lisa-code
https://hbr.org/2012/04/the-real-leadership-lessons-of-steve-jobs
https://blog.adafruit.com/2021/05/05/elk-a-tiny-js-engine-for-embedded-systems-embedded-javascript/
https://coder-mike.com/blog/2022/06/11/microvium-is-very-small/


http://www.primrosebank.net/computers/pda/psion3a/psion3a_software_emulators.htm
http://www.inference.org.uk/mackay/psion/part5.htm

FreeRTOS is one of the common OSes used on Ambiq Micro. The advantage to using FreeRTOS over uClinux is a smaller kernel:
https://www.freertos.org/FreeRTOS_Support_Forum_Archive/November_2016/freertos_Free_RTOS_Memory_Management_59ed41adj.html
The disadvantage is more development time. However, with limited onboard flash & RAM, a microkernel would provide lower power consumption than a larger linux kernel, unless using an older linux kernel such as 2.4, but since there would be security risks with an older kernel, 
its functionality would be limited to off-line use. See https://doc.slitaz.org/en:guides:pxe#why-use-pxe-the-vnc-example
https://tiny.slitaz.org/index.php Using a uClinux version for Cortex M4 may have advantages, provided there is enough space for individual apps.

https://en.wikipedia.org/wiki/FatFs
https://en.wikipedia.org/wiki/Cramfs
https://github.com/jcmvbkbc/linux-xtensa (runs on 3MB+ of RAM)
https://hackaday.com/2023/08/19/linux-running-on-not-a-lot/
https://www.youtube.com/watch?v=MpjRqMPWrAg

https://bootlin.com/blog/ext2-filesystem-driver-now-marked-as-deprecated/

https://popovicu.com/posts/making-a-micro-linux-distro/

https://popovicu.com/posts/789-kb-linux-without-mmu-riscv/

https://github.com/popovicu/linux-micro-distro

https://hackaday.com/2023/10/13/because-you-can-linux-on-an-arduino-uno/
https://github.com/raspiduino/arv32-opt

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

https://leanrada.com/htmz/ a low power tool for html

---
Audio
----

https://nwavguy.blogspot.com/2011/02/headphone-amp-impedance.html (not low-power specific, but helpful for quality considerations)

https://engineering.fb.com/2024/06/13/web/mlow-metas-low-bitrate-audio-codec/ 

---
Similar projects/ of interest:
---
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

https://github.com/chettrick/discobsd

https://www.theregister.com/2023/10/06/elks_and_fuzix_tiny_unixes/?td=rt-3a

https://github.com/ghaerr/elks

https://tomu.im/tomu.html

https://electronics.stackexchange.com/questions/27594/what-operating-systems-have-been-ported-to-cortex-m3

Window Managers: 
https://github.com/mackstann/tinywm (0.2MB RAM)
https://unauthorised.org/dhog/9wm.html 
https://en.wikipedia.org/wiki/Twm
https://forums.freebsd.org/threads/window-manager-resident-ram-usage.81914/
https://www.xfree86.org/current/TinyX.1.html

Display Driver
https://github.com/8l/fbui
[Linux framebuffer - Wikipedia](https://en.wikipedia.org/wiki/Linux_framebuffer)
https://github.com/directfb2
https://github.com/Bareflank/hypervisor
https://static.sched.com/hosted_files/osseu2022/2c/Trading_Fbdev_for_DRM_no_returns_accepted_Handouts.pdf
https://www.x.org/releases/X11R7.6/doc/man/man4/fbdev.4.xhtml
https://github.com/TheNeuronProject/ef.qt
https://dri.freedesktop.org/wiki/DDX/

---
DOS + GUISs
----

https://arstechnica.com/gadgets/2024/06/30-years-later-freedos-is-still-keeping-the-dream-of-the-command-prompt-alive/

https://arstechnica.com/gadgets/2024/06/the-ultimate-windows-3-1-laptop-sellers-behind-book-8088-are-back-with-pocket-386/

https://arstechnica.com/gadgets/2023/07/going-deep-with-the-book-8088-the-brand-new-laptop-that-runs-like-its-1981/


http://www.fabglib.org/ https://github.com/fdivitto/fabgl

https://www.youtube.com/watch?v=Tr2yMjrgP8o  IBM PC on ESP32 with FabGL - Part VI (Linux ELKS)
https://www.youtube.com/watch?v=84ytGdiOih0&t=103s


https://github.com/jhhoward/MicroWeb in 640K RAM!

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

https://hackaday.com/2023/11/08/reliving-the-authentic-90s-linux-experience/
https://www.youtube.com/watch?v=MsAHi7t4Cj8

https://www.theregister.com/2023/10/25/window_maker_096_live/

https://www.theregister.com/2023/09/01/antix_23/

---
Silicon Valley History:
----
https://www.youtube.com/watch?v=ZTC_RxWN_xo 

https://steveblank.com/2009/04/06/story-behind-%E2%80%9Cthe-secret-history%E2%80%9D-part-iii-the-most-important-company-you-never-heard-of/

https://landley.net/notes.html#28-10-2023

https://dl.acm.org/doi/pdf/10.1145/234286.1057828  "the early history of smalltalk"

"By now it was already 1979, and we found ourselves doing one of our many demos, but this time for a very interested audience: Steve Jobs, Jef Raskin, and other technical people from Apple. They had started a project called Lisa but weren't quite sure what it should be like, until Jef said to Steve,
"You should really come over to PARC and see what they are doing." Thus, more than eight years after overlapping windows had been invented and more than six years after the ALTO started running, the people who could really do something about the ideas, finally got to to see them. The machine used was the Dorado,
a very fast "big brother" of the ALTO, whose Smalltalk microcode had been largely written by Bruce Horn, one of our original "Smalltalk kids" who was still only a teen-ager. Larry Tesler gave the main part of the demo with Dan sitting in the copilot's chair and Adele and I watched from the rear. 
One of the best parts of the demo was when Steve Jobs said he didn't like the blt-style scrolling we were using and asked if we could do it in a smooth continuous style. In less than a minute Dan found the methods involved, made the (relatively major) changes and scrolling was now continuous! This shocked the visitors,
especially the programmers among them, as they had never seen a really powerful incremental system before.

Steve tried to get and/or buy the technology from Xerox (which was one of Apple's minority venture capitalists), but Xerox would neither part with it nor would come up with the resources to continue to develop it in house by funding a better NoteTaker cum Smalltalk.

VI. 1980-83—The release version of Smalltalk (-80)
"The greatest sin in Art is not Boredom,
as is commonly supposed, but lack of
Proportion" — Paul Hindemith

As Dan said "the decision not to continue the NoteTaker project added motivation to release Smalltalk widely." But not for me. By this time I was both happy about the cleanliness and elegance of the Smalltalk conception as realized by Dan and the others, and sad that it was farther 
away than ever from the children—it came to me as a shock that no child had programmed in any Smalltalk since Smalltalk-76 made its debut. Xerox (and PARC) were now into "workstations" as things in themselves—but I still wanted "playstations". The romance of the Dynabook seemed less within grasp, paradoxically just when the 
various needed technologies were starting to be commercially feasible—some of them, unfortunately, like the flat-screen display, abandoned to the Japanese by the US companies who had invented them. This was a major case of "snatching defeat from the jaws of victory." 
Larry Tesler decided that Xerox was never going to "get it" and was hired by Steve Jobs in May 1980 to be a principal designer of the Lisa. I agreed, had a sabbatical coming, and took it." - Alan Kay

https://news.ycombinator.com/item?id=40506495 

https://web.archive.org/web/20240528075957/https://firstmicroprocessor.com/ 

https://www.youtube.com/watch?v=dxvcBa2RIbU

https://www.youtube.com/watch?v=wVyu7NB7W6Y Exposing The Flaw In Our Phone System (Blue Boxes)

---
Low-Precision/High Throughput
---

https://en.wikipedia.org/wiki/Tensor_Processing_Unit#Comparison_to_CPUs_and_GPUs

https://www.youtube.com/watch?v=WQDMKTEgQnY

https://news.mit.edu/2010/fuzzy-logic-0103

https://spectrum.ieee.org/1-bit-llm

https://arxiv.org/abs/2402.04291

---

Miscellaneous and unrelated links:
--

https://youtu.be/3EPTfOTC4Jw?t=885 Double-precision floating point in video games (an excellent demonstration of a glitch in aligning flippers in Space Cadet Pinball and boxes in Minecraft, pre-64 bit patch) 

http://www.catb.org/jargon/html/overgeneralization.html 

https://youtu.be/WE3R29_6XKw CP/M-65 port to the Olimex neo6502. impractical but nonetheless interesting, like the fuzix port.

https://spectrum.ieee.org/history-of-power-grid

https://hackaday.io/project/195010-pocket-pad

https://hackaday.com/2024/02/29/internet-of-production-alliance-wants-you-to-think-globally-make-locally/

https://www.solarpunkpresents.com/season-four/the-radical-democratizing-power-of-a-better-way-to-make-things-with-sarah-hutton

https://www.internetofproduction.org/electroniccomponents

https://hackaday.com/2023/02/21/openstructures-is-a-modular-building-system-for-the-reprap-age/

https://hackaday.com/2018/02/27/can-open-source-hardware-be-like-open-source-software/

https://search.openknowhow.org/

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

"You can trace the portability aspect into the Macintosh, which had a handle built right into it; that was pretty obvious. Steve also paid a lot of attention to and took a lot of inspiration from Hartmut Esslinger, the founder of Frog Design. The mouse for the Lisa was by
Frog Design and they were mocking up Macintosh cases for us in 1982. Then Steve left Apple and Apple lost its way into a profusion of beige boxes.

If you remember the history the next big thing on the landscape was the Macintosh IIcx. That was a highly modular, highly manufacturable computer and that was a landmark. But it wasn't about portability and it wasn't about industrial design, it was about manufacturability. 
At the same time Compaq was a big success making the PC highly manufacturable and highly modular, and so the Mac IIcx was kind of Apple's answer to that."

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

Mike Muller Interview - 2018 - Life, Acorn and ARM https://www.youtube.com/watch?v=ljbdhICqETE (Describes many of the intersections between Apple and ARM in the early 90s from a top-level)

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



https://www.forbes.com/sites/jaymcgregor/2023/08/16/samsung-is-investing-in-unusual-new-foldable-tablets--laptops/?sh=405e0b4732f3

https://wiki.laptop.org/go/XO-2 (Placement of these links is the hint)

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

"Self-powered electronic paper with energy supplies and information inputs solely from mechanical motions" pp. 1496-1505 (2020)
https://opg.optica.org/directpdfaccess/e1ac90b1-595d-47b7-ae3b3878d6347837_437501/prj-8-9-1496.pdf?da=1&id=437501&seq=0&mobile=no

https://sourceware.org/pipermail/gas2/1994/thread.html

https://en.wikipedia.org/wiki/Howard_Zinn
https://www.zinnedproject.org/materials/neutral-on-a-moving-train-dvd 
https://www.goodreads.com/work/quotes/878739-you-can-t-be-neutral-on-a-moving-train-a-personal-history-of-our-times 
"“You can’t be neutral on a moving train,” I would tell them. Some were baffled by the metaphor, especially if they took it literally and tried to dissect its meaning. Others immediately saw what I meant: that events are already moving in certain deadly directions, and to be neutral means to accept that.”
― Howard Zinn, You Can't Be Neutral on a Moving Train: A Personal History of Our Times"

What the Fork: A Study of Inefficient and Efficient
Forking Practices in Social Coding 
https://cmustrudel.github.io/papers/fse19forks.pdf

Not related, but an early LCD: https://www.youtube.com/watch?v=eGQQWIbD-nM&t=0s

3D Printed Cases (Phones, Laptops, etc)
---

https://github.com/ZitaoTech/Hackberry-Pi_Zero
