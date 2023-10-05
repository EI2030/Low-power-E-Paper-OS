(from https://github.com/kragen/dernocua/blob/master/text/energy-autonomous-computing.md)
This is a Copy from Kragen Sitaker's Dernocua diary:

"I spent some time trying to figure out what it would take to be able
to read, write, and interactively compute, without a connection to a
power grid, with maximal autonomy.  A big part of this is power usage,
and it looks like it should be possible to get a self-sufficient
computing environment that runs on under a milliwatt and doesn’t need
batteries, though batteries might enable orders of magnitude more
computational power.  See also file `microlisp.md` for thoughts on how
to design a software environment for such a computer.

In particular, it seems like with Sharp Memory LCDs, several of
Ambiq’s new line of subthreshold microcontrollers, amorphous solar
panels, and supercaps, you should be able to do a low-resolution
black-and-white GUI on the order of what you could do on a PowerMac
7100, SPARC 5, or 486DX2/66, without a battery, on 0.5 mW, with an
average write bandwidth to your SD card of some 10 kilobytes per
second (say, 10 megabytes per second at an 0.1% duty cycle).  You
could run a Web browser and PDF viewer, though not DHTML apps like
Slack and Fecebutt, because it would only have a few megabytes of RAM
across all the CPUs, and PDFs might be difficult to read at the low
resolution of the screen.  The whole computer might weigh 100 grams.

It would take a week to discharge when not in sunlight, but need only
an hour or so of sunlight per day, or a few seconds of being plugged
in, to stay fully charged.  By scaling the clock frequency of the CPUs
and turning more of them on, within a few milliseconds you could scale
up to a billion instructions per second (comparable to a
turn-of-the-millennium Pentium III or iMac G4, or an iPad 2 from
02011, or the original Raspberry Pi), though this would be limited by
your available energy, since it would use close to 50 milliwatts.

Computation needs
-----------------

Although computation isn’t the only power cost in a computer, it’s a
fundamental one.  But how much computation do you need?  About 0.1
DMIPS for a minimal responsive computing environment (Apple ][,
Commodore 64, SDS 940); about 1 DMIPS for a reasonably comfortable one
with a lightweight GUI and IDE (VAX 11/785, HP 9000/500, IBM PC/AT,
Sun 3/60); maybe 10 DMIPS for workstation-class performance (SPARC 2,
386/40); maybe 100 DMIPS for browsers and rich GUIs (SPARC 20, RS/6000
250, PowerMac 7100, Pentium 120).

### Historical computer performance: a 1-MHz 6502 was a bit less than 0.1 DMIPS ###

A Commodore 64 or Apple ][ were also capable of running the VisiCalc
spreadsheet, the Berkeley Softworks GEOS GUI and geoPaint and whatnot,
and Contiki, though not, say, the GEM desktop.  The 5MHz and sub-MIPS
Apple Lisa was capable of running a non-janky GUI, but even on the
Macintosh (7.8 some MHz, 16-bit ALU, [0.40–0.52][25] Dhrystone MIPS
even though [some 68000 machines were faster][26]) it was slow enough
that you could see the order in which the lines of dropdown menus got
painted, top to bottom.  [With GEOS on the Commodore 64, though, you
can see that it paints each line of the dropdown menu left to right,
even with a memory expander cartridge,][47] and in geoWrite, typing
onto the end of a short line of centered text makes it flicker quite
noticeably as it gets erased and repainted left to right in the new
position.

[25]: http://performance.netlib.org/performance/html/dhrystone.data.col0.html
[26]: https://en.wikipedia.org/wiki/Instructions_per_second
[28]: https://articulo.mercadolibre.com.ar/MLA-896239873-computadora-commodore-64-c-funciona-liquido-dream-_JM
[47]: https://youtu.be/gnFavusEwVE?t=1146 "10MARC Presents: GEOS Adventures Part 1"

The [Magic-1 4-MHz homebrew microcoded TTL minicomputer gets 506
Dhrystone repetitions per second][50], while the same page says the
Mac 512 gets 625. I guess those work out to ` (mapcar (lambda (x) (/ x
1757.0)) '(506 625)) ` 0.29 and 0.36 respectively.  0.36 is a little
lower than the 0.40–0.52 range in the netlib page cited above, but
it's pretty close.  The same page reports that a 2.5-MHz Z-80 did 91
Dhrystones per second, which is 36.4 Dhrystones per second per MHz,
and that an Apple IIe only squoze 37 Dhrystones per second out of its
1.02 MHz 65C02, which by the same calculation is ` (/ 37 1757.0)
` = 0.021 DMIPS, and thus 0.021 DMIPS/MHz.  And so that seems to be
close to the minimum CPU power to run a usable GUI.

So the STM32F1 does about 50 (!) times as much Dhrystone work per
clock cycle, and about 4–5 times as many instructions per clock cycle,
so it’s doing about 10–12 times as much Dhrystone work per
*instruction*.  This is substantially larger than the factor of 2 I
had guesstimated for the 8-bit vs. 32-bit difference, and I suspect
it’s unrealistically large — an artifact of trying to benchmark the
C-unfriendly 6502 with a C program, and perhaps using a lousy compiler
to boot.

### [SRI’s oN-Line System][52] ran on an SDS 940 system at around 0.1 DMIPS ###

[52]: https://en.wikipedia.org/wiki/NLS_%28computer_system%29

The Mother of All Demos, demonstrating the mouse, windowing, networked
hypertext, multimedia computerized documents including images, and
IDEs, was done in 01968 on an SDS 940 (one of some 60 ever built, over
a third of which were sold to Tymshare) which supported 6 concurrent
users, using specialized analog hardware for video compositing.  The
system’s interactive response slowed notably when more than one person
was using it actively.  The SDS 940 had a 24-bit CPU and up to 64
kibiwords of 24-bit memory.  [An integer add instruction on its
predecessor the 930 took 3.5 μs][53], and the memory’s cycle time was
1.75 μs, so we can estimate it roughly at 200,000 instructions per
second, about the same as the 1-MHz 6502 in the Commodore 64; but they
were 24-bit instructions instead of 8-bit instructions, so it might
have been perhaps twice as fast as the C64.

The 940 they were running NLS on [was exactly the same in those
respects][54]: 0.7-μs memory access time, 1.75-μs cycle time, 3.5-μs
“typical execution time” for integer addition “(including memory
access and indexing)”, and 7.0 μs for integer multiply.

The manual/brochure for the machine, which was built for the Berkeley
Timesharing System under which NLS ran, says:

> System response times are a function of the number of active users.
> Typical times are:
> 
> 6 active users . . . . . 1 second  
> 20 active users . . . . . 2 seconds  
> 32 active users . . . . . 3 seconds  

[53]: https://en.wikipedia.org/wiki/SDS_9_Series#SDS_930
[54]: http://archive.computerhistory.org/resources/access/text/2010/06/102687219-05-08-acc.pdf "SDS 940 Time-Sharing Computer System, 18 pp."

It's very unlikely that anybody ever ran Dhrystone on the SDS 940; its
successor the SDS 945 was announced in 01968, and that was the last of
the whole SDS 9 line; SDS continued to introduce upgrades to the
32-bit [SDS Sigma series][55] until 01974 (though that series began
earlier, in 01966), until Xerox sold them to Honeywell in 01975.  I
think the last operational SDS 940 probably got decommissioned in the
mid-1970s.  (These things weren't cheap to run; the SDS 940 manual
cited above says it used 3 “Kva”, which is roughly kilowatts.)  But
[Dhrystone][57] wasn’t written until 01984.

[55]: https://en.wikipedia.org/wiki/SDS_Sigma_series
[57]: https://en.wikipedia.org/wiki/Dhrystone

Amusingly, some [former SDS employees refounded the company in
01979][56].  Guess what CPU their new computer used?

A 6502A.

[56]: https://en.wikipedia.org/wiki/Scientific_Data_Systems#A_new_start

The vague handwaving argument above that the 1-MHz 6502’s 0.02-DMIPS
number is a little lower than would be realistic, along with the
estimate that the SDS 940 was probably about twice as fast, combine to
form a vaguer, even more handwaving argument that the SDS 940 was
about 0.1 DMIPS, which was barely able to support 6 concurrent users
with specialized analog display hardware.

This reinforces the above argument that 0.1 Dhrystone MIPS is close to
the minimum practical for an interactive computing system.

### Estimating the necessary performance for basic interactive computation: 0.1 DMIPS ###

My previous estimate in Dercuano was that basic interactive
computation like word processing takes about 7500 32-bit instructions
per keystroke.  At one point, I said, “WordStar on a 2MHz (≈0.5MIPS)
8-bit CPU would sometimes fall behind your typing a bit,” but then
later calculated that a Commodore 64 (now [AR$12000][28] = US$80) or
Apple ][ would only do about 200 000 8-bit instructions per second and
were usable for word processing, and a 32-bit instruction is roughly
equivalent to two 8-bit instructions, so you need about 0.1 32-bit
MIPS, and you might be typing like 160 wpm (13.3 keystrokes per
second), which works out to about 7500 instructions per keystroke.

Also in Dercuano, I estimated that painting text in a framebuffer fast
enough that it doesn’t slow down reading at 350wpm might take about 50
bytes of I/O per glyph and 100 instructions / glyph × 350 wpm × 6
glyphs / word × 1 minute / 60 seconds = 3500 instructions/second.  But
that’s orders of magnitude lower than the computations I discussed
above.  Indeed, old computers like the Sinclair ZX-81 with its
3.25-MHz Z-80, lacking an external framebuffer, would use the CPU to
repaint the screen 50 times a second.

### Modern microcontrollers run at around 1 Dhrystone MIPS per MHz ###

How fast are modern microcontrollers?  [dannyf compiled Dhrystone 2.1
with a modern compiler][48] and got 921 repetitions per second per MHz
on an STM32F1 with what I guess is the vendor compiler, or 736 with
GCC; to [convert that into Dhrystone MIPS I think we divide by
1757][58], so that’s 0.52 and 0.42 DMIPS/MHz.  However, other
commenters say the ARM Cortex-M0+ used in the STM32F1 is 0.93 DMIPS
per MHz, and the STM32F103x8/STM32F103xB datasheet says it's actually
“1.25 DMIPS/MHz (Dhrystone 2.1)”.  And apparently [a CoreMark is about
half a DMIP][49].

[58]: https://en.wikipedia.org/wiki/Dhrystone#Results
[48]: https://www.eevblog.com/forum/microcontrollers/dhrystone-2-1-on-mcus/
[49]: http://linuxgizmos.com/hifive-unmatched-sbc-showcases-new-fu740-risc-v-soc/
[50]: http://www.homebrewcpu.com/new_stuff.htm

Computational energy consumption
--------------------------------

How much battery you need, and whether you need a battery at all, and
what other kind of power source you need, depends on how much power
you need.  So, how much power do computers need?

### Laptops need tens of watts and often run off old 18650s ###

My “new” HP laptop’s `/sys/class/power_supply/BAT0/power_now` produces
numbers ranging from about 11 million to about 32 million, with CPU
usage seeming to be the biggest determinant.  (I’m guessing these are
microwatts.)  Its battery (four 18650 cells, I think) is so shot that
it only runs for about an hour and a half on it, which suggests a
capacity in the 60–180 kJ range, probably close to 100 kJ.  The (HP
V104) notebook battery is *labeled as* “14.8 V” and “41Wh” (though the
broken off-brand spare says “2200mAh/33Wh”), and
`/sys/class/power_supply/BAT0/energy_full_design` says 23206000, and
bizarrely so does `energy_full`, and `energy_now` approaches that
level (20364000 at the moment).  `cycle_count` reports 208, but then
after popping the battery out and back in, only 200.  [The docs
say][7] that energy is reported in μWh; `power_now` is not documented
there but [SuperUser says it’s in μW][8], and indeed 23 watt-hours
divided by 15 watts is about an hour and a half.  I suspect the
battery is worn out down to 57% capacity and just doesn’t report its
design capacity.  23 Wh at 14.8 V is 1600 mAh, which is in a
reasonable range for the half-worn-out 18650s it presumably contains.

[7]: https://www.kernel.org/doc/Documentation/power/power_supply_class.txt
[8]: https://superuser.com/questions/808397/understanding-the-output-of-sys-class-power-supply-bat0-uevent

It can do something like 10 or 15 billion instructions per second, so
this is something like 2000–3000 pJ per instruction, including the
monitor.

[An HPC paper from 02011][94] found that these numbers were typical of
the most efficient large processors from the 02000s and 02010s: the
Lenovo ThinkPad X201s i7-640LM (15 W idle, 33 W run, 13917.89
Dhrystone MIPS, 2400 pJ/“insn”), the Dell Inspiron 910 Atom N270 (7 W
idle, 10 W run, 4683.57 Dhrystone MIPS, 2100 pJ/“insn”), and the SHARP
PC-Z1 i.MX515 (2.2 W idle, 4.4 W run, 1184.58 Dhrystone MIPS,
3700 pJ/“insn”).  Many other contemporary processors they tested
(Pentium D, MV88F5281-D0, Xeon E5530, Core 2 Quad) were less efficient by an
order of magnitude or even more.

[94]: https://ipsj.ixsq.nii.ac.jp/ej/?action=repository_action_common_download&item_id=78048&item_no=1&attribute_id=1&file_no=1 "Retrospective Study of Performance and Power Consumption of Computer Systems, 02011, Tomari and Hiraki"

### Ereaders use on the order of 200 mW; maybe reprogram one? ###

The [Amazon Swindle 2][29] uses a 3.7V-1530 mAh battery (20 kJ), which
reportedly lasts [7 days after Amazon tweaked the firmware][30], which
I think is based on some nominal usage level per day — [Amazon shill
sites claim it’s only 15 hours of active use][31], and people say they
[normally charge their e-readers around once a week][32] or [every
32–64 hours of use or so][33], with 6–8 weeks of standby time.  So
this is about 100–300 mW during active use.  Other e-ink-based
“ereaders” have similar battery lives.  All of them have much higher
display resolution than a Nokia cellphone display (typically 300 dpi
instead of like 20 dpi), but evidently they also use two orders of
magnitude more power, a problem which may not be entirely fixable in
software.

[29]: https://en.wikipedia.org/wiki/Amazon_Kindle#Kindle_2
[30]: https://ceklog.kindel.com/2009/11/24/longer-battery-life-for-the-kindle-2/
[31]: https://www.pickmyreader.com/long-will-kindle-battery-last/
[32]: https://www.goodreads.com/topic/show/19252863-battery-draining-quickly
[33]: https://archive.fo/bg5vd "https://www.quora.com/How-long-is-the-battery-life-for-a-Kindle-Paperwhite"

Reprogramming and possibly rewiring an ereader (Amazon or otherwise)
might be a reasonable approach.  Since the [Swindle Touch][34] in
02011, most of them have touchscreens, and since the Paperwhite in
02012, most have backlights or frontlights, which can be turned off.
New, these cost on the order of US$150 here, but older models are
available used and supposedly working for [AR$7000–10000][35]
(US$50–70), 86% Amazon-branded (344 out of 398 current listings).
Older devices tend to have more I/O options, while newer ones tend to
be waterproof.  An [already-jailbroken Swindle is currently for sale
for AR$17000][36] (US$115; Paperwhite 3, 1072×1448, 300dpi, LED
frontlit, 1GHz CPU, 0.5 GiB RAM, “4/3” GB Flash, touchscreen).
Non-Amazon ereaders like the [Noblex ER6A15][37] (AR$12500, US$85)
tend to run Android and have SD card slots, which have been removed
from more recent models of the Swindle — though that one in particular
has no data radios.

[34]: https://en.wikipedia.org/wiki/Amazon_Kindle#Kindle_Touch
[35]: https://computacion.mercadolibre.com.ar/tablets-accesorios/e-readers/usado/_PriceRange_0-10000
[36]: https://articulo.mercadolibre.com.ar/MLA-902119551-kindle-paperwhite-3ra-generacion-como-nuevofundajailbreak-_JM
[37]: https://articulo.mercadolibre.com.ar/MLA-869689729-noblex-er6a15-e-reader-6-memoria-4gb-luz-micro-sd-funda-_JM

Some Swindles have LCDs instead of e-ink displays, and these have
larger batteries; the [Swindle Fire HD 7’s is reportedly 4440 mAh,
bringing its weight to 345 g][38], for example.

[38]: https://www.devicespecifications.com/en/model-battery/e1a32e23

The Kobo seems to have the best reputation for hackability and can run
the [portable open-source ereader firmware “KOReader”][41] (though
there aren’t many for sale; Forma 8 and Clara HD seem to be the
options, but [one Aura N514 remains, at AR$16000][39]), and at least
some models of the Barnes & Noble Nook pair a small, fast LCD with a
large e-ink display, enabling you to have both rapid feedback and low
power use, but [none of them on sale now have this][46].

[46]: https://computacion.mercadolibre.com.ar/tablets-accesorios/e-readers/barnes-noble/

[Report on rooting the Aura][40]:

> I had read that some newer models had the NAND flash soldered onto
> the board, but mine is a Sandisk sdcard in a slot. So I pulled the
> card out, dd copied it, and I can restore if I do anything really
> bad that makes it stop booting.
> 
> There is a well-marked ttl level serial port on the back. uboot is
> accessible and allows for interrupting boot. You can log into a root
> shell onto the running system without a password. It's basically
> open for business.

[The Kobo company does have some despicable practices you have to
protect yourself from][42].

[39]: https://articulo.mercadolibre.com.ar/MLA-904536370-ereader-_JM
[40]: https://www.mobileread.com/forums/showthread.php?t=281817
[41]: https://github.com/koreader/koreader
[42]: https://www.mobileread.com/forums/showthread.php?t=223155

The Kobo Clara is reputedly [pretty easy to program without needing to
jailbreak.][44] It uses the same [.kobo/KoboRoot.tgz firmware upgrade
process earlier Kobos did.][45]

[44]: https://www.mobileread.com/forums/showthread.php?t=314032
[45]: https://yingtongli.me/blog/2018/07/30/kobo-telnet.html

Jailbreaking the Swindle is [quite a pain by contrast][43], because
Amazon keeps causing trouble.

[43]: https://blog.the-ebook-reader.com/2018/03/17/list-of-hacks-mods-and-add-ons-for-kobo-ereaders/

### Lower-power computing: low-power MCUs use 200 pJ/insn, Ambiq uses 30 ###

Ordinary microcontrollers (without a monitor) are comparable to the
laptop’s 2000–3000 pJ/intruction power usage, or a bit lower, or much
worse for floating-point or SIMDable computations, but low-power
microcontrollers like the STM32L0 or the Atmel SAMD picoPower ARM
chips are in the 150–250 pJ/insn range, and the MSP430 just a little
higher (though only 16-bit).

Recent reports are that [the new RISC-V-based microcontroller line
“GD32V”][23] are better by another factor of 3 or so.  [The datasheet
for the GD32VF103][24] doesn’t yet provide a lot of detail on lowest
possible power consumption, but the numbers they do give say that it
uses about 2.1 mW/MHz at 2 MHz, which drops to 0.7 mW/MHz at 36–48 MHz
and 0.6 mW/MHz at 72–108 MHz, at 3.3 V, executing from Flash, with all
peripherals off.  You can probably improve this by running at 2.6 V,
which is still kind of sad because the RISC-V core itself is running
at 1.2 V.  (The datasheet and user manual claim it’s a Harvard
architecture, so you probably can’t execute from RAM, and executing
from RAM does improve power consumption on ARM microcontrollers.)  If
we assume that’s about one instruction per clock cycle, 0.6 mW/MHz is
also 0.6 mW/MIPS (not Dhrystone MIPS!), which works out to 600 pJ per
instruction.  This is a little better than the STM32F0 (which I think
is 12 mA at 3.6 V and 48 MHz: 900 pJ/instruction) but a lot worse than
the STM32L0.

[23]: http://www.gd32mcu.com/en/product/risc
[24]: https://www.gigadevice.com/datasheet/gd32vf103xxxx-datasheet/

Ambiq has apparently finally brought to market subthreshold computing,
Sparkfun sells [an Ambiq Apollo3 devboard][81] for US$15 with a 48MHz
Cortex-M4F with 1MB Flash and 384k SRAM on the chip, running at 6
μA/MHz at 3.3V, which I think is roughly 5 μA/DMIPS, plus floating
point.  The 6μA figure is running a while loop, though; more typically
[the datasheet][82] says it’s supposed to weigh in at around
10 μA/MHz, which works out to 33 pJ/instruction, plus 68 μA overhead.
This is higher than the 3pJ/insn research subthreshold processors I
mentioned in file `low-power-micros` in Dercuano, but it’s
dramatically lower than the STM32L0, a dramatically less capable
processor.  [Direct from Ambiq, the chip costs US$4.21.][103]

XXX I uh have gotten confused between μA and μW in most of the rest of
this note and need to redo a lot of calculations which are off by a
factor of 3.3 now

[81]: https://www.sparkfun.com/products/15170
[82]: https://cdn.sparkfun.com/assets/c/1/b/7/6/Apollo3_Blue_MCU_Data_Sheet_v0_10_0.pdf
[103]: https://www.ambiq.top/en/mcu-1/apollo3

0.1 MIPS at 1000 pJ/insn works out to 0.1 milliwatts, and at 33
pJ/insn it’s 3.3 μW; 1 MIPS would be 33 μW; 10 MIPS would be 330 μW.
It’s worth noting that these are *average* figures; a 10-MIPS 80386-40
couldn’t go any faster than 10 MIPS, but the Apollo3 can reportedly
“burst” to 96MHz occasionally for Pentium-Pro-like responsiveness
while averaging 100 μW.

Display energy consumption
--------------------------

At such low power levels, the processor might not be what consumes
most of the power.  For example, unless the UI is purely audio, you
need a display, and it's easy for the display to use much more than
that.  In modern hand computers such as cellphones, it's common for
the display to use the majority of the power.

My estimate from Dercuano was that updating an e-paper display takes
about 25 μJ per glyph; at 350 wpm and thus 35 glyphs per second, this
works out to 875 μW, which is several times more than the 0.1 MIPS or even 10 MIPS.
My friend Eric Volpe tells me that he’s gotten old Nokia SPI screens
(like the 84×48 Nokia 3310 screen, about 25 words of text) to maintain
their display on less than 1 mA at 3.3 volts (though [others say it
needs 6–7 mA][25], and he reports that it consumes more when you’re
updating it, too).  They’re readable without backlight in direct
illumination, but if you use it, he says the backlight also uses
nearly a milliamp.

[25]: https://duino4projects.com/using-nokia-3310-84x48-lcd-arduino/

But now there are displays with much lower power consumption than
that.  Adafruit is selling a [Sharp LS013B7DH05 memory LCD][83]
breakout board for US$25; it’s 168×144 pixels in 24.5 mm × 21 mm (174
dpi), and they claim it draws 4 μA at 3.3V “with 1Hz data refresh”, so
13 μW.  [The datasheet says][84] you can write individual lines of
data to it with a serial protocol at up to 1Mbps, but it’s write-only,
and the maximum frame rate is 60fps.  The datasheet provides no
information at all about power consumption, so I guess Adafruit’s
testing is all we have to work with.  Delightfully, they’ve used a ZIF
socket and double-stick tape so you can take the module off the
breakout board without desoldering anything.  Like cellphone screens,
it’s readable in sunlight.  [Sharp’s brochure from 02015][85] says its
power consumption is “60 μW\*” and gives the power consumption of
similar-sized displays as “10 μW static, 45 μW dynamic” and “15 μW
static, 150 μW dynamic”.

[83]: https://www.adafruit.com/product/3502 "Adafruit SHARP Memory Display Breakout - 1.3" 168x144 Monochrome"
[84]: https://cdn-shop.adafruit.com/product-files/3502/Data+sheet.pdf
[85]: https://www.mouser.de/pdfdocs/Sharp_Memory_LCD_Brochure_2015746065.PDF

Although it’s out of stock, in theory [Adafruit also sells a bigger
Memory LCD for US$45][86], 400×240 pixels and 58.8 mm × 35.3 mm
(173 dpi), which I guess is the [LS027B7DH01A][87], running on 5 V and
“50 μW static, <175 μW dynamic”, and which is monochrome but
transflective.  This is the display the [Playdate handheld
console][88] ([press blurb with demo video][90]) is planning to use,
according to [the Wikipedia article][89].  This resolution would give
you 40 lines of 114 characters at 3.5×6 or 30 lines of 80 characters,
which is quite comfortably usable.  In Adafruit’s demo video it seems
to be at least 30fps.

[86]: https://www.adafruit.com/product/4694 "Adafruit SHARP Memory Display Breakout - 2.7" 400x240 Monochrome"
[87]: https://www.sharpmemorylcd.com/2-7-inch-memory-lcd.html
[88]: https://play.date/
[89]: https://en.wikipedia.org/wiki/Playdate_%28console%29
[90]: https://www.theverge.com/2020/8/12/21365535/playdate-handheld-game-console-doom-release-date-new-games-update

[A fellow named Mike made a video in 02011][97] with one of these
400×240 displays; he reported that you can update a single 400-pixel
line at a time, and that he measured the power draw at 5 μA to hold a
static display, or 3–4 μA if your “frame signal” is at its minimum
speed of 4 Hz (max is 100 Hz).  He also said the datasheet says you
can clock pixel data in at 2 MHz, but he’s been able to clock it up to
6 MHz with success, updating the whole screen in 40–50 ms.  Also,
interestingly, for the reflective (not transflective) ones, he
suggests the interesting possibility of bouncing light off them for a
projector, which could help with the small physical size of these
displays.

[97]: https://www.youtube.com/watch?v=eAoC818Mxy4

There’s also an [EEVblog video from 02019][98] and [forum thread][99]
about using these memory LCDs for “super” low-power design.

[98]: https://www.youtube.com/watch?v=XoHkE4xgaFA
[99]: https://www.eevblog.com/forum/blog/eevblog-1242-memory-lcdsupercapslow-power-design/

Digi-Key [also has in stock a 320×240 LS044Q7DH01 Sharp Memory LCD for
US$70][100], which is a 4.4-inch diagonal, and [the tiny 184×38
LS012B7DD01 for US$16][101], demonstrated in the EEVblog video.

[100]: https://www.digikey.com/en/products/detail/sharp-microelectronics/LS044Q7DH01/5054070
[101]: https://www.digikey.com/en/products/detail/sharp-microelectronics/LS012B7DD01/5054063

The smallest we can practically make readable English text is about 6
pixels tall and 3.5 pixels wide, in a proportional font, giving 24
lines of 48 characters in 168x144; more traditional than proportional
3.5×6 is fixed-width 5×8, as used in lots of terminals in the 01970s
and 01980s, which would give 18 lines of 33 characters.  Either of
these would qualify as “barely usable”, I think.  If we guess that
Adafruit’s 13 μW measurement is 10 μW of static power plus 3 μJ to
refresh the whole screen, then Sharp's 60 μW\* rating would be at 16.7
fps, but updating an 8-pixel line of text on the display would cost
170 nJ, two orders of magnitude less than my 25000 μJ Dercuano
estimate for e-paper.  (The datasheet says you can update a line at a
time, but Adafruit says you have to update the whole screen.)

Doing this 35 times per second would cost 6 μW on top of the base
10 μW for a total of 16 μW.  But my “35 glyphs per second” was to keep
ahead of someone *reading*, not typing; that’s really one line of text
per second, and you probably don’t have to redraw it 35 times!  So
it’s more like 10.2 μW under the assumptions above.  Basically,
updating the display at full text reading speed probably costs an
insignificant amount more than the display’s static power consumption.

Suppose we have the 400×240 display consuming 100 μW, and an Ambiq CPU
consuming another 100 μW, probably providing about 40 DMIPS, 400 times
the minimum above, and closer in speed to an [i860, an Alpha
21064][92], a [SPARC 5][94], [a 486DX2/66, or a PowerMac 7100/66, than
to a Commodore 64 or an SDS 940][91].  You’d have less RAM (more like
an Amiga, a Mac, or a 386 than like these late-90s CPUs) but you can
leverage enormous amounts of fast Flash to make the RAM feel bigger.
These 0.2 mW are then plenty to get a *really good* responsive
interactive computation environment.  Smalltalk, GUIs, spreadsheets,
IDEs, the whole works.  Just, not modern web browsers, not without a
lot more memory.

[91]: https://frc.ri.cmu.edu/~hpm/book97/ch3/processor.list.txt
[92]: https://en.wikipedia.org/wiki/Instructions_per_second#Timeline_of_instructions_per_second

Memory energy consumption
-------------------------

Generally you probably want some kind of memory besides on-chip RAM,
both so you don’t lose your data when you run out of energy, and
because it allows you to have more data than fits in on-chip RAM.

And you probably want a *lot* more than the few hundred K of on-chip
RAM these microcontrollers give you.  CP/M machines used for
development work typically had dual 8-inch floppy drives, holding half
a meg or a whole meg per disk, with a disk storage cabinet with 16–256
of these floppies in them, for a total capacity in the tens to
hundreds of megs; a Commodore 64 might have a 170-KiB 1541 drive, but,
again, a stack of hundreds of floppies, for tens of megs of space.  A
[Sun-3 in the late 01980s][102] might have 16 MiB of RAM (the base
US$12000 models came with 4 MiB, while mine had 48 MiB, but that’s
because I bought it in the late 01990s after RAM was cheap); an
internal disk of 71, 141, 327, or 654 MiB; and access to an NFS server
with more than a gibibyte.  That’s what was needed to be comfortably
productive with these machines.

[102]: http://www.bitsavers.org/pdf/sun/Sun_Price_List_Dec88.pdf

Having a few hundred K of RAM on-chip, like the Ambiq chip does, can
ease the cost of using such memory enormously.  The kinds of paging
and swapping schemes considered in file `microlisp.md` need much less
off-chip traffic, and thus power usage, when most of their working set
fits in the chip’s own RAM.

This involves much less of a *speed* cost than accessing data in
external memory in the historical systems I talked about above.
Paging, swapping, or overlaying on floppies was painfully slow, with
access times around a second and bandwidths of a few kibibytes per
second, and even on hard disks access times were in the tens of
milliseconds and bandwidths under a mebibyte per second.  Modern
spinning-rust hard disks can manage latencies in the milliseconds and
bandwidths in the tens of mebibytes per second.  By contrast, the
forms of memory discussed here have latencies in the 10ns to 100_000ns
ranges (except for writing to NOR, which takes tens of ms) and
bandwidths in the range of 2–32 MiB/s, while the microcontrollers
we’re talking about can only access their internal SRAM at speeds
around 64–128MiB/s.  So it’s much more a question of the *energy* hit.

Suppose we’re willing to spend another 200 μW on accessing external
memory on average.  With crude factor-of-2 approximations, this gives
us these fairly stringent, floppy-disk-like bandwidth limits (though,
as with computation, these limits are averages rather than peaks):

<table>
<tr><td>               <th>read a byte<th>write a byte <th>read BW <th>write BW  <th>cost per megabyte
<tr><th>SPI SRAM       <td>10 nJ      <td>10 nJ        <td>20kB/s  <td>20kB/s    <td>US$20
<tr><th>parallel SRAM  <td>5 nJ       <td>5 nJ         <td>40kB/s  <td>40kB/s    <td>US$5
<tr><th>NOR Flash      <td>0.5 nJ     <td>2_000 nJ     <td>400kB/s <td>0.1kB/s   <td>US$0.50
<tr><th>NAND Flash     <td>1 nJ       <td>10 nJ        <td>200kB/s <td>20kB/s    <td>US$0.01 (or US$0.0001 as an SD card)
<tr><th>Ambiq MCU (!)  <td>0.05 nJ    <td>0.05 nJ      <td>4MB/s   <td>4MB/s     <td>US$5
</table>

If instead we’re willing to splurge 10 mW (average) on accessing
external memory, it becomes a much more appealing option, though we
are more often limited by interface speeds:

<table>
<tr><td>               <th>read BW <th>write BW
<tr><th>SPI SRAM       <td>2MB/s   <td>2MB/s
<tr><th>parallel SRAM  <td>2MB/s   <td>2MB/s
<tr><th>NOR Flash      <td>20MB/s  <td>5kB/s
<tr><th>NAND Flash     <td>10MB/s  <td>1MB/s
<tr><th>Ambiq MCU      <td>50MB/s  <td>50MB/s
</table>

Even with this expanded power budget, we can still read faster from
Flash than from parallel SRAM because the Flash chips use so little
power.

The standby currents of the memories are in almost all cases insignificant.

Details follow.

### SD cards ###

SD cards and even eMMC memory are very cheap nowadays, and Flash does
not use energy to maintain data the way SRAM or DRAM does.  Matthew
Green tells me current Sandisk MicroSD cards can handle 90MB/s of
write traffic and 2000 iops for a few minutes, but then start to have
multi-second garbage collection pauses, and can deliver 200MB/s of
read traffic.  [Sandisk 32GiB MicroSD cards, possibly of this speed
and possibly not, are locally available for AR$925][106], which is
US$5.

[106]: https://articulo.mercadolibre.com.ar/MLA-886634828-microsd-32gb-sandisk-ultra-100mbs-clase-10-_JM

### NOR Flash ###

For things that get written rarely but need instant random-access
reads, NOR is an option.  You can get surprisingly
cheap and fast SPI flash, as outlined in file `ghz-dds.md`: [the 30¢
GD25D10C][66] contains half a mebibit of NOR flash and can read it at
160 megabits per second.  It uses about 0.1 μA
(0.33 μW) in standby — you’d have to cut its power line with a MOSFET
or something if you want to avoid that.  Actively reading from it at
this 160Mbps speed is supposed to cost 2.5 mA (8.25 mW), and *writing*
costs *20* mA (**66 mW**) and is also slow as dogshit.  After a
snowstorm!  Doing the math, reading a byte (of a long stream of them)
at that speed costs about 400 pJ, plus whatever the processor spends
on frobbing the SPI lines.

(How slow is writing?  100 000 000 ns (a suspiciously round number!)
to erase a 4KiB sector (thus 24 000 ns to erase each byte), 30 000 ns
to program the first byte, and 2500 ns to program each subsequent
byte.  This staggering total of 10 300 000 ns to write an erased
sector brings the total time to 110 000 000 ns to erase and rewrite
it, or 27 000 ns per byte, and the *energy* to write the byte to some
1800 nJ, on the order of executing 3000 instructions.)

### SRAM ###

CMOS SRAM uses a little energy, but much less than DRAM; for example,
[the Cypress CY62136EV30LL-45ZSXIT][67] is a 2-mebibit (256-kibibyte)
45-ns asynchronous parallel SRAM chip for US$1.11 that claims it
typically uses 1 μA at 2.2–3.6 V to retain its data when in standby
mode.  The big problem with SRAM is that fast SRAM is all
parallel-interface, so you need at least to spend at least 26 pins to
talk to this chip, though this is less of a problem if you spend a
27th pin to pull its /CE line high — you can share the pins with other
signals as long as they go to other things that also have some kind of
/CE-like mechanism.

[66]: https://www.gigadevice.com/datasheet/gd25d10c/
[67]: https://www.digikey.com/en/products/detail/cypress-semiconductor-corp/CY62136EV30LL-45ZSXIT/1543737

Still, spending 3 μW to get an extra quarter-mebibyte of 45ns SRAM
seems pretty cheap.  But that goes up to 6600 μW/MHz when you’re
actively frobbing it (2 mA at 1 MHz, says the datasheet front page.)
That’s, I guess, 3300 pJ per off-chip SRAM
access, which is kind of high when we recall that we’re only paying on
the order of 500 pJ per instruction (or much less with Ambiq)
and 400 pJ per byte read from SPI
NOR Flash.  Accessing the SRAM *once* costs as much as running *7*
instructions, or *100* Ambiq instructions.
You can write a byte of SRAM in 45 ns instead of the
Flash’s average 27 000 ns, and spending 6600 pJ instead of the Flash’s
1 800 000 pJ, and it really is random access both for reading and
writing, which the Flash very much is not.

The CY7C1020D-10VXI also mentioned therein is a smaller parallel CMOS
SRAM with 10-ns access time and fifteen times higher cost per byte.
But it’s enormously more power-hungry, too: 3 mA rather than 1 μA in
standby, according to the datasheet, and *80 mA* when being accessed
at 100 MHz, which (at 5 V) is *400 mW*.  That’s still less energy per
access when going full tilt — 4000 pJ per byte instead of
6000 pJ — but the 3000-times-higher high quiescent draw means this
chip has no place in milliwatt computing.

Another option is SPI SRAM chips like the [US$1.20 Microchip
23K256][68], which has 32 kibibytes of SRAM, a 20MHz SPI interface,
and runs on 3.3V; it uses 10 mA (33 mW) reading at 20 MHz (20Mbps) and
idles at 1 μA (typical).  The datasheet doesn’t specify the write
power usage; if we assume it’s the same as the read power usage, then
they’re both around 1700 pJ per bit, or 13 000 pJ per (sequential)
byte.  (Random access costs four times as much.)

[68]: https://www.digikey.com/en/products/detail/microchip-technology/23K256-I-P/2001112

“Quad SPI” chips like the [US$2.10 Microchip 23LC1024][69], with 128
KiB, are generally faster.  It runs at 2.5–5 V and up to 20 MHz,
purporting to use only 3 mA (10 mW at 3.3 V) reading at 20 MHz.
Moreover, it can transfer data at 80Mbps instead of 20Mbps, so this
ends up being 120 pJ/bit or 1000 pJ/byte, nearly as low as reading the
GD SPI NOR Flash above.  Typical standby current is higher at 4 μA, but
not so high as to matter here.

[69]: https://www.digikey.com/en/products/detail/microchip-technology/23LC1024-I-SN/3543084

### NAND Flash ###

NAND Flash requires orders of magnitude less energy than NOR to write
to, and it also costs orders of magnitude less per byte to buy it.

SD cards have NAND flash on them and can normally write with
bandwidths of several megabytes per second, with latencies in the tens
of μs.

Four promising bare NAND chips are the [US$3 104MHz quad SPI
128-mebibyte Winbond W25N01GVZEIG TR][70], the [US$2.50 120MHz
quad-SPI 128-mebibyte GigaDevice GD5F1GQ4RF9IGR][71], the [US$1
45-ns/25000-ns 48-pin parallel 128-mebibyte Cypress
S34MS01G200TFI900][72] (whose datasheet has been memory-holed from
Cypress’s site but [I found a datasheet for a clone on Mouser
via Yandex][73] after filling out a captcha in Cyrillic), and the
[US$2.30 50MHz quad-SPI 128-mebibyte Micron MT29F1G01ABBFDWB-IT:F
TR][74] whose [datasheet I found the same way][75].

[70]: https://www.digikey.com/en/products/detail/winbond-electronics/W25N01GVZEIG-TR/5803931
[71]: https://www.digikey.com/en/products/detail/gigadevice-semiconductor-hk-limited/GD5F1GQ4RF9IGR/9484745
[72]: https://www.digikey.com/en/products/detail/cypress-semiconductor-corp/S34MS01G200TFI900/4833856
[73]: https://ru.mouser.com/datasheet/2/980/002-03238-1669830.pdf
[74]: https://www.digikey.com/en/products/detail/micron-technology-inc/MT29F1G01ABBFDWB-IT-F-TR/6135561
[75]: https://datasheet.octopart.com/MT29F1G01AAADDH4-IT:D-Micron-datasheet-11572380.pdf

The SkyHigh Memory datasheet for the S34MS01G2 claims SLC, 25 μs (max)
for random access, but 45 ns (min) for sequential access, and there
are versions with 8-bit and 16-bit I/O buses (this is the 8-bit
version); for writing, it takes 300 μs to program a 2048+64-byte page
and 3 ms to erase a 64-page block.  It uses the same 8-bit or 16-bit
bus for address and data bits, so I have no idea why it has 48 pins;
only 23 are used in the 8-bit version, and 31 in the 16-bit version,
and 8 of those are power pins!  So you only need 15 GPIO pins to talk
to it.

To access the memory, first you clock in 1–4 command bytes, and then
you feed in the address on the bus in four successive clock cycles
while signaling the desired operation with some other control lines.
A read command copies a page from the Flash into a buffer (in
25000 ns, apparently), signaled by the “ready/busy” pin going high,
and then you can read out a word (8 bits on this chip, but 16 bits on
16-bit parts) every 45 ns, as you choose to toggle the read-enable
pin.

*Writing* the memory may fail and need to be retried — at a different
page address, probably.  Also typically NAND chips have about 2% bad
bits.

It supports prefetching pages so you can overlap the 25000-ns
copying-into-buffer with your reading of the previous page, and
similarly you can send it data you’re planning to write to another
page while it’s still burning in the data you sent before.

So it looks like kind of a pain to talk to, but still easier than
you’d think from the 48-pin package; but how much *power* does it use?

It runs on 1.8 volts, and it claims to use 15 mA typical, 30 mA max,
for all of read, program, and erase!  That can’t possibly be correct.
(Can it?)  And 10 μA typical standby current (“(CMOS)”, whatever that
means).

But if that *were* correct, it would work out to 27 mW for 22 million
bytes *read* per second, assuming the 25000-ns overlap thing works
out.  So that’s 1.2 nJ per byte, three times the cost of reading from
NOR.  *Writing* 131072 bytes (not counting the 64) supposedly requires
21.2 ms at the same 27 mW, plus 5.9 ms to clock them into the device,
potentially overlapping, which would be only 4.4 nJ per byte.
[Avinash Aravindan of Cypress explains that this two orders of
magnitude faster erasure, using much lower power, is characteristic of
NAND][76], and [Edouard Haas has an insightful article on the same
subject][77], where he points out among other things that NOR permits
single-byte write operations, and in [his QSPI NAND article][78] he
points out that NOR uses 100 times more energy for erase+write than
NAND.

[76]: https://www.embedded.com/flash-101-nand-flash-vs-nor-flash/
[77]: https://www.jblopen.com/nor-vs-nand-so-you-think-you-know-the-music/
[78]: https://www.jblopen.com/qspi-nand-intro/

The “obsolete” GD5F1GQ4RF9IGR is another 1.8 V 128-mebibyte NAND
Flash, but this time SPI/dual-SPI/QSPI, with broadly similar
performance: 400 μs (700 μs max) to program a (2048+128)-byte page,
3000 μs to erase a 64-page block, 80 μs to read a page, using 40 mA
maximum active current (again, for all of read, program, and erase, so
I guess that *can* be real) and 90 μA standby current.  It has
internal ECC, so you don’t have to worry about bad bits.  It actually
looks like *higher* bandwidth than the 8-bit parallel chip — 120 MHz
and quad-SPI gives you 60 megabytes a second instead of 22 — but its
internal slowness more than compensates.  It doesn’t seem to have the
pipelining feature the Cypress part has to overlap fetches with reads,
or burns with loads.  The Digi-Key page linked above is the 8×6mm
8-VLGA package.

This works out to 72 mW and 80+34 μs = 114 μs to read a page, so 56 ns
and 4 nJ to read each byte (again, disregarding the “extra data”);
writing a 131072-byte block takes 3 ms to erase, 25.6 ms to program
(plus 34 μs per page to clock in the data, which might add another
2.2 ms) for 28.6 ms: 220 ns per byte, which means 16 nJ per byte.

I’m going to assume the other two gibibit NAND chips are similar.

### More Ambiq MCUs ###

This is a pricey option, but for RAM, it might actually be the most
reasonable one.  Ambiq doesn’t make memory chips, but for 68 μA you
can stick another Ambiq Apollo MCU next to the first one and get
another 384K of SRAM, and then you can communicate with it at tens of
megabytes per second, though the capacitive load of traces in between
the chips can become a problem.  Charging 1 pF of parasitic
capacitance to 3.3 volts costs 5.4 pJ; doing it at 10 MHz (and then
dumping the charge to ground) costs 54 μW, and in this context that is
a significant cost.  Still, I think we can estimate that communicating
a byte between the processors will cost on the order of 50 pJ.  This
is at least an order of magnitude cheaper than anything offered by
conventional CMOS memory chips.

This suggests that, although we probably want at least NAND flash in
our low-power system both for mass storage and for stable memory, it
may be more effective to add more RAM by turning it into a cluster
rather than by adding RAM chips.  Making it a cluster costs a little
more, and it makes writing the software more complicated, but it also
offers a lot of opportunities for reducing costly off-chip
communication.

In addition to the Apollo3 Blue microcontroller on the Sparkfun board
above, there's apparently also [an Apollo3 Blue Plus with 768KiB of
RAM for US$4.82][105], but only as a BGA.  That’s about the same price
per byte as dedicated SRAM chips in conventional CMOS, although those
are much faster.

[105]: https://www.ambiq.top/en/apollo3-blue-plus-mcu-768kb-108pin-bga

Batteries
---------

Maybe you need batteries.  If so, what kinds of batteries are there,
and what are their advantages and disadvantages?

### Lead-acid batteries: 9–36 kJ/US$ at retail, mostly around 20 kJ/US$ ###

Lead-acid batteries are generally cheaper than the lithium-ion type,
even in 02021.  At the very low end joules per buck drops
dramatically; [a 1.3-amp-hour 12V HiStarX LA612 battery goes for
AR$900][0]; at AR$147/US$ that’s US$6.10 for 56 kJ, or 9.2 kJ/US$.  By
contrast, a [2-kg 7-amp-hour Risttone battery goes for AR$1220][1],
US$8.30, 300 kJ, 36 kJ/US$.  A [24-amp-hour deep-cycle golf-cart Press
PR12240D goes for AR$9000][2], US$61, which is getting low again: 17
kJ/US$; while car starter batteries are in theory much cheaper, like
[a Rosler 65-amp-hour starter goes for AR$4900][3], US$33, 84 kJ/US$,
but of course you can only use a fraction of that before you start
killing the battery.  Even with starter batteries, prices per joule go
way up at the low end: [a Yuasa 5.3-amp-hour 1.5kg 12N5-3B 12-volt
motorcycle starter battery][10] (230 kJ) is [sold for AR$2500][11]
(US$17, 13 kJ/US$).

[0]: https://articulo.mercadolibre.com.ar/MLA-904920119-bateria-de-gel-12v-13ah-recargable-luz-emergencia-ups-_JM
[1]: https://articulo.mercadolibre.com.ar/MLA-871599822-bateria-de-gel-12v-7a-amper-sistema-alarmas-cerco-electrico-_JM
[2]: https://articulo.mercadolibre.com.ar/MLA-671410956-bateria-12v-24ah-press-ciclo-profundo-moto-carros-golf-_JM
[3]: https://articulo.mercadolibre.com.ar/MLA-856727008-bateria-12x65-super-oferta-nueva-_JM
[10]: https://www.yuasa.es/batteries/moto-e-powersport/convencional-de-12-voltios/12n5-3b.html
[11]: https://articulo.mercadolibre.com.ar/MLA-853988819-bateria-moto-yuasa-12n5-3b-motomel-c-110-0518-_JM

Digging further suggests higher-capacity options like [the 2.8-kg
9-amp-hour Moura 12MVA-9][19] for AR$2500 (US$17, 390 kJ, 23 kJ/US$),
or, in the extreme, [the Ultracell UCG 100-12 100-amp-hour deep-cycle
gel cell][18] for AR$38400 (4.3 MJ, US$261, 17 kJ/US$).

[18]: https://articulo.mercadolibre.com.ar/MLA-852742149-bateria-ciclo-profundo-gel-12v-100ah-ultracell-ppanel-solar-_JM
[19]: https://articulo.mercadolibre.com.ar/MLA-867421155-bateria-moura-12v-9ah-gel-ups-alarmas-paneles-solares-_JM

### Low-power lithium-ion batteries are more expensive at 3–16 kJ/US$ ###

Lithium-ion batteries are trickier to buy because of the profusion of
fakery, but [this Sanyo NCR20700b cell is specified at 4250mAh and
3.7V for AR$2500][4], which would be US$17 and 57 kJ, or only 3.3
kJ/US$.  (The seller falsely claims it’s an 18650.  It’s tested at
[3.7–4.2 amp hours at 0.2–15 amps of discharge rate][12] by what I
think is an independent tester, who weighed it at 61 g; this 53 kJ
then works out to 870 kJ/kg.)  But there
are a lot of fake lithium-ion batteries like this [UltroFite GH 18650
“6800 mAh” which sells for AR$427][5], which would be 91 kJ, US$2.90,
and 31 kJ/$, nearly an order of magnitude cheaper and up in the
lead-acid price range.  (Lithium-ion batteries are already immensely
cheaper per watt or amp rather than per joule, but so are capacitors.)
USB “power banks” are even less controlled, but much more convenient
to use; [this Tedge H555 claims 10 amp-hours for AR$1700][6],
US$11.50, 180 kJ, 16 kJ/$, and it probably has 18650s inside, which
could be replaced, while [this offbrand Libercam powerbank claims 20
amp-hours for AR$1500][9] and is too thin to contain 18650s.  I'm
guessing it’s fake.

My “10050 mAh” powerbank (180 kJ) can recharge my phone about four
times, which can keep it alive for about a week.

[4]: https://articulo.mercadolibre.com.ar/MLA-756391264-panasonic-sanyo-ncr20700b-4250mah-10a-20700-ion-litio-37v-_JM
[5]: https://articulo.mercadolibre.com.ar/MLA-816550268-pila-bateria-recargable-18650-6800mah-37v-para-linterna-_JM
[6]: https://articulo.mercadolibre.com.ar/MLA-795347543-cargador-bateria-portatil-powerbank-2-usb-10000-mah-tedge-_JM
[9]: https://articulo.mercadolibre.com.ar/MLA-856270207-power-bank-cargador-portatil-20000-mah-celular-micro-usb-_JM
[12]: https://lygte-info.dk/review/batteries2012/Sanyo%20NCR20700B%204000mAh%20%28Red%29%20UK.html

### High-power lithium batteries are down around 1.4–1.6 kJ/US$ but 25 W/US$ ###

I thought maybe the motorcycle starter batteries were about to get
murdered by lithium, since lithium is so great at rapid discharge, but
it’s not so clear.  The Yuasa 12N5-3B above is only 35 or 39 cold
cranking amps, depending on who you believe, which is only like 450
watts (26 W/US$).  At 3.7 volts and 15 amps the Sanyo cell, which is
the same US$17 price, delivers only 56 watts; you’d need 9 of them (9
times the price!)  to deliver the same starter power as the lead-acid
beast, though admittedly the resulting 0.550 kg of lithium battery is
noticeably lighter the 1.5 kg of the Yuasa battery.

However, 4 amp hours and 15 amps is a discharge rate of only “3.75C”,
and [lithium-ion batteries for drones][13] come in “C ratings” of
“15C”, “20C”, “25C”, “30C”, and even “50C”, though at a substantial
penalty in joules per buck.  Does this make them competitive for
starting motorcycles?  Well, a [Blomiky SDL-853562 7.4V 1600mAh 25C
radio-controlled car battery][14], for example, is listed for AR$6900
(US$47) and hypothetically ought to hold only 43 kJ (0.91 kJ/US$) but
be able to deliver 40 amps.  But that’s still only 300 watts, and it
costs more than twice as much as the lead-acid battery.  Cheaper drone
batteries like [this Kitch Tech 30C 7.5-V 1200-mAh YZ-803063 for
AR$3500][15] come closer — if real, that’s 32 kJ for US$24 (1.4
kJ/US$), 36 amps, and 270 watts, but lead-acid still beats it by a
substantial factor.  [This Zippy 25C 2200mAh 11.1V drone battery][16]
can purportedly deliver 610 watts (or 850 watts, 35C, in bursts) and
is listed at only AR$4700 (US$32, 2.7 kJ/US$).  850 W / US$32 is
27 W/US$, within a stone’s throw of the Yuasa price — but far from
dramatically undercutting it.

Moreover, [advertised C ratings are often fake, even outside
Argentina][17].

[13]: https://electronica.mercadolibre.com.ar/drones-accesorios-repuestos-baterias/
[14]: https://articulo.mercadolibre.com.ar/MLA-843144652-bateria-lipo-74v-1600mah-25c-t-connector-blomiky-_JM
[15]: https://articulo.mercadolibre.com.ar/MLA-873577542-bateria-pila-lipo-yz-803063-1200mah-75v-30c-drone-drones-_JM
[16]: https://articulo.mercadolibre.com.ar/MLA-741554734-bateria-lipo-zippy-compact-2200mah-3s-25c-111v-xt60-_JM
[17]: https://oscarliang.com/lipo-battery-c-rating/

### Lithium thionyl chloride batteries might last decades ###

[Lithium thionyl chloride batteries][79] are really good at low
self-discharge (0.5%–1% per year, self-discharging about 20% in 9
years — according to their plot, if you discharge their battery in
1500 hours at 2 mA, you get 2.6 Ah, and if you discharge it at 25 μA,
it takes 80000 hours, or 9 years, and yields 2.1 Ah, so about 20% of
its capacity was lost to self-discharge) and high energy density
(710 Wh/kg).  About 0.175% of them fail each year, according to
[Tadiran’s brochure][80].  “High cost and safety concerns limit use in
civilian applications. Can explode when shorted. Underwriters
Laboratories require trained technician for replacement of these
batteries,” says Wikipedia.

[79]: https://www.jauch.com/blog/en/advantages-and-special-features-of-lithium-thionyl-chloride-batteries/
[80]: https://tadiranbatteries.de/pdf/Technical-Brochure-LTC-Batteries.pdf

Sadly, it seems that they are not available on MercadoLibre.

Strategies for avoiding batteries
---------------------------------

XXX

### Batch processing can wait until the sun is shining ###

For batch processing, it might make sense to wait until the daytime:
an average watt of batch-processing power might be 7 watts during the
15% of the time that the sun is shining full force, and 7 Wp of solar
panels only costs US$2.30, which is a lot less than US$6.60.  Also you
don’t need a high-power battery charge controller.

### Lower power opens up alternative power sources and stores, like supercaps ###

As I pointed out in Dercuano, a pullstring can yield 500 mm of pull at
50 N, which is 25 J, which (if harnessed with a dynamo) would run the
laptop for a second or two, but that’s enough to run a 10-milliwatt
computer for 40 minutes, or a 100-milliwatt Swindle for 4 minutes.
For that you don’t need a battery; a capacitor will do.

You might think to go with ceramics, but that’s still impractical for
a pocket computer or laptop.  Although you can get a [25V 4.7μF X5R
0805 Samsung cap for 2.2¢][59] or a [25V 10μF X5R 0805 Taiyo Yuden cap
for 4.1¢][60], either in quantity 1000, ½CV² at the rated voltage
works out to 1.5 mJ and 3.1 mJ respectively, so you’d need thousands
of caps.

Getting to 25 J at under 50 V requires 10000 uF, and for that you need
electrolytics or supercaps.  You can get [22000-μF TDK electrolytics
for a buck fifty][61], but those caps are only 16V, so you’d need five
of them (or 18 of them to have a comfortable 2× margin on the voltage
rating), and they’re a bit bulky: 30 mm diameter, 32 mm tall.

[59]: https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL21A475KAQNNNE/3886902
[60]: https://www.digikey.com/en/products/detail/taiyo-yuden/TMK212BBJ106KG-T/2714163
[61]: https://www.digikey.com/en/products/detail/epcos-tdk-electronics/B41231C4229M000/3493609

Electrolytics are really optimized for charge/discharge frequencies of
60Hz up to a few kHz, though.  This application has frequencies closer
to a millihertz, albeit kind of sawtoothy.  So a supercap like the
[US$4 5.5V 5F Illinois Capacitor DGH505Q5R5][62], the [US$5 5V 1.5F
Maxwell BMOD0001 P005 B02][63], or the [US$2.50 5.5V 1.5F Illinois
Capacitor DGH155Q5R5][64] would probably work; these are rated at 75
J, 18 J, and 22 J, respectively, and they’re pretty small, in the last
case 12 mm × 17 mm × 8.5 mm.

Supercaps are notorious for leakage, but that’s in different contexts;
the Maxwell supercap, for instance, is rated for 5 μA, which is a loss
of 12 mV per hour, so it will lose its charge in a matter of weeks.

Another reason to use two or more is to allow faster charging — the
Maxwell cap is only rated for 3.1 A of one-second surge current, and
the DGH155Q5R5 for 2.8 A, so your pull-cord charge would need to take
a few seconds.  The DGH505Q5R5 is rated for 8.4 A, though.  Smaller
supercaps might include [the US$1 1F 2.7V Eaton HV0810-2R7105-R][65],
which is rated to hold 3.6 J, but rated for 1.1 amps of pulse current,
8 mm in diameter, 13.5 mm long, and 1.2 grams.  You’d need to use
about 8–16 of these, giving you 8.8–17.6 amps of pulse current at up
to 2.7 V, which would probably be enough for the pull cord.

Me, I’d be tempted to vastly oversize the capacitor bank, but that
could be dangerous.

At 3.1 A, 5.0 V, and 1.5 F, you could fully charge the 3.4 g Maxwell
supercap ([datasheet][63a]) to its 18.8 J full charge (5.5 J/g) in
2.4 seconds.  It’s rated for 500,000 cycles, 4 years shelf life
uncharged, or 10 years DC life at room temperature.  I think all of
these are typical of supercaps.

[62]: https://www.digikey.com/en/products/detail/illinois-capacitor/DGH505Q5R5/7387525
[63]: https://www.digikey.com/en/products/detail/maxwell-technologies-korea-co-ltd/BMOD0001-P005-B02/946807
[63a]: https://web.archive.org/web/20210415110650/https://www.maxwell.com/images/documents/5_0_1_5F_Module_ds_datasheet.pdf "Maxwell BMOD0001 P005 B02 datasheet"
[64]: https://www.digikey.com/en/products/detail/illinois-capacitor/DGH155Q5R5/7387513
[65]: https://www.digikey.com/en/products/detail/eaton-electronics-division/HV0810-2R7105-R/3878078

To charge the capacitor from the pull cord you need not just a dynamo
but also something like a MPPT buck converter that regulates its
output voltage to just above the present voltage of the capacitor bank
(any voltage drop from the capacitor bank’s ESR is, after all, wasted,
and produces heat), then varies it a bit to do MPPT on the pull-cord
dynamo.  At some point, if overloaded as I did with the regenerative
braking on Trevor Blackwell’s scooter, it might need to just
open-circuit the dynamo or connect it to a power resistor instead, but
smoothly feathering into that by easing off of the maximum power point
would be better than suddenly releasing all mechanical resistance.
(That is what the scooter did, falling out from under me, but I think
the mechanism was that I blew a fuse.)

Prospects for energy-independent computing
------------------------------------------

So I was thinking it might be worthwhile to buy a 12-volt gel cell
like those mentioned above and rig up some power supplies for offline
computation.  The AR$1200 7-amp-hour Risttone battery mentioned above
ought to be able to run this laptop at 15 watts for 6 hours (given
appropriate boost conversion), or recharge this cellphone about 6
times, and there might be better deals out there too.  Two or three
such batteries, or a single larger battery, could perhaps power the
laptop, or a fan, through a long night.

Standard photovoltaic solar panel modules are 990 mm × 1650 mm or
thereabouts, deliver 200–400 Wp, and, at retail in Argentina, cost
[AR$12000][20]–[AR$24000][21] (US$80–160), on the order of 30¢–40¢/Wp.
Smaller panels like [this AR$3200 20-Wp jobbie][22] do exist but cost
more per watt (US$22, US$1.09/Wp in this case).

[20]: https://articulo.mercadolibre.com.ar/MLA-882723840-panel-solar-solamerica-260w-tipo-250w-270w-280w-12v24v-_JM
[21]: https://articulo.mercadolibre.com.ar/MLA-898045941-panel-solar-jinko-solar-mono-perc-405w-media-celda-_JM
[22]: https://articulo.mercadolibre.com.ar/MLA-718610857-panel-pantalla-solar-20w-watts-policristalino-111-amper-amp-_JM

Suppose the solar capacity factor for residential solar panels here is
15%, so 100 Wp delivers 15 watts average.  (It’s fairly sunny here in
Buenos Aires, but we get more clouds than California and Arizona
deserts with their 29% and 25% capacity factors, and also residential
panels may have to deal with shadows and suboptimal angling.)  And
suppose we want 24 hours of “autonomy”, meaning, we can keep computing
even when it’s super cloudy; so a watt of average usage requires 24
watt-hours (86 kJ) of battery.

So each watt of usage requires 86 kJ of battery, which at 20 kJ/US$
costs US$4.30, plus 7 Wp of solar panel, about US$2.30 at retail, for
a total of US$6.60, plus some amount of power electronics.  So running
the laptop all the time at 15 watts would cost a bit over US$100 of
equipment; at 32 watts we’re talking US$210.  I paid AR$50k (at the
time, about US$320) for the laptop a couple months ago.  So powering
it autonomously nearly doubles its cost!  Also, 32 watts average at a
15% capacity factor means 213 watts of solar panel, which is a whole
square-meter panel.  It would occupy a significant fraction of the
balcony and might attract unwanted attention.

In file `garden-light-panel.md` in Derctuo, I tested a 38-mm-square
amorphous panel at 8 mW in full sunlight, though a more careful MPPT
calibration might yield more, and I didn’t measure the “full”
sunlight.  Surprisingly, unlike some other amorphous panels, I wasn’t
able to get a usable amount of power from it under indoor lighting
conditions."
