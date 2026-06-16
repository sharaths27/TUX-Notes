## **Core Linux Hardware Commands** 

**How You Should Learn These (Best Path)**

 **Beginner**
uname, lsblk, free, df, top, ip a, lspci, lsusb

 **Intermediate**
lshw, dmidecode, iostat, sensors, ethtool, dmesg

 **Advanced**
perf, cpupower, udevadm, setpci, modprobe

**Important Tip**
**80% of real Linux hardware work is done using just:**

	lscpu
	lsblk
	free
	df
	ip a
	lspci
	lsusb
	dmesg

 **System & CPU Information**

|**Command**|**Purpose**|
| :-: | :-: |
|uname -a|Kernel & system info|
|lscpu|CPU architecture & cores|
|cat /proc/cpuinfo|Detailed CPU info|
|nproc|Number of processing units available to current process |
|top|Real-time CPU usage|
|htop|Better interactive top (if installed)|
|uptime|Load average|
|mpstat|Per-CPU statistics|
**Memory (RAM & Swap)**

|**Command**|**Purpose**|
| :-: | :-: |
|free -h|RAM & swap usage|
|vmstat|Memory + CPU stats|
|cat /proc/meminfo|Detailed memory info|
|swapon --show|Active swap|
|top / htop|Memory usage by process|
 
 **Disk & Storage**

|**Command**|**Purpose**|
| :-: | :-: |
|lsblk|Block devices (disks, partitions)|
|df -h|Disk usage|
|du -sh|Directory size|
|mount|Mounted filesystems|
|umount|Unmount device|
|blkid|UUID & filesystem info|
|fdisk -l|Disk partitions (MBR/GPT)|
|parted -l|Advanced partition info|
|`mount|column -t`|

df = filesystem usage\
du = actual directory/file usage 

**Filesystems**

|**Command**|**Purpose**|
| :-: | :-: |
|ls -l /dev|Device files|
|df -T|Filesystem types|
|mount -t|Mount by FS type|
|fsck|Filesystem check|
|tune2fs|ext filesystem tuning|
|findmnt|Mounted FS tree|

**PCI / USB Devices**

|**Command**|**Purpose**|
| :-: | :-: |
|lspci|PCI devices (GPU, NIC, sound)|
|lsusb|USB devices|
|lsusb -t|USB device tree|
|udevadm info|Device manager info|
|dmesg|Hardware detection logs|

**GPU / Graphics**

|**Command**|**Purpose**|
| :-: | :-: |
|`lspci|grep VGA`|
|glxinfo|OpenGL info|
|nvidia-smi|NVIDIA GPU stats|
|vainfo|Video acceleration|
|xrandr|Display info|

**Network Hardware**

|**Command**|**Purpose**|
| :-: | :-: |
|ip a|Network interfaces|
|ip link|Link-layer devices|
|ip route|Routing table|
|ethtool|NIC info|
|nmcli|NetworkManager|
|iwconfig|Wireless info|
|iw dev|Wi-Fi devices|

**Audio Hardware**

|**Command**|**Purpose**|
| :-: | :-: |
|aplay -l|Audio playback devices|
|arecord -l|Audio recording devices|
|amixer|ALSA mixer|
|pactl list|PulseAudio devices|

**Power & Battery**

|**Command**|**Purpose**|
| :-: | :-: |
|upower -i|Battery info|
|acpi|Battery & thermal info|
|powertop|Power usage|
|tlp-stat|Power management|

**Sensors & Temperature**

|**Command**|**Purpose**|
| :-: | :-: |
|sensors|CPU/GPU temps|
|watch sensors|Live monitoring|
|thermal\_zone\*|Kernel thermal data|

**Kernel & Hardware Logs**

|**Command**|**Purpose**|
| :-: | :-: |
|dmesg|Kernel messages|
|journalctl -k|Kernel logs|
|lsmod|Loaded kernel modules|
|modprobe|Load module|
|modinfo|Module info|

**Benchmarking & Diagnostics**

|**Command**|**Purpose**|
| :-: | :-: |
|stress|Stress test CPU/RAM|
|iostat|Disk I/O|
|iotop|Disk usage by process|
|watch|Run command repeatedly|
|perf|Performance analysis|

**Low-Level Hardware Access (Advanced)**

|**Command**|**Purpose**|
| :-: | :-: |
|setpci|PCI config|
|hwinfo|Full hardware dump|
|lshw|Detailed hardware tree|
|dmidecode|BIOS/firmware info|
|cpupower|CPU frequency control|

**Deep Hardware Enumeration (Rare but Legit)**

|**Command**|**Use**|
| :-: | :-: |
|inxi|Clean human-readable hardware summary|
|hardinfo|GUI + CLI hardware info|
|hwloc-ls|Hardware topology|
|numactl --hardware|NUMA layout|
|lsipc|Shared memory / IPC|

**CPU & Power Control (Advanced)**

|**Command**|**Use**|
| :-: | :-: |
|cpufreq-info|CPU frequency info|
|cpufreq-set|Change CPU governor|
|turbostat|Intel CPU power stats|
|rdmsr / wrmsr|CPU registers|
|x86\_energy\_perf\_policy|Intel power tuning|

**Storage & I/O (Advanced / Enterprise)**

|**Command**|**Use**|
| :-: | :-: |
|lsnvme|NVMe devices|
|nvme list|NVMe management|
|smartctl|Disk health (SMART)|
|badblocks|Disk surface check|
|wipefs|Remove FS signatures|
|losetup|Loop devices|
|cryptsetup|Disk encryption|
|multipath -ll|SAN multipathing|

**Network Hardware (Low-Level)**

|**Command**|**Use**|
| :-: | :-: |
|ss|Socket statistics|
|tc|Traffic control|
|bridge|Bridge devices|
|devlink|NIC firmware control|
|rfkill|Enable/disable radios|

**Audio / Media (Extra)**

|**Command**|**Use**|
| :-: | :-: |
|speaker-test|Test speakers|
|pw-cli|PipeWire control|
|pw-top|Audio performance|

**Firmware, BIOS & Boot**

|**Command**|**Use**|
| :-: | :-: |
|efibootmgr|EFI boot entries|
|fwupdmgr|Firmware updates|
|bootctl|systemd-boot control|
|mokutil|Secure Boot keys|

**Kernel Internals & Debugging**

|**Command**|**Use**|
| :-: | :-: |
|trace-cmd|Kernel tracing|
|ftrace|Kernel function tracing|
|bpftrace|eBPF analysis|
|bpftool|eBPF control|
|perf stat|Performance counters|

**Embedded / Niche Hardware**

|**Command**|**Use**|
| :-: | :-: |
|i2cdetect|I2C devices|
|i2cget/set|I2C control|
|spidev\_test|SPI devices|
|gpioinfo|GPIO pins|


/proc is **huge**, but unlike normal commands, it’s a **virtual filesystem**. So the “commands” are really:

- files you **read**
- directories you **explore**
- combined with tools like cat, less, grep, watch, awk

Below is the **most complete** *useful*** /proc **reference**—everything you’ll realistically need, from beginner → kernel-nerd.

**/proc — Complete Useful Reference**
**How You Read /proc**

	cat /proc/file
	less /proc/file
	grep something /proc/file
	watch cat /proc/file
	
### **CPU Information**
 **Global CPU**

|**Path**|**Meaning**|
| :-: | :-: |
|/proc/cpuinfo|CPU model, cores, flags|
|/proc/stat|CPU usage stats|
|/proc/loadavg|Load averages|
|/proc/uptime|System uptime|
|/proc/interrupts|IRQ usage per CPU|
|/proc/softirqs|Soft IRQ stats|

**Per-CPU**

  /proc/stat
  /proc/irq/\*
  /proc/sys/kernel/sched\*

**Memory & Swap**

|**Path**|**Meaning**|
| :-: | :-: |
|/proc/meminfo|RAM usage (gold mine)|
|/proc/swaps|Active swap devices|
|/proc/vmstat|Virtual memory stats|
|/proc/buddyinfo|Memory fragmentation|
|/proc/pagetypeinfo|Page allocation|
|/proc/slabinfo|Kernel slab cache|

 **Most important**:
 
	/proc/meminfo
	/proc/vmstat
	
	
 **Disk & Filesystems**

|**Path**|**Meaning**|
| :-: | :-: |
|/proc/partitions|Block devices|
|/proc/mounts|Mounted filesystems|
|/proc/self/mounts|Mounts for process|
|/proc/filesystems|Supported FS|
|/proc/diskstats|Disk I/O stats|
|/proc/sys/fs/\*|FS kernel tuning|

###**Network**

**Core Network Info**

|**Path**|**Meaning**|
| :-: | :-: |
|/proc/net/dev|Interface RX/TX|
|/proc/net/tcp|TCP connections|
|/proc/net/udp|UDP connections|
|/proc/net/raw|Raw sockets|
|/proc/net/sockstat|Socket usage|
|/proc/net/snmp|Network stats|
|/proc/net/route|Routing table|
|/proc/net/arp|ARP cache|

 Replacement for old tools:
 
	cat /proc/net/dev
	cat /proc/net/tcp
	
###**Hardware & Devices**

|**Path**|**Meaning**|
| :-: | :-: |
|/proc/devices|Registered devices|
|/proc/ioports|I/O ports|
|/proc/iomem|Memory map|
|/proc/dma|DMA channels|
|/proc/driver/\*|Driver info|

**Kernel & System**

|**Path**|**Meaning**|
| :-: | :-: |
|/proc/version|Kernel version|
|/proc/cmdline|Boot parameters|
|/proc/modules|Loaded modules|
|/proc/kallsyms|Kernel symbols|
|/proc/locks|File locks|
|/proc/timer\_list|Kernel timers|
|/proc/sysrq-trigger|Magic SysRq|
 **Process-Specific (/proc/PID/)**
Each running process has a directory:

	/proc/1234/
### **Most Important Files**

|**Path**|**Meaning**|
| :-: | :-: |
|/proc/PID/status|Human-readable info|
|/proc/PID/stat|Raw process stats|
|/proc/PID/cmdline|Launch command|
|/proc/PID/environ|Environment vars|
|/proc/PID/maps|Memory mappings|
|/proc/PID/fd/|Open file descriptors|
|/proc/PID/io|Disk I/O stats|
|/proc/PID/limits|Resource limits|
|/proc/PID/cgroup|Control groups|
|/proc/PID/net/\*|Process networking|

**Top 3 you’ll use constantly**:

	/proc/PID/status
	/proc/PID/fd/
	` `/proc/PID/cmdline

**Threads**

	/proc/PID/task/TID/

Same files as /proc/PID/, but per-thread.

**Kernel Tuning (/proc/sys)**
This is where **runtime kernel tuning** lives.

**Popular Ones**

|**Path**|**Meaning**|
| :-: | :-: |
|/proc/sys/kernel/hostname|System hostname|
|/proc/sys/kernel/panic|Panic timeout|
|/proc/sys/vm/swappiness|Swap behavior|
|/proc/sys/net/ipv4/ip\_forward|Routing|
|/proc/sys/fs/file-max|Max open files|

Change values (temporary):

echo 10 > /proc/sys/vm/swappiness

Permanent → /etc/sysctl.conf

**Performance & Debug**

|**Path**|**Meaning**|
| :-: | :-: |
|/proc/pressure/\*|CPU/MEM/IO pressure|
|/proc/schedstat|Scheduler stats|
|/proc/latency\_stats|Kernel latency|
|/proc/zoneinfo|Memory zones|

###**Most Useful /proc Cheat Sheet**

**Hardware**

	/proc/cpuinfo
	/proc/meminfo
	/proc/diskstats
	/proc/partitions
	/proc/iomem
	
 **Performance**
 
	/proc/stat
	/proc/loadavg
	/proc/uptime
	/proc/vmstat
	

**Networking**

	/proc/net/dev
	/proc/net/tcp
	/proc/net/route
	
**Processes**

	/proc/PID/status
	/proc/PID/fd
	/proc/PID/maps

**Important Notes**

	- /proc is **generated on the fly** (no real files)
	- Format **can change** between kernels
	- Some files are **root-only**
	- Writing to /proc/sys/\* changes live kernel behavior

###**1) Real Troubleshooting Using /proc**
 
 **High CPU usage**
 
	cat /proc/loadavg
	cat /proc/stat
	cat /proc/interrupts
	Find culprit:
	for p in /proc/[0-9]\*; do
	`  `awk '{print $1,$14+$15}' $p/stat 2>/dev/null
	done | sort -k2 -nr | head

**Memory leak**

	cat /proc/meminfo
	cat /proc/vmstat
	Per process:
	grep -H VmRSS /proc/\*/status | sort -k2 -nr | head
	
**Disk I/O bottleneck**

	cat /proc/diskstats
	cat /proc/pressure/io
	Per process:
	cat /proc/PID/io

**Network issue**

	cat /proc/net/dev
	cat /proc/net/tcp
	cat /proc/net/route

###**2) How top, free, ps REALLY Work**
Linux tools are basically **pretty printers for** /proc.
 **free**
Reads:

	/proc/meminfo
 **uptime**
Reads:

	/proc/loadavg
	/proc/uptime

**ps**
Reads:

	/proc/PID/stat
	/proc/PID/status
	/proc/PID/cmdline

**top**
Reads:

	/proc/stat
	/proc/loadavg
	/proc/meminfo
	/proc/PID/\*

` `If /proc breaks, **all these tools lie or fail**.

###**3) Safe vs Dangerous /proc Writes (VERY IMPORTANT)**
 **Generally Safe (Temporary tuning)**
 
	echo 10 > /proc/sys/vm/swappiness
	echo 1 > /proc/sys/net/ipv4/ip\_forward
	echo myhost > /proc/sys/kernel/hostname

These reset on reboot.

**Dangerous (Can freeze or crash system)**

	echo 1 > /proc/sys/kernel/sysrq
	echo c > /proc/sysrq-trigger     # instant kernel panic
	echo 0 > /proc/sys/kernel/panic
	echo 3 > /proc/sys/vm/drop\_caches   # can kill performance

` `Rule:

	**Never write to** /proc **unless you know EXACTLY what it does**

**4) Visual Mental Map of /proc**
/proc
├── cpuinfo        → CPU details
├── meminfo        → RAM usage
├── stat           → CPU + system stats
├── uptime         → system uptime
├── loadavg        → load average
├── diskstats      → disk I/O
├── mounts         → mounted filesystems
├── net/           → networking
│   ├── dev
│   ├── tcp
│   └── route
├── sys/           → kernel tuning (DANGEROUS)
│   ├── vm/
│   ├── kernel/
│   └── net/
├── 1234/          → process with PID 1234
│   ├── status
│   ├── stat
│   ├── fd/
│   ├── maps
│   └── io

 **Golden Rule of /proc**
**If you understand** /proc**, you understand Linux internals.**\
Everything else is just tooling on top.

 **1 /proc/PID/status — COMPLETE DEEP DIVE**
Pick any running PID:

	cat /proc/$$/status
	
###**Most Important Fields (you *must* know)**
**Identity**

|**Field**|**Meaning**|
| :-: | :-: |
|Name|Process name|
|Pid|Process ID|
|PPid|Parent PID|
|State|R=run, S=sleep, D=IO wait, Z=zombie|

#### **Memory (VERY IMPORTANT)**

|**Field**|**Meaning**|
| :-: | :-: |
|VmSize|Total virtual memory|
|VmRSS|Actual RAM used|
|RssAnon|Heap memory|
|RssFile|File-backed memory|
|RssShmem|Shared memory|

**Memory leak?** Watch VmRSS, not VmSize.

#### **Security**

|**Field**|**Meaning**|
| :-: | :-: |
|Uid|Real / effective user|
|Gid|Group IDs|
|CapEff|Linux capabilities|
|Seccomp|Syscall filtering|
#### **Threads**

|**Field**|**Meaning**|
| :-: | :-: |
|Threads|Number of threads|
|voluntary\_ctxt\_switches|Yielding CPU|
|nonvoluntary\_ctxt\_switches|Preempted|

High context switches = contention or I/O wait.
**2 /proc/meminfo — MEMORY FIELD BY FIELD**

	cat /proc/meminfo
	
### **Fields You MUST Understand**

|**Field**|**Meaning**|
| :-: | :-: |
|MemTotal|Total RAM|
|MemFree|Completely unused|
|MemAvailable|Real usable memory|
|Buffers|Block device cache|
|Cached|File cache|
|SwapTotal|Swap size|
|SwapFree|Free swap|

**Ignore** MemFree
**Use** MemAvailable to judge memory pressure
### **Advanced (Still Important)**

|**Field**|**Meaning**|
| :-: | :-: |
|Dirty|Waiting to be written|
|Writeback|Currently writing|
|Slab|Kernel objects|
|PageTables|Page table memory|
|AnonPages|Anonymous memory|
### **3 /proc/stat — CPU MATH (THIS IS GOLD)**

	cat /proc/stat
### **CPU line format:**

cpu  user nice system idle iowait irq softirq steal guest guest\_nice
**Example:**

	cpu  4705 0 2255 226255 367 0 45 0 0 0

**Calculate CPU Usage Manually**

	prev=$(head -n1 /proc/stat)
	sleep 1
	cur=$(head -n1 /proc/stat)
	CPU Usage formula:
	usage = 100 × (delta\_total - delta\_idle) / delta\_total

This is **exactly how** top **works**.
 
 **5 Writing SAFE sysctl Values (DO THIS CAREFULLY)**
### **Common SAFE Tunings**

#### **Swap behavior**

	echo 10 > /proc/sys/vm/swappiness
#### **Enable routing**

	echo 1 > /proc/sys/net/ipv4/ip\_forward
#### **File descriptors**

	echo 100000 > /proc/sys/fs/file-max
### **Correct Way (recommended)**

	sysctl vm.swappiness=10
	sysctl net.ipv4.ip\_forward=1

**Permanent:**

	/etc/sysctl.conf
	/etc/sysctl.d/\*.conf

### **NEVER TOUCH unless you KNOW**

	kernel.sysrq
	kernel.panic
	vm.drop\_caches
	
### **5 Rebuild top MANUALLY Using /proc**
**Step 1: System CPU**

	cat /proc/stat
 **Step 2: Load**
 
	cat /proc/loadavg
 **Step 3: Memory**
 
	grep -E 'MemTotal|MemAvailable' /proc/meminfo
 **Step 4: Per-process CPU (RAW)**
 
	awk '{print $1,$14+$15}' /proc/[0-9]\*/stat 2>/dev/null | sort -k2 -nr | head
 **Step 5: Per-process Memory**
 
	grep -H VmRSS /proc/[0-9]\*/status | sort -k2 -nr | head


###**Mental Model (Remember This)**

	- /proc = **kernel truth**
	- Tools = **pretty printers**
	- If tools disagree → /proc wins

**CPU Vulnerabilities**

	lscpu | grep Vulnerability\
	or
	cat /sys/devices/system/cpu/vulnerabilities/\*


**Memory Hardware**

	dmidecode -t memory\
Shows:

	DIMM slots
	speed
	manufacturer

**BIOS**

	dmidecode -t bios

**Motherboard**

	dmidecode -t baseboard
