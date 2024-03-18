![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/0247543a-be5f-4724-aee7-3244f2dd9ad3)

---
Origins of this Project - to my best recollection (and occasionally updated, as recently done here)
---

3/11/2024- Update to my previous "origin" story. In June 2011, Liliputing posted an [article](https://liliputing.com/pixel-qi-suggests-low-power-tablets-could-be-powered-by-1w-solar-panels/) titled, "Pixel Qi suggests low power tablets could be powered by 1W solar panels,"  where I [commented](https://liliputing.com/pixel-qi-suggests-low-power-tablets-could-be-powered-by-1w-solar-panels/#comment-218940429) on the original article. That link I posted was to a 6/2011 [TechCrunch article](https://techcrunch.com/2011/06/04/first-solar-powered-laptop/), documenting an Industrial designer, "[Andrea Ponti](https://www.andreaponti.com/index.html)'s Luce Solar Panel Powered PC." Luce in Italian means "Light." I don't claim to have been the first to have the idea for a solar powered laptop. I just want(ed) and (still) want the idea to come to fruition.

I ~~first~~ later conceived of this project after visiting and [reviewing](https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/2011%20Maker%20Faire%20%E2%80%93%20Queens%2C%20NYC%20_%20Fujimoto.pdf
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

In early-2023, I recall listening to a audio interview with Richard Barbook https://www.youtube.com/watch?v=KyoxwUmQBns. Being quite wired to the maker community in the past 15 years, I did not really pay much attention to the political differences of Silicon Valley's origin and European constitutions:

"Unlike its American equivalent, the French revolution went beyond economic liberalism
to popular democracy. Following the victory of the Jacobins over their liberal opponents
in 1792, the democratic republic in France became the embodiment of the ‘General Will’.
As such, the state was believed to defend the interests of all citizens, rather than just to
protect the rights of individual property-owners. The discourse of French politics allows
for collective action by the state to mitigate – or even remove – problems encountered by
society. While the Californian Ideologues try to ignore the taxpayers’ dollars subsidising
the development of hypermedia, the French government can openly intervene in this sector of the economy.46

Although its technology is now increasingly dated, the history of Minitel clearly refutes the
anti-statist prejudices of the Californian Ideologues – and of the Bangemann committee.
The digital future will be a hybrid of state intervention, capitalist entrepreneurship and
DIY culture. Crucially, if the state can foster the development of hypermedia, conscious
action could also be taken to prevent the emergence of the social apartheid between the
‘information rich’ and the ‘information poor’. By not leaving everything up to the vagaries
of market forces, the EU and its member states could ensure that every citizen has the opportunity 
to be connected to a broadband fibre-optic network at the lowest possible price."
https://networkcultures.org/wp-content/uploads/2015/10/0585-INC_NN10-totaal-RGB.pdf


It is within this context that I see an opportunity for solar powered mobile devices to become the 21st century upgrade from Minitel- a wireless, local-first, decentralized and distributed means to connect the information-poor global economy.

---
Why this project has not been funded for more than 3 years:
---

Despite submitting several grant applications, it exceeds the risk-taking of the Lower-Level Agents:
![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/ef2b337b-36e4-4f7e-a5c7-0eeb70849b49)

from: "The agent principal problem" : https://www.strangeloopcanon.com/p/the-agent-principal-problem

Amount of risk of this project (perceived or real): 

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/1885064b-6278-4044-84ff-e1f171d3dd8f)

If you'd like to contribute to this project, first look for ways to lower the perceived or real risks. This repository is not an ideology, but a pursuit of ideas.

A great [Substack](https://dgardner.substack.com/p/the-history-of-technology-is-most
) post today mentioned Kranzberg's six laws of Technology:

"Technology is neither good nor bad; nor is it neutral.

Invention is the mother of necessity.

Technology comes in packages, big and small.

Although technology might be a prime element in many public issues, nontechnical factors take precedence in technology-policy decisions.

All history is relevant, but the history of technology is the most relevant.

Technology is a very human activity – and so is the history of technology."

https://en.wikipedia.org/wiki/Melvin_Kranzberg#Kranzberg's_laws_of_technology 

http://pantaneto.co.uk/the-decline-of-unfettered-research-andrew-odlyzko/

https://en.wikipedia.org/wiki/The_Logic_of_Collective_Action

https://en.wikipedia.org/wiki/Collective_action_problem

"A collective action problem or social dilemma is a situation in which all individuals would be better off cooperating but fail to do so because of conflicting interests between individuals that discourage joint action.[1][2][3] The collective action problem has been addressed in political philosophy for centuries, but was most clearly established in 1965 in Mancur Olson's The Logic of Collective Action.

Problems arise when too many group members choose to pursue individual profit and immediate satisfaction rather than behave in the group's best long-term interests."

"David Hume provided another early and better-known interpretation of what is now called the collective action problem in his 1738 book A Treatise of Human Nature. Hume characterizes a collective action problem through his depiction of neighbors agreeing to drain a meadow"

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

https://media.ccc.de/v/vcfb2023_-_193_-_en_-_202310151500_-_ignored,_disposed_of,_revived_-_michael_engel

https://multicores.org/lisa/VCFB2023.pdf (great history on the early hardware of the Lisa and Apples)

https://youtube.com/watch?v=0OlEHIAIWn4 "No experience in life is wasted as an artist if remembered and used later" 

by that logic, Steve Jobs was an artist - calligraphy in the Macintosh.

"Reed College at that time offered perhaps the best calligraphy instruction in the country. Throughout the campus every poster, every label on every drawer, was beautifully hand calligraphed. Because I had dropped out and didn’t have to take the normal classes, I decided to take a calligraphy class to learn how to do this. I learned about serif and sans serif typefaces, about varying the amount of space between different letter combinations, about what makes great typography great. It was beautiful, historical, artistically subtle in a way that science can’t capture, and I found it fascinating.

None of this had even a hope of any practical application in my life. But 10 years later, when we were designing the first Macintosh computer, it all came back to me. And we designed it all into the Mac. It was the first computer with beautiful typography. If I had never dropped in on that single course in college, the Mac would have never had multiple typefaces or proportionally spaced fonts. And since Windows just copied the Mac, it’s likely that no personal computer would have them. If I had never dropped out, I would have never dropped in on this calligraphy class, and personal computers might not have the wonderful typography that they do. Of course it was impossible to connect the dots looking forward when I was in college. But it was very, very clear looking backward 10 years later."

https://www.youtube.com/watch?v=b9_Vh9h3Ohw Springboard: the secret history of the first real smartphone (Full Documentary)


------

https://litverse.substack.com/p/steve-jobs-vs-the-haters

https://www.directors-institute.com/post/whystevejobswasfiredbyapple 

https://newsteve.substack.com/p/most-ideas-come-from-previous-ideas My recent writeup with a tangent into Biology

"Looking back, some have questioned whether Apple's board of directors could have done more to retain Steve Jobs in 1985. Sculley himself later acknowledged Jobs' effective leadership and called him "the best CEO ever," admitting that he underestimated Jobs' visionary potential at the time. The firing of Jobs also raises questions about the board's decision-making and overall company strategy. Could they have chosen different approaches or members to better handle the situation?"

https://www.latimes.com/business/technology/la-fi-tn-how-the-first-macintosh-failed-and-still-changed-computing-20140123-story.html

Imagine an open source project, that, uses a unified design until each milestone is complete. Job's logic here could be like the Cathedreal in the Bazaar. The Bazaar houses the Cathedral, but temporarily cannot access the Cathedral.

​
"Certainly all historical experience confirms the truth - that man would not have attained the possible unless time and again he had reached out for the impossible." -Max Weber

"No worthwhile human achievement has ever been instigated on the basis of demonstrable cost effectiveness." - Adrian Bowyer

My Github draft got lost because I accidentally cancelled a tab closing and undid a nearly complete commit, but I had written a substantial paragraph on how cost is a secondary consideration in the progression of inventions, citing Bowyer, but also analyzing Xerox's Chuck Thacker and Apple's Woz "middle stage" adaption of IBM/PDP (e.g. 945/360, PDP-6) systems into novelties-  portable Compaq-like consumer tech (though they weren't the only ones- as [Landley.net](https://landley.net/notes.html#28-10-2023) has a better history on that- he mentions Paul Allen and Mitch Kapor, which I read much less into, but that they had identified that complexity was no longer the only drafting stage.): 

"The bestselling computer in the world was the PDP-8 from 1973 until it was displaced by the Apple II around 1979, and in its entire production run the PDP-8 sold a grand total of around fifty thousand units EVER, meaning there was no consumer base for a "software industry" before microcomputers. Most software before that was either produced by hardware manufacturers bundling software with the hardware they sold, or by local staff maintaining an installation, or collaborations like produced Multics. What little commercial software got created was bespoke development tailored to specific installations because there was no other business model yet due to a lack of customers to sell to. (Not a lot of speculative development when your total potential worldwide market for PDP-6 software was 23 machines, you talk to them FIRST and get paid before putting in the engineering time, and then you DO the work on their hardware because you haven't got one.) The first computer to sell a million units was the Commodore VIC 20 at the end of 1982, and "the computer" was Time's man of the year for 1982. The Apple vs Franklin legal battle happened when it did because a shrinkwrap software finally had a potential customer base THAT YEAR. People fought over the money once there actually was money."

To focus on two engineers:

" The obvious difficulty in this method--the only method the engineering world had known until recently--was that the more complex the problem, the more complicated the hardware setup needed to address it. In this world, the most gifted engineers were those who could puzzle out novel ways to reduce the number of components by, say, 10 percent. And it was in this particular type of simplification that Woz had shown almost supernatural talent." from Infinite Loop (1999) by Michael Malone https://archive.nytimes.com/www.nytimes.com/books/first/m/malone-loop.html

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/4b1c7bc3-b18d-44a5-af97-b4ab2916ae05) 

from [The Dealers of Lightning: Xerox PARC](https://www.amazon.com/Dealers-Lightning-Xerox-PARC-Computer/dp/0887309895) and the Dawn of the Computer Age Paperback – (1999) by Michael A. Hiltzik (Author)

A careful review shows that they both understood that cost reduction was the future of Silcon Valley (and since PARC was primarily focused on 10-year long research & dev, the marketability of the Xerox Star would arrive too late, thus Jobs accelerated development by completing their menu screen and cost reduction, as stated by Jobs in an interview in 1990 to the WGBH Boston: https://www.youtube.com/watch?v=L40B08nWoMk  

To tie this back to the hypothesis stage, the phrase "talk is cheap" isn't to devalue talk, but to acknowledge that cost is an important factor in even the exploratory stage. And therefore "talk is cheap" is another way of rapidly prototyping (hence Bowyer's RepRap concept) various iterations of expensive ideas in a way that doesn't require actually making them all, but rather exchanging them either via market surveys/research, forums, or prior product feedback to discover market or business inefficiencies in both availability of products and underserved markets which sometimes actually have viral, general purpose applications after passing through the [Gartner hype cycle](https://en.wikipedia.org/wiki/Gartner_hype_cycle). In other words, "Think Rich" is not delusions of grandeur, but it's an inalienable right to discuss concepts and products as ideas cannot be patented, something that creative people do not often have a shortage of (and sometimes are better off working on multiple projects if they have [writers block](https://www.hottakes.space/p/accessing-your-creative-reserves)/engineer's block)

The cost of prototypes, toys, and research, are, according to Byrne Hobart, "But there's a feature of the outside world that also has a major impact: solutions-in-search-of-a-problem and toys-in-search-of-real-world-use are both less costly and more valuable in a world of lower real interest rates." (A Solution in Search of a Problem" is a Low-Rates Phenomenon
 12/12/20222) 

I had written something in my draft about I/O shields, and how many new SBC boards such as Raspberry Pi, Orange Pi and even AMD, could share more similar [form factors](https://hackaday.io/page/21232-platos-ideal-world) to support even long-side backplates (as in AMD's case)  if they developed something like a mini i/o shield (1/6 scale perhaps).

![image](https://github.com/EI2030/Low-power-E-Paper-OS/assets/76194453/e2e89a73-c420-4dce-967c-feebfec8f22e)

This little "cosmetic" detail could support more reusability and dual-use integration into laptops such as the PiTop, which do not require major modification of chassis if the rectangular I/O shield can be limited to a narrow segment of the chassis. As mentioned in my mobile-ITX [blog](https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/Mobile-ITX%20and%20ATX-like%20standards%20for%20SBCs%20and%20mobile%20motherboards.pdf) post, degrees of freedom are a chemistry concept that chemist know more about, and architects of SBCs have far more leeway into rearranging components that do not require convoluted overpasses of wires above heatsinks to reach the backplate I/O.

 ---

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

One of the key differences from this project and the Raspberry Pi is that micro-SD loaded OSes like Raspberry Pi OS are extremely slow, and do not compare to the true, baremetal capabilities of even the armv6 in the Raspberry Pi Zero. loading Raspup Buster 8.2.1  or Tinycore linux on a Raspberry Pi 3 on 512 MB RAM runs faster on RAM than loading apps from microSD.

The early Nokia phones had immediate response times when navigating the Symbian OS. The modern operating systems of today adopt an omnibus of kernel modules, that prevent replicating the user experience of earlier phones and desktops. Phones attempt to run at even faster speeds to keep up with the hundreds of processes, yet lag behind the simplified OS of a generation ago.

What would be ideal is to focus efforts on operating systems that feature HMI and userspace applications while retaining the benefits of the RTOS task scheduling. An analogy would be the UDP vs TCP comparison. UDP is a connectionless protocol- it does not require connections to restart after losing a byte to a corrupt transmission packet. Rather than have hundreds of process IDS waiting to be completed, the user could wait for a kernel task to complete, and if not busy, the syscall could complete the user's request. I call it the "use it or lose it" concept. Which the kernel would be programmed to skip a task that would take too long to process. It would be better to have real time notifications of kernel tasks (likea sysmonitor) rather than an hourglass (or no indicator at all) to observe system health- this would significantly benefit microcontrollers that have limited RAM (2-4MB usable).

Another focus is to perhaps limit the amount of POSIX compliance in an OS to further reduce OS size. 

A third focus is compatibility with plug and play screens that do not emit a backlight, to save power and to reduce eyestrain.
A reflective display with a variable refresh rate- 1-30hz, toggled by the user, would be a desirable feature in such a system.

The addition of solar panels is would certainly be a goal, but would need to be implemented at a later stage.

Low-power-E-Paper-OS Working Group

=====================

**Name:** Low-power E-Paper OS

**Objective:**  The goal of this project is to run an OS on an ultra low-power CPU/MCU that can output terminal or a window manager to an e-paper display.

**Members:** hatonthecat, @alexsotodev open to new members, including after project started.

https://alexsoto.dev/static/community-built-eink-laptop-project/slides.pdf (Slides 45-49)

https://ei2030.zulipchat.com/register/

**Hardware:** Redboard Artemis, SAMD51, Dialog 14695, ESP32, STM32, other MCUs/MPUs with can be used, including ones with E-paper already connected, like M5Paper, or LILYGO® TTGO T5.

Looking for:

"At this point, we need other people interested in the idea of this super-low-power device with its “I’m not a regular laptop” aspiration. You can help us figure out the key important areas for us to focus on. No special skills needed! If you like the sound of such a device, email us and join! No required time-commitment and no contribution is too small and no worries of all of this microcontroller-type talk goes over your head. We need you!"


If you do have experience (and it is welcome), these fields are of particular help:

"Embedded Development

Electrical Engineering

Software Developers

Reverse-Engineering

Writers/Researchers"


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

3-4-2024

https://albertcory50.substack.com/p/bring-back-private-offices An interesting story on the myth of open (collaboration) spaces. Covers Xerox  and Bell Labs offices. 
