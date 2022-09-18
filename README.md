These are the original "OPENWODE.RAR" archive contents.

Please refer to file "OpenWode_GettingStarted_20110520.pdf" for instructions on how to start.

Please also see https://vermillion57.wixsite.com/wode-re for more information on the WODE internals, hardware and so on.

Update:
=======

This archive, while it's in the original state, does NOT contain:

- Bootloader source code (U-Boot v1.3.4 incl. LPC313x patches, DirectC driver code and custom code additions)
- Bootloader AES key *
- "WODE" binary source code used within the WODE Linux Kernel for interaction on the LCD screen

These were never released and most likely never will.

Even after so many years and the possibility to use softmods, they should have been instead.

Maybe anyone is willing to help in getting into contact with "TheArtificer", who also did the software aspect of the Xk3y.

Thanks in advance.

* - The WODE Bootloader AES key was dumped on May, 23rd 2022 at 06:18pm after
    hacking the LPC3143 MCU by VCC glitching the 1.2V power rail which is used
    for devices like USB-OTG, OTP, SD/MMC and so on. By obtaining the Bootloader
    AES key, it was almost possible to reverse the bootloader source code and
    compile a custom-bootloader binary which includes the exact same functionality
    as the stock bootloader.

SHA-256 of the Bootloader AES key: 1C08F957CD7E5AC4065D9CDEA23604590A1EFFC2507F720385907941580812C2

NOTE - The LPC3143 boot flow looks like this:

BOOTROM -> Bootloader -> Kernel -> APP

Patch:
======

The "patch-openwode-git.diff" should make OPENWODE compile on newer Linux distributions.

After setting up the main repository, the end user needs to "cd" into the actual repositories' root folder and issue a...

* - patch -p1 < [PATH-TO-patch-openwode-git.diff]

...command on the shell. Then you run the commands...

* - ./build.sh prepare

...and...

* - ./build.sh build

...to compile this.

Additional refs: 
================

* - https://github.com/alicemirror/Open-Wode-Backfire - Enrico Miglino a. k. a. "AliceMirror" who was working on the WODE Linux Kernel
* - https://www.mail-archive.com/openwrt-devel@lists.openwrt.org/msg06818.html - Signs of life for Kernel development
* - https://lists.denx.de/pipermail/u-boot/2009-March/049975.html - Signs of life for Bootloader development
* - https://web.archive.org/web/20200527211318/https://wode.obeygravity.de/YouAreRoot - Regarding source code release
