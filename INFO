Here is release .98 of SLS (SoftLanding Linux System).
This is NOT just an image dump of someones Unix system.
Instead it is a distribution whose primary purposes are:

0) provide an initial installation program (for the quesy).
1) utilities compiled to use minimal disk space.
2) provide a reasonably complete/integrated U*ix system.
3) provide a means to install and uninstall packages.
4) permit partial installations for small disk configs.
5) add a menu driven, extensible system administration.
6) take the hassle out of collecting and setting up a system.
7) give non internet users access to Linux.
8) provide a distribution that can be easily updated.

MENU INTERFACE:

In particular, the menu interface allows the users to see
what commands would be executed if an option was selected,
so that Unix newbies who use it, don't have to always stay 
newbies (this was my big complaint about DELL, ISC, etc).
In some ways, however, this release is more a framework than
a finished product in that much more can be added to the menus.
So be forewarned.


There are several reasons for using DOS formatted 
floppies for for distribution:

1) it is easier to view/maintain/change the distribution.
2) it is easier for first time users to download/bootstrap
3) users can take just the parts from each disk they want.
4) DOS diskcopy can be used to backup all but disks 1 and 2. 

This is a binary mostly distribution (except for the kernel), and
is broken into multiple parts, or series, each of which is denoted 
by a letter followed by the disk number as follows:

	a1-aN: The minimal base system
	b1-bN: Base system extras, like man pages, emacs etc.
	c1-cN: The compiler(s), gcc/g++/p2c/f2c
	x1-xN: The X-windows distribution

This scheme allows new disks to be added to the distribution without
changing the disk numbering.  Also, the sysinstall program doesn't
have to be changed when new disks are added, because the last disk is
marked by the presence of the file "install.end".  And when interviews
is added, say as a new series "i", it can be installed with:

	sysinstall -special i

Highlights of the base are:  gcc/g++, emacs, kermit, elm/mail/uucp, 
gdb, sc (spreadsheet), man pages, groff, elvis, zip/zoo/lh and menu.  
Highlights of X are: X, programmers libs, 75 dpi fonts, games (spider,
tetris, xvier, chess, othello, xeyes, etc) and utilities like xmag, 
xmenu, xcolormap.


Utilities < 40K are linked -N (in most cases) to eliminate the 
header, so much disk space is saved.  Disk usage is as follows:

Minimal base system:     6 Meg
Full base system:       20 Meg
Full base system + X11: 40 Meg


INSTALLATION:

An auto installation utility is provided which does all the work
after the user does an fdisk and mkfs.  Installation begins with

	doinstall /dev/hd? 

which installs the base system software onto the hard drive, generates a
new boot disk, and then asks the user to reboot to use the hard disk.
This should be more or less fool proof.   Once you have rebooted, you
can logon as "root", type "menu" and install the remainder of the software,
if desired, via the menu system.


AVAILABILITY:

This distribution is freely available if you have internet 
access, or an obliging friend with access to it.
The distribution is around 18 disks, only the first two of 
which are not DOS formatted floppies. Each disk contains about 
1100K of stuff.  You can, however, get a pretty complete system with 
just disk 1-4, or if you already have linux up, just disks 3 and 4.

The SLS system is available, primarily for non-netters from:

	Softlanding Software
	910 Lodge Ave. 
	Victoria, B.C., Canada
	V8X-3A8
	(604) 360-0188

for $3.25/disk US ($4.00/disk Canadian) copying charge.
See Softlanding for a gentle touch down from a DOS bailout.
