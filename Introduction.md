
**What is an Operating System?**
An Operating System (OS) is software that manages hardware resources and provides services to applications.
**Examples:**
- Linux
- Windows
- macOS
  
**Responsibilities:**
- Process management
- Memory management
- Storage management
- Device management
- Security
  
**Process** = Running program

**Thread** = Execution unit inside a process

**Example:**

Chrome

  ├── Thread 1
  ├── Thread 2
  └── Thread 3
  
**Birth of Unix (1969)**: After AT&T Bell Laboratories pulled out of the Multics project, Ken Thompson and Dennis Ritchie developed Unix. Originally written in assembly, it was rewritten in the C programming language in 1973 to make it portable across different hardware.

**The Rise of Variants (1970s–1980s)**: Unix's portability led to many "flavors," including BSD (Berkeley Software Distribution) and commercial versions like SunOS (from Sun Microsystems) and IBM AIX.

**The GNU Project (1983)**: Richard Stallman launched the GNU Project to create a completely free, Unix-like operating system. By the early 1990s, most components (compilers, shells, editors) were complete, but its kernel, GNU Hurd, was still under heavy development and not yet functional.

**MINIX (1987):** Andrew S. Tanenbaum released MINIX, a small Unix-like system for educational use. It was the system Linus Torvalds used at the University of Helsinki, but its licensing restrictions and limitations on personal computer hardware frustrated him
(MINIX source was available for study, but it was not as freely redistributable and modifiable as modern open-source software.)

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

	Linux technically refers to the kernel.
	A complete operating system is usually:
	Linux Kernel + GNU Tools + User Applications

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

**To put the kernel in context, you can think of a Linux machine as having 3 layers:**

**The hardware:** The physical machine—the bottom or base of the system, made up of memory (RAM) and the processor or central processing unit (CPU), as well as input/output (I/O) devices such as storage, networking, and graphics. The CPU performs computations and reads from, and writes to, memory.

**The Linux kernel**: The core of the OS. (See? It`s right in the middle.) Its software residing in memory that tells the CPU what to do
.
**User processes**: These are the running programs that the kernel manages. User processes are what collectively make up user space. User processes are also known as just processes. The kernel also allows these processes and servers to communicate with each other (known as inter-process communication, or IPC).

**How It Works (Flow)**
		 You open an app
		 App sends request → kernel
		 Kernel talks to hardware
		 Hardware responds → kernel → app → you

Everything goes through the kernel.

**Linux Kernel Architecture**

<img width="500" height="442" alt="image" src="https://github.com/user-attachments/assets/102b771d-6902-4039-a7fc-78d80214ec3d" />

<img width="800" height="308" alt="image" src="https://github.com/user-attachments/assets/cb629d10-5d75-446e-b28b-3bef78ca9289" />

**Kernel Space**

The privileged, protected area where the kernel runs. Has direct access to hardware CPU, memory, I/O devices).

**Full access to:**
	 CPU
	 Memory
	 Hardware devices

**Runs critical code:**
	Device drivers
	Process scheduler
	Memory manager

***If something crashes here → the whole system can crash.***

**User Space**

The restricted area where normal programs run. Does not have direct access to hardware or kernel memory

**Apps like:**
	Browser
	Text editor
	Games
**Limited access:**
	 Cannot directly touch hardware
	 Cannot access other programs’ memory

*** If an app crashes → only that app crashes, not the whole system.***

Why Separate Them?

This separation exists for safety and stability:

1. Security
	Prevents malicious apps from:
	Accessing hardware directly
	Reading sensitive memory
2. Stability
	Bugs in apps don’t crash the OS
3. Control
	Kernel decides who gets resources

**How They Communicate**

User space and kernel space cannot directly access each other.
They communicate using system calls

**System Calls (The Bridge)**
A system call is a controlled way for a program to request services from the kernel.

 Example:
**When you open a file:**
	 App (user space) → requests file open
	 System call triggers switch to kernel space
	 Kernel accesses disk
	 Returns result to app

**Step-by-Step Flow**
	 Program runs in user space
 	Needs something (file, network, memory)
 	Makes a system call
 	CPU switches to kernel space
 	Kernel does the work
 	Returns result
 	Switches back to user space


**Console**

The console is the system’s primary direct interface (often the “main screen”).

Types:
Physical console: Monitor + keyboard connected to machine
Virtual console (Linux): Access with Ctrl + Alt + F1–F6

Think of console as:  The “real” system interface, while terminals are windows inside it

**Terminal**

A terminal is a program that lets you interact with the system using text.

Examples: GNOME Terminal, Konsole, or iTerm2

What it does:
	 Displays text interface
	 Takes your keyboard input
	 Shows output
Important:
	 Modern terminals are actually terminal emulators (software, not real hardware)

**TTY (Teletype)**

TTY stands for Teletypewriter (old physical terminals from the 1960s),The term TTY is a relic from the days when people used actual electromechanical typewriters to send data to computers.

Today: It refers to the kernel subsystem that handles input and output. When you press Ctrl+Alt+F3 on Linux, you switch to a "Virtual TTY"—a full-screen text interface managed by the kernel.

In modern Linux:
TTY means:  A text-based interface device

**Examples:**  /dev/tty1, /dev/tty2 → virtual consoles
 It represents:  Input/output channel between user and system

**PTS (Pseudo Terminal Slave)**

PTS is a virtual terminal used by terminal emulators, When you open a terminal window inside a graphical desktop (like Ubuntu or macOS) or connect via SSH, you aren't using a "real" hardware TTY.
Instead, the system creates a PTS. It’s a "fake" TTY that allows graphical applications to behave like old-school text terminals

Example: /dev/pts/0, /dev/pts/1
What it means:
 When you open:
 	GNOME Terminal
	 It creates a pseudo terminal pair:
 		Master (controlled by terminal app)
 		Slave (used like a TTY)

**Shell**

A shell is a program that interprets your commands. The shell lives inside the terminal.

**What it does**:
	 Reads your input
	 Executes commands
	 Talks to the kernel

** Example:**
What Happens When You Type:
$ ls
	1. Terminal captures input
	2. PTS sends input
	3. Shell parses command
	4. Shell finds /usr/bin/ls
	5. Kernel loads program
	6. ls executes
	7. Kernel returns output
	8. Terminal displays result

**Bash (Bourne Again Shell)**
Bash is just one type of shell

**Why it’s popular:**
	 Default shell in many Linux systems
	 Powerful scripting capabilities

**Other shells exist**: sh, zsh, fish

**How They Work Together**

	Hardware/GUI → you open a Terminal Emulator.
	It connects to a PTS device (/dev/pts/X ).
	That session runs a Shell (usually Bash).
	The shell accepts your input, passes it to the Kernel, and displays the result

When you type a command, the data flows through these layers in a specific order:

**Terminal Emulator**: You type mkdir photos into a window.
PTS/TTY: The window sends those characters through a PTS (the bridge) to the system.
Shell (Bash): The Shell receives the characters, realizes you want to make a directory, Shell launches the mkdir program.The mkdir program then invokes system calls to create the directory.
Display: The Shell sends the "Success" message back through the PTS, and the Terminal draws the text on your screen.

**Summary**
	Terminal is the where you type.
	TTY/PTS is how the data moves.
	Shell is what understands your commands.
	Bash is the specific language the shell speaks.

**Quick Commands to Explore**
tty        	  # shows which terminal device you're on (e.g. /dev/pts/1
ps -p $$ 	  # shows which shell youʼre using 
echo $0   	  # prints current shell name
who        	  # shows who is logged in and on which tty/pts

**In short:**
Terminal = the window/program you type into.
Shell = the command interpreter running inside the terminal.
Bash = the most common shell.
TTY = old-school physical/virtual terminals (/dev/ttyX ).
PTS = modern pseudo-terminals for terminal emulators ( /dev/pts/X )


The Terminal is the UI window where I type; it handles things like fonts and colors. It communicates with the system through a** PTS **(Pseudo-Terminal) if I'm in a **GUI**, or a **TTY **if I'm at the **system console**. Inside that **terminal**, a **Shell** is running this is** theinterpreter** that actually executes my commands. **Bash** is simply the specific flavor of shell I\'m using, known for its scripting capabilities and ubiquity in Linux.

A **terminal **is the interface I use to interact with the system. If I'm on the machine directly, that's the **console**, backed by **TTY **devices. If I'm using a** terminal emulator (GUI) or SSH**, that's a **PTS device**. Inside the** terminal,** a** shell** runs to interpret my commands, and **Bash** is one of the most common shells.

At the top, we have the **terminal**, the interface I use to interact with the system. If I'm directly on the machine, that's the **console**, backed by **TTY devices**. If I'm using a **terminal emulator or SSH**,that's a **PTS device**. Inside that **terminal**, a** shell** runs to interpret my commands, and** bash** is one of the most common shells.


**“everything is a file”**

Linux treats many different things (devices, processes, data, communication) using the same file interface.

**Linux File System Hierarchy Explained**
The hierarchy starts at the root directory / , and everything branches from there.

**Core Directory Structure**

**Directory**	    **Purpose**

	/ 		Root of the file system (everything starts here)
	/bin 		Essential user binaries (commands like ls, cp)
	/sbin 		Essential system binaries (like reboot , fsck)
	/etc 		System-wide configuration files
	/dev 		Device files (e.g., /dev/sda, /dev/null )
	/proc 		Virtual filesystem providing process and kernel info
	/sys 		Interface to kernel (devices, drivers)
	/var 		Variable data (logs, spool files, mail)
	/tmp 		Temporary files (cleared on reboot)
	/home 		User home directories /root Home directory for the root user
	/boot 		Bootloader files (kernel, initrd, grub)
	/lib, /lib64 	Essential shared libraries for /bin and /sbin
	/usr 		User-installed software and libraries (non-essential at boot)
	/opt 		Optional third-party software /media Mount points for external devices USB, DVD
	/mnt 		Temporarily mounted filesystems
	/run 		Runtime data (system boot time, PID files, sockets)
	/root		Root user home directory (optional)

**Old Layout**

	/bin → 	essential binaries
	/sbin → 	system tools
	/lib → 		libraries
	/usr/bin → 	additional binaries
	/usr/sbin → 	additional system tools
	/usr/lib → 	additional librarie

**New (Merged /usr )**

	/bin  → 	symlink to /usr/bin
	/sbin   →	 symlink to /usr/sbin
	/lib   → 	symlink to /usr/lib
	/usr/
	bin/
	sbin/
	lib/

**Important Directories**

/proc **(Virtual filesystem)**
Not real files — shows kernel and process info
Example: /proc/cpuinfo , /proc/meminfo ,

/sys **(Kernel Interface)**
/proc/uptime Info about devices, modules, buses, etc.

/run **(Early boot runtime info)**
PID files, systemd info, etc. Exists only in RAM, not stored on disk (Traditional:init, Modern: systemd)

/boot **(System boot files)**
Contains  static  files  for  the  boot  loader.  This directory holds only the files which are needed during the boot process

/etc
Contains configuration files which are local to the machine

$ man hier
( hier - description of the filesystem hierarchy)
