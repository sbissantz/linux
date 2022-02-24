# vocabs.md

daemon process	daemon	A program that runs a background process		linux_01_term_fad
GNU's Not Unix!	GNU	recoding of UNIX that could be freely distributed	Linux kernel + GNU = Linux	linux_01_term_fad
Desktop Environment	DE	A GUI to access and manage the OS	Gnome, KDE, etc.	linux_01_term_fad
Graphical User Interface	GUI	A graphical way to interact with the system	menu bars, icons, etc.	linux_01_term_fad
Window Manager	WM	Manages the placement &amp; appearance of windows	...can be part of a DE or be used standalone	linux_01_term_fad
X Window System	X	A framework on which DE's or WM's can operate		linux_01_term_fad
hypen	-	An option prefix		linux_01_term_fad
double hypen	&nbsp; --	A flag prefix		linux_01_term_fad
environment variable	$PATH	The place where the shell looks up commands	..in hierarchical order (left-right)	linux_01_term_fad
piping between commands	[command] | [command]	Connect the output from one command to another	cat /etc/oassd | sort |less	linux_01_term_fad
The nicer rule		The nicer a process is, the less CPU attention it gets		rethinking_01_term
Proprietary software		closed-source software	reserve rights, restrict use, modification &amp; sharing	Term - Explanation
Linux	Operating System	An open source UNIX-like OS		Term - Explanation
Binary		A compiled, ready-to-run version of software		Term - Explanation
Wayland		A modern replacement for X		Term - Explanation
X Server		Interface to my screen, mouse and keyboard	..runs on the local system	Term - Explanation
X Client		An app which is displayed on an X Server		Term - Explanation
Live Image		A tool to take over the operation of your computer temporarily	..without harming the contents of your hard drive	Term - Explanation
Mutter		Window manager	..default with GNOME 40	Term - Explanation
Nautilus	aka. Files	File manager&nbsp;/ graphical shell	..default wiht GNOME 40	Term - Explanation
Gnome panels		Application/task launcher	..default with Gnome 40	Term - Explanation
Drawer		An icon to view other icons	..menus, applets, launchers	Term - Explanation
$	prompt	Regular user		Term - Explanation
#	prompt	Default prompt for the root user		Term - Explanation
Shell script		A group of commands that runs from a plain text file		Term - Explanation
Shell		Command language interpreter		Term - Explanation
option		Specification of a command's behavior	-l, -a, -la	Term - Explanation
Argument		A hint for the command on what to act	..file name, directory, username, device	Term - Explanation
flag		A whole word as an option		Term - Explanation
IDLE time	who -uH	How long the shell is open without a command being typed	.. a "." means active&nbsp;	Term - Explanation
shell variables		Store (useful) info on the user's shell session		Term - Explanation
environment variables		A value assigned to a dynamic name <br>..to exand it in scripts &amp; commands	\(^*\)<a href="https://www.gnu.org/software/bash/manual/bash.html#Shell-Variables">https://gnu.org/software/bash/manual/bash.html#Shell-Variables</a>	Term - Explanation
-<u>rw-</u>rw-r--	file mode bits	Owner's permission		Term - Explanation
-rwx<u>rw-</u>r--	file mode bits	Permission of assigned group		Term - Explanation
-rwxrw-<u>rw-</u>	file mode bits	General user permissions		Term - Explanation
Read (file)	File Permission	View file content		Term - Explanation
Read (dir)	write permission	View files &amp; sub-dirs		Term - Explanation
Write (file)	File Permission	Change content, rename &amp; delete	(CcRD)	Term - Explanation
Write (dir)	file permission	Add, rename &amp; delete files/sub-dirs	(ARD)	Term - Explanation
Execute (file)	File Permission	Run the file as a program		Term - Explanation
Execute (dir)	file permission	Make WD, execute programms, search thorugh, acess metadata	(MESA)	Term - Explanation
Default (file)	file permission number	664 <br>(rw-rw-r)	umask 002	Term - Explanation
Default (dir)	file permission number	775 <br>(rwxr-xr-x)	umask 002	Term - Explanation
Full open (file)	File permission number	666 <br>(rw-rw-rw-)	umask 000	Term - Explanation
Full open (dir)	file permission number	777 <br>(rwxrwxrwx)	umask 000	Term - Explanation
Default root (file)	file permission number	644&nbsp;<div>(rw-r-r)</div>	umask 022	Term - Explanation
Default root (dir)	file permission number	755 <br>(rwx-r-xr-x)	umask 022	Term - Explanation
ls-locate restriction		If you cant 'ls' to view files, you cannot 'locate' them		Term - Explanation
Multitasking	Multitasking system	Many process running at the same time		Term - Explanation
process		An running instance of a command		Term - Explanation
superuser	root user	Manager of the system's ressources		Term - Explanation
Cockpit		A browser based system manager facility		Term - Explanation
DNS	Domain Name System	Finds the IP behind domain names	"google.com" --&gt; IP:&nbsp;192.168.122.1	Term - Explanation
SELinux	Security-Enhanced Linux	A security architecture for Linux		Term - Explanation
NFS	Network File System	Allows a client computer to <i>access</i> files over a computer network		Term - Explanation
FTP	File Transfer Protocol	Allows to <i>transfer</i> files from/to a server\(^*\)&nbsp;	\(^*\)to/from a client on a computer network	Term - Explanation
Apache	Apache HTTP Server	Free and OS web server software		Term - Explanation
Service		Group of deamons	<ol><li>System services {process mngmt, login, cron}&nbsp;</li><li>Network service&nbsp;&nbsp;{remote login,DNS, file transfer)</li></ol>	Term - Explanation
DHCP	Dynamic Host Configuration Protocol	Dynamic/automatic IP address assignment		Term - Explanation
NTP	Network Time Protocol	Synchronizes the time/date with a centeralized (NTP) server		Term - Explanation
firewall		Network security system\(^*\)	\(^*\)to monitor/control incoming/outgoing network traffic	Term - Explanation
OpenStack		A tool to manage private, hybrid clouds	see: RHELOSP	Term - Explanation
OpenShift	Kubernetes	A tool to manage a clusters &amp; containers (pods)	see: Red Hat OpenShift	Term - Explanation
RHV	Red Hat Virtualization	A tool to manage VMs		Term - Explanation
CUPS	Common Unix Printing System	Printing service		Term - Explanation
Postfix		Mail transport agent		Term - Explanation
Sendmail		Mail transport agent		Term - Explanation
Systemd		Manages the boot process &amp; <i>system</i> services\(^*\)	\(^*\) using <b>systemctl</b>	Term - Explanation
systemd journal		Gathers logging infos and debugging messages	<b>journalctl</b>	Term - Explanation
rsyslogd	Reliable and Extended Syslog Daemon	Gathers log messages &amp; directs them to /var/log/...\(^*\)	\(^*\)according to /etc/rsyslog.conf	Term - Explanation
BUS	omnibus	Connects components in/attached to a computer	high-speed bus = high-speed computations | e.g. cpu power	Term - Explanation
PCI	Peripheral Component Interconnect Bus	Attaches <i>hardware</i> devices in/onto a computer		Term - Explanation
host bridge		Connects the processor and peripheral PCI-components		Term - Explanation
udevd	Event Managing Daemon	Adds/removs devices\(^*\) from /dev	\(^*\)hardware &amp; software	Term - Explanation
loadable modules	loadable kernel modules	Code to flexible extent the kernel	e.g.: if software is not detected properly	Term - Explanation
Network card	Network Interface Card (NIC)	Connects a device to a network with an ethernet cable	green light: electricity<br>orange light: connection	Term - Explanation
kdump	Kernel Crash Dump	Crash dumps\(^*\) the <i>working memory</i> in terms of a kernel crash	\(^*\)Speicherauszug erstellen	Term - Explanation
Anaconda		A graphical installer for Linux		Term - Explanation
Kickstart file		Gives <i>prior answers–</i>commands–to installation questions\(^*\)	\(^*\)...you normally click through. <br><br>Note: Automate the installation process by passing it as boot option	Term - Explanation
Dual Boot		Multiple OS on the same computer		Term - Explanation
GParted		Gnome's graphical partition editor		Term - Explanation
VNC	Virtual Network Compuing	Remotly control(s) another computer	Note: Graphical desktop sharing system!	Term - Explanation
VNC installation	Virtual Network Computing Installation	Run the installation on computer A from computer B\(^*\)	After you start this type of installation you can go to another system and open a VNC viewer, giving the viewr the address of the installation maschine (192.168.0.99:1)	Term - Explanation
Inital Ram Disk		Modules &amp; tools to start the installer		Term - Explanation
RAID	Redundant Array of Independent Disks	Combines multiple <i>disks</i> to a single logical unit\(^*\)	\(^*\)back-up SSD's and/or performance improvement	Term - Explanation
Partitioning		Divide a disk into logical areas\(^*\)	\(^*\)that can be worked seperately	Term - Explanation
LVM	Logical Volume Management Partition	A unit of a LVM Group allocating space more dynamically &amp; flexible\(^*\) (=logically)&nbsp;	\(^*\)..than traditional storage management in partitions (MBR, GPT). \(\infty\) logical volumes!	Term - Explanation
RAID Partition	Redundant Array of Independent Disks Partition	A unit on a <i>separate</i> disk to build a RAID array\(^*\)	\(^*\)improves performace, reliability, data storage	Term - Explanation
Swap Partition		Extends the system's amout of virtual memory available		Term - Explanation
MBR	Master Boot Record Partition Table	Old standard for partition tables	only &lt;= 4 primary partitions (~BIOS)<br><br><u>Traditional partition</u>&nbsp;vs. logical<i>&nbsp;</i>volume&nbsp;<u>management</u>	Term - Explanation
BIOS	Basic Input Output System	Initializes the hardware &amp; loads the (GRUB) boot loader from the MBR	BIOS + MBR = old standard to start the machine	Term - Explanation
UEFI	Unified Extensible Firmware Interface	Uses UEFI Images to get hardware &amp; OS engaged	UEFI + GPT partition table = newer standard to start the machine&nbsp;	Term - Explanation
GPT	GUID Partition Table	New standard for partition tables	128 primary partitions (~UEFI)<br><br><u>Traditional partition</u> vs. logical<i>&nbsp;</i>volume <u>management</u>	Term - Explanation
Logical Volume		Dynamic partition\(^*\)	\(^*\)non-static partitions simplify resizing, moving &amp; creating new instances without interrupting the system&nbsp;	Term - Explanation
/boot&nbsp;\(\rightarrow\) /boot	Assign Partition to Directory	Ensures the info in /boot is accessible to the BIOS	1024 MiB	Term - Explanation
/var \(\rightarrow\) /var	Assign Partition to Directory	Prevents attacks on FTP &amp; web server from corrupting/filling up the hard disk		Term - Explanation
Mounting		Make a filesystem available to the system\(^*\)	\(^*\)i.e.: after mounting your files will be accessible under the   mount-point	Term - Explanation
xinetd	Extended Internet Service Daemon	Manages Internet Based Connectivity\(^*\)	\(^*\)Listens for incoming requests over a network&nbsp;-- which are made using port numbers --&nbsp; and launches the approriate service	Term - Explanation
crond	Schedueling Daemon	Executes schedueld commands		Term - Explanation
XDG	X Desktop Group, freedesktop.org	An OS project to set a common base for the X Window System		Term - Explanation
Sticky bit (t)	permission set	User can add items but root must delete		Term - Explanation














