The Linux Administration and Supercharge Your Career
https://www.udemy.com/course/linux-administration

### Linux Boot Process

BIOS - basic Input/Output System
POST - Power-On Self Test
Primary purpose is to find and execute the boot loader
It's operating system independent 
Knows about bootable devices:
- Hard drives
- USB drives
- DVD drives
- etc.
The boot device search order can be changed

### Boot Loaders

- LILO
        -Linux Loader
- GRUB
        -Grand Unified Bootloader
        -Replaced LILO
- Boot loaders start the operating systems
- Boot loaders can start the operating system with different options

### Initial RAM Disk
- initrd
  - initial RAM disk
- Temporary filesystem that is loaded from disk and stored in memory
- Contains helpers and modules required to load the permanent OS file system.
- Temporary filesystem that is loaded from disk and stored in memory
- Contains helpers and modules required to load the permanent OS file system.

### The /boot Directory

-/boot
 - Contains the files required to boot Linux
 - initrd
 - kernel
 - boot loader configuration

$ ls -F /boot
The kernel is usually called - vmlinuz or vmlinux
If the kernel is compress its name ends NZ

### Kernel Ring Buffer
- Contains messages from the Linux kernel
- dmesg
- /val/log/dmesg

### Runlevels / Description

0 - Shuts down the system
1, S, s - Single user mode. Used for maintenance.
2 - Multi-user mode with graphical interface.(Debian/Ubuntu)
3 - Multi-user text mode(RedHat/CentOS)
4 - Undefined
5 - Multi-user mode with graphical interface.(RedHat/CentOS)
6 - Reboot
traditionally controled by the init program:
/etc/inittab:

Systemd - alternative to init.
/lib/system/system
ls -l runlevel5.target

### Changing runlevels or target
telinit RUNLEVEL
 telinit 5
systemctl isolate TARTET
 systemctl isolate graphical.target

### Rebooting
sutdown [options] time [message]

sutdown -r 15:30 "rebooting!"
sutdown -r +5 "rebooting soon!"
sutdown -r now

### Poweroff
telinit 0
systemctl isolate poweroff.target
poweroff

END of THE LESSON 1

## The linex boot demo

inside the /boot directory
systemctl isolate graphical.target 
load the graphical interface of the linux from the terminal, nice!

## System Logging

-The syslog standard
-Facilities and severities
-Syslog servers
-Logging rules
-Where logs are stored
-How to generate your own log messages
-Rotating log files

### The Syslot Standard
-Aids in the processing of messages.
-Allows logging to be centrally controlled.
-Uses facilities and severities to categorize messages.

Number Keyword Description
0 kernel    kernel messages
1 user      user-level messages
2 mail      mail system
3 daemon    system daemons
4 auth      security/authorization messages
5 syslog    messages generated by syslogd
6 lpr       line printer sybsystem
7 news      network news subsystem
8 uucp      UUCP subsystem
9 clock     daemon
10 authpriv security/authorization messages

Number Keyword Description
11 ftp      FTP daemon
12 -        NTP subsystem
13 -        log audit
14 -        log alert
15 cron     clock daemon
16 local0   local use 0 (local0)
17 local1   local use 0 (local1)
18 local2   local use 0 (local2)
19 local3   local use 0 (local3)
...
23 local7   local use 0 (local7)

Code Severity   Keyword       Description
0    Emergency  emerg (panic) System is unstable
1    Alert      alert         Action must be taken immediately
2    Critical   crit          Critical conditions 
3    Error      err(error)    Error conditions
4    Warning    warning(warn) Warning conditions
5    Notice     notice        Normal but significant condition
6    Info       info          Informational messages
7    Debug      debug         Debug-level messages

### Syslog Servers
- Process syslog messages based on rules.
- syslogd
- rsyslog
- syslog-ng
(alternatives)

### rsyslog

/etc/rsyslog.conf:

$IncludeConfig /etc/rsyslog.d/*.conf

