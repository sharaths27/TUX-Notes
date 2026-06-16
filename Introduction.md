
**Birth of Unix (1969)**: After AT&T Bell Laboratories pulled out of the Multics project, Ken Thompson and Dennis Ritchie developed Unix. Originally written in assembly, it was rewritten in the C programming language in 1973 to make it portable across different hardware.

**The Rise of Variants (1970s–1980s)**: Unix's portability led to many "flavors," including BSD (Berkeley Software Distribution) and commercial versions like SunOS (from Sun Microsystems) and IBM AIX.

**The GNU Project (1983)**: Richard Stallman launched the GNU Project to create a completely free, Unix-like operating system. By the early 1990s, most components (compilers, shells, editors) were complete, but its kernel, GNU Hurd, was still under heavy development and not yet functional.

**MINIX (1987):** Andrew S. Tanenbaum released MINIX, a small Unix-like system for educational use. It was the system Linus Torvalds used at the University of Helsinki, but its licensing restrictions and limitations on personal computer hardware frustrated him

**The Invention of Linux (1991)**
Frustrated by the high cost of commercial Unix (roughly $5,000 at the time) and the limitations of MINIX, Linus Torvalds began writing his own kernel.

**The Announcement:** On August 25, 1991, Torvalds posted a famous message to the  comp.os.minix  newsgroup, stating he was working on a free operating system as "just a hobby, won't be big and professional like gnu".
First Release: Linux version 0.01 was released on September 17, 1991, with approximately 10,000 lines of code.
**Adopting the GPL (1992): **In early 1992, Torvalds relicensed the Linux kernel under the GNU General Public License (GPL). This was a turning point, as it allowed the kernel to be combined with existing GNU software, creating a complete, free operating system often called GNU/Linux.

**Modern Linux Milestones**
1993: The first major distributions like Slackware and Debian were founded.
1994: Linux 1.0 was released, signaling its stability for broader use.
1996: The penguin mascot, Tux, was created after Linus Torvalds was reportedly bitten by a penguin at a zoo.
Late 1990s: Major corporations like IBM and Oracle began supporting Linux, leading to its dominance in servers and supercomputers.

**Birth of Unix (1969)**

The story begins at AT&T Bell Laboratories, where researchers like Ken Thompson and Dennis Ritchie were working.

**What happened?**
They were originally part of a large, complex project called Multics.
When Bell Labs left the project, Thompson wanted a simpler system.
In 1969, he created the first version of Unix.

**Why Unix was revolutionary**

Simple and modular design
 Instead of one huge system, Unix used small programs that do one thing well.
 These programs could be combined using pipes.

**Written in C (1973)**
 Originally written in assembly it was rewritten in the C programming language by Ritchie. 
** This made Unix:**
 	Portable (could run on different machines)
	 Easier to modify

This portability is one of the biggest reasons Unix spread so widely.

**Rise of Unix Variants (1970s–1980s)**

Because of legal restrictions, AT&T couldn’t sell Unix commercially at first, so they:

Licensed it cheaply to universities
Shared source code

Result: Explosion of versions (“flavors”)
Academic version
	Berkeley Software Distribution (BSD)
		Developed at UC Berkeley
		Added major innovations:
			TCP/IP networking (foundation of the internet)
			Virtual memory
	
**Commercial versions**
 As Unix became valuable, companies created their own versions:
	SunOS (by Sun Microsystems)
	IBM AIX (by IBM)

**The downside: Fragmentation**
 Each version was slightly different
 Software compatibility became difficult
 Systems were often proprietary and expensive

This fragmentation later motivated the push for a free, unified Unix-like system.

The Portable Operating System Interface (POSIX) standard was created, defining the core interface and behavior of a Unix-style operating system.

**The GNU Project (1983)**
This is where philosophy enters the story.

**Who started it?**
Richard Stallman

**What was the goal?**
To build a completely free (as in freedom) Unix-like operating system.

 “GNU” stands for: GNU’s Not Unix (a recursive joke)

**What GNU achieved**

By early 1990s, GNU had built:
	Compilers (like GCC)
	Shells (like Bash)
	Editors (like Emacs)
	Core utilities

**What was missing?**
A working kernel: GNU Hurd
Still incomplete and unstable

So GNU had almost everything except the core piece that makes an OS run.

**MINIX (1987)**
**Created by**: 	Andrew S. Tanenbaum
** Purpose:** 	Educational Unix-like system

Designed for teaching operating system concepts
Key features:
	 Small and simple
	 Microkernel architecture
	 Source code available for study

**Why MINIX mattered to Linux**
A student named Linus Torvalds used MINIX at the University of Helsinki.
But he faced problems:

	License restrictions
	Not fully free to modify and redistribute
	Limited capabilities
	Not powerful enough for real-world use
	Especially weak on PC hardware
	Frustration
He wanted more control and performance

This frustration directly led to:
“I’ll just build my own system.”

**Why This Led to Linux**
In 1991:

 Torvalds created the Linux kernel
 Combined it with GNU tools

**Result:**
 A complete, free, Unix-like operating system: GNU/Linux

**Key Insight**
Linux didn’t replace Unix—it continued its philosophy:

	 Portability (from Unix)
	 Modularity (from Unix)
	 Freedom (from GNU)
	 Practical usability (beyond MINIX)

**The Announcement:** On August 25, 1991, Torvalds posted a famous message to the comp.os.minix newsgroup (Usenet group), stating he was working on a free operating system as "just a hobby, won't be big and professional like gnu".

**First Release:** Linux version 0.01 was released on September 17, 1991, with approximately 10,000 lines of code.

**Adopting the GPL (1992)**: In early 1992, Torvalds relicensed the Linux kernel under the GNU General Public License (GPL). This was a turning point, as it allowed the kernel to be combined with existing GNU software, creating a complete, free operating system often called GNU/Linux.

**Building the Linux Kernel**
What he actually built
Torvalds focused on creating the kernel, which is:

**The core part of an OS**
 Manages:
	 CPU
	 Memory
	 Hardware devices
	 File systems

Unlike the GNU Project, which lacked a kernel, Linux solved exactly that missing piece.

**Big Picture**
Think of it like this:

	Unix → The original idea
	GNU → The tools
	Linux → The missing core (kernel)

**1993: First Major Distributions**
Two important projects appeared:

	-  Slackware
	-  Debian

**What changed here?**
Before this, using Linux was hard:

	You had to manually compile the kernel
	Install tools one by one
	Configure everything yourself

 These early distributions solved that.

**Why they mattered**
**Slackware**: One of the first usable, complete Linux systems
**Debian**: Introduced:
Strong community governance
Package management system (install software easily)

This made Linux accessible beyond hardcore programmers.

**1994: Linux 1.0 Release**
Linux kernel version 1.0 was released

**Key capabilities**
	 Networking support (TCP/IP)
	 Could run servers
	 Better memory and process management

**This is when Linux stopped being a “student project” and became a serious operating system**

**1996: Tux the Penguin**
Linux got its mascot: Tux
Origin story
	 Linus Torvalds joked about being bitten by a penguin
	 He liked penguins → community adopted it
**Why it matters**
Symbol of Linux culture:
 	Friendly
	 Fun
 	Community-driven
 Unlike corporate logos, Tux represents open-source spirit.

What is a “Distribution” (Distro)?

A Linux distribution (distro) is:
A complete operating system built using the Linux kernel + software tools + user interface

**Think of it like this:**
The Linux kernel alone is just the engine 
A distribution is the full car:
	Engine (kernel)
	Dashboard (UI)
	Controls (tools)
	Extras (apps)

**What a distro includes**
	 Linux kernel
	 GNU tools (from the GNU Project)
	 Package manager (to install software)
	 Desktop environment (GUI, optional)
	 Pre-installed applications

Major Linux Distribution: Slackware, Debian, Ubuntu, Fedora, RHEL, SUSE, Arch, Gentoo etc..
(https://upload.wikimedia.org/wikipedia/commons/1/1b/Linux_Distribution_Timeline.svg)

**Unix 1969**
├── BSD FreeBSD, OpenBSD, NetBSD, Darwin/macOS
└── GNU  Linux Kernel 1991
    ├── **Debian 1993**     Ubuntu, Mint, Kali
    ├── **Red Hat 1994**    RHEL, Fedora, CentOS, Rocky, Alma
    ├── **Slackware 1993**	SUSE, openSUSE
    ├── **Arch 2002**		Manjaro, EndeavourOS
    ├── **Gentoo 2000**	    Funtoo, ChromeOS (inspired)
    └── **Independent**     Alpine, Void

## Kernel

The kernel is the program that controls everything in a computer and lets applications talk to hardware safely and efficiently.

The Linux kernel is the core, foundational program of the operating system that acts as the direct bridge between computer hardware (CPU, memory, devices) and software applications. It manages system resources, enabling apps to run, and acts as a central mediator, ensuring secure interaction between hardware and software.

<img width="800" height="633" alt="image" src="https://github.com/user-attachments/assets/9a795f03-00de-41a5-9dae-332487a0654c" />

**What the Kernel Actually Does**

**1. Process Management**
	Handles running programs (called processes)
	Decides:
		Which program runs first
		How long it runs (CPU scheduling)

**2. Memory Management**
	Controls RAM usage
	Allocates memory to programs
	Prevents programs from interfering with each other

**3.  Device Management**
	Communicates with hardware using drivers
	Controls:
		Keyboard
		Mouse
		Disk
		Printer

**4. File System Management**
	Manages files and directories
	Handles reading/writing data to storage

**5. Security & Access Control**
	 Ensures programs don’t access unauthorized data
	 Enforces permissions
