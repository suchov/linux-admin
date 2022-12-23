The Linux Administration and Supercharge Your Career
https://www.udemy.com/course/linux-administration

Linux Boot Process

BIOS - basic Input/Output System
POST - Power-On Self Test
Primary purpose is to find and execute the boot loader
It's operating system independent 
Knows about bootable devices:
    -Hard drives
    -USB drives
    -DVD drives
    -etc.
The boot device search order can be changed

Boot Loaders
    -LILO
        -Linux Loader
    -GRUB
        -Grand Unified Bootloader
        -Replaced LILO
    -Boot loaders start the operating systems
    -Boot loaders can start the operating system with different options

Initial RAM Disk
    -initrd
        -initial RAM disk
    -Temporary filesystem that is loaded from disk and stored in memory
    -Contains helpers and modules required to load the permanent OS file system.
    -Temporary filesystem that is loaded from disk and stored in memory
    -Contains helpers and modules required to load the permanent OS file system.

The /boot Directory

-/boot
    - 
