Update: the project page for the microkernel has been created here: https://github.com/hatonthecat/Soap-Kernel/blob/main/README.md


A proposed new concept for a microkernel is to develop a suite of partial kernels that can each function as a single driver, and are rotated into RAM, for microcontrolellers with limited RAM. This could allow a "time-share" for a larger, fuller kernel that could fit into a fraction of the space. If uCLinux can use a 300 KB kernel, but can only run 1 app, then a larger kernel of 3MB could be split into 10 microkernels of 256kB each. Then apps that are not used frequently can be stored on ROM, with bootloader that could allow a different app to be loaded into SRAM. The advantages to this over XiP (https://en.wikipedia.org/wiki/Execute_in_place) may be if an app is going to be used for a duration, where the transfer of the entire microkernel to RAM, replacing the previous image, would be a relatively small delay compared to the overall faster runtime once loaded into RAM. 

For example, if a user is running a text editor or a calculator app, they may not need the tcp/ip stack in the kernel while using that. modprobe and malloc could be used to remove the portions of memory address that were reserved for a driver that isn't being used. (I am not a knowledgeable programmer though, so I do not know the mechanisms on how this could be done) If the user is no longer using notepad/calc but wants to browse the web, the kernel can rewrite itself to fit only the components of the kernel needed to display a webpage. Whether this requires 1MB of RAM or more, is dependent on the compactness and simplicity of the browser. This concept isn't designed to accomplish a modern browser features initially, but rather a DOS or early windows like operating system, which used comparable RAM sizes (Windows 3.00 used 1MB RAM) https://www.pcjs.org/software/pcx86/sys/windows/3.00/.

https://www.pcjs.org/software/pcx86/sys/windows/1.00/ used 640K of RAM. By comparison, the Ambiq Apollo3 has 2 MCU variants, one in 384k and one in 768k. The Ambiq Apollo4 has more ram and support for i/o drivers: https://ambiq.com/apollo4/, thus is of great interest to this project.

An analogy in chemistry is electrons that hop around the atoms in molecule, such as carbonate: https://en.wikipedia.org/wiki/Carbonate

The property confers a double bond cycling around the molecule to produce a more stable charge than two fixed single bonds and a double bond.  (https://en.wikipedia.org/wiki/Resonance_(chemistry))

This property is also seen in aromatic compounds where the electron shares a double bond with six carbon atoms: https://en.wikipedia.org/wiki/Aromaticity

"In chemistry, aromaticity is a property of cyclic (ring-shaped), typically planar (flat) molecular structures with pi bonds in resonance (those containing delocalized electrons) that gives increased stability compared with other geometric or connective arrangements of the same set of atoms. Aromatic rings are very stable and do not break apart easily. Organic compounds that are not aromatic are classified as aliphatic compounds—they might be cyclic, but only aromatic rings have enhanced stability."

Of course, this analogy to comparing a kernel module cycling into RAM from slow ROM write speeds will fall short of the light speed of an electron. However, this project is here to explore the feasibility of a "quasi-kernel" or "quarter kernel" revolving functional instructions into and out of RAM, both on demand, as userpace is designed for, and also for system processes that require it.

As writing a kernel is highly dependent on the needs of a user, this concept may not necessarily fit every purpose. However, if a full linux kernel is seen to be a practical, existing tool that simply can't fit into a smaller microcontroller, this project is designed to explore a solution to that. The idea isn't to just search for a larger RAM chip- sometimes the power consumption penalty may prohibit certain uses in energy constrained systems. Thus, this project isn't about trying to get every application to run at the same time, but to see how the kernel could be designed so that it can rotate essential infrastructure for each app/driver/tool into the kernel "just-in-time."

Edit: This obviously has been tried in some form before, the most notable is found here: https://www.oreilly.com/openbook/opensources/book/appa.html

https://en.wikipedia.org/wiki/Minix_3 
There are other microkernel OSes out there like QNX https://en.wikipedia.org/wiki/QNX but it's not clear if there is a leading open source microkernel OS that resembles a linux "userpace" kernel, rather than an RTOS.


