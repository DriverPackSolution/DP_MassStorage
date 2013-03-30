Readme file for HPT370/370A/372/372A/372N/302/302N ATA RAID Controller
BIOS & Device Drivers

Copyright (C) HighPoint Technologies, Inc. All rights reserved.
Last updated on Jan 5, 2004

Please review this file for important information about compatibility issues and 
differences in operation that were discovered after our product manuals were 
created. In case of conflict among various parts of the documentation set, this 
file contains the most current information.

Note: The latest firmware and product documentation will be available for 
download at http://www.highpoint-tech.com

This file is divided into the following major sections:

1. Software Version
2. Files Listing
3. Revision History
4. BIOS Update
5. Known Problems

1. Software Version
====================

    BIOS version: v2.351
    Driver version: v2.351
    
    Operating Systems:
       Windows 98/ME
       Windows NT 4.0
       Windows 2000
       Windows XP
       Windows 2003


    Version Compatibility:
       This BIOS/driver can be used with HighPoint RAID Management Software v2.32
       or later.

2. Files Listing
=================
    Readme.txt                  This file
    BIOS
     |_ load.exe                BIOS loading utility (HighPoint) not for all Type of
     |                           Flash-ROM
     |_ flash100.com            BIOS loading utility (Dawicontrol)
     \_ bios.bin                HPT372A/372N(DID5) controller BIOS
    win98_me                    Windows 98/ME driver
     |_ hpt3xx.inf
     |_ hpt3xx.mpd
     |_ hptpwr.vxd
     \_ hptwrap.vxd
    win_nt                      Windows NT 4.0 driver
     |_ hpt3xx.inf
     |_ hpt3xx4.inf
     |_ hpt3xx6.inf
     \_ hpt3xx.sys
    win_2k                      Windows 2000 driver
     |_ hpt3xx.inf
     |_ hpt3xx.cat
     |_ hpt3xx.sys
     \_ hptpro.sys
    win_xp                      Windows XP driver
     |_ hpt3xx.inf
     |_ hpt3xx.cat
     |_ hpt3xx.sys
     \_ hptpro.sys
    win_2003                    Windows 2003 driver
     |_ hpt3xx.inf
     |_ hpt3xx.cat
     |_ hpt3xx.sys
     \_ hptpro.sys
    disk1                       Driver disk label
    txtsetup.oem                Windows NT/2k/XP setup file


3. Revision History
====================

   v2.351 01/05/2004
         * Add "use private stack" option in BIOS (to fix DOS6.22 booting fail)
         * Fix 66M PCI support

   v2.35  08/04/2003
         * Add 302/302N support
	
   v2.345 05/09/2003
         * Fix compatibility issue with Intel SATA RAID BIOS
         * Fix Windows "LDM configuration disk write error"

   v2.344 04/11/2003
         * Fix clock calculation
         * Fix driver compatibility issue on SOYO SY-P4IP mainboard

   v2.342 03/24/2003
         * Fix HPT370A timing
         * Add RAID 1.5 support

   v2.34 10/17/2002
         * Add HPT372N controller support
         * Fix hptpro.sys compatibility issue with NIS2003 on FAT partition

   v2.33 09/17/2002
         * Fix 48bit LBA compatibility
         * Add RocketMate support

   v2.32 07/01/2002
         * Fix 48bit LBA formatting issue
         * Fix hptpro.sys problem on Windows XP system restore and sparse files
         * use PMM to allocate BIOS memory
         * Disable BIOS EBDA reallocation by default

   v2.31 01/09/2002
         * Performance improved
         * Fix BIOS compatibility issue with Adaptec SCSI
         * Fix Seagate Barracuda III and IV mode to ATA100
         * Show capacity by 1G=1,000,000,000 Bytes
         * Fix BIOS bug "drive capacity incorrect after deleting a broken array"

   v2.3  12/20/2001
         * Add support for stripe size 128K-2M
         * Support multi controller
         * Modify driver for HPT370/370A compatibility
         * Fix reading ATA/133 disk error when PCI clock is lower than 33MHz
         * Fix compatibility problem with Intel IAA driver under Windows ME
         * Fix BIOS compatibility issue with MSI845 mainboard

   v2.2  12/08/2001

         * Performance improved
         * Fix GUI re-open bug when rebuilding an array
         
   v2.1  11/15/2001
         
         * Add 48bit LBA (Big Drive) support
         * Fix BIOS display problem on S3 display adapter
         * Fix BIOS BBS support
         * Fix Windows ME hibernating problem
  

4. BIOS Update
===============

  To update BIOS for onboard HPT3xx controller, please refer to your
  mainboard manual or contact the hardware vendor for updating BIOS.
    
  To update BIOS for HPT3xx adapter, you can use HighPoint BIOS loading
  utility.
  
  * Notes for BIOS update from v2.0.xxxx on adapters with auto-load enabled
  
    If your HPT370/370A adapter has auto-load feature enabled, PCI configuration
    header may change after you update BIOS. This will cause Windows 2000/XP 
    unable to boot from the controller. To avoid this problem, you must use load
    utility v2.1.12.22 or later and specify the following parameters to update 
    BIOS:
           load bios372.231 /e 408=1800003,42c=51103


5. Known Problems
==================

  * Install OS to devices attached to HPT3xx controller

    Before installing OS to devices attached to HPT3xx controller, you must
    remove the drives connected to other controllers from your system temporarily.
    After OS installation complete, you can put them back.
    
  * Windows XP upgrade installation
  
    When doing an upgrade installation of Windows XP (before Service Pack 1)
    with HPT3xx controller, Windows XP will use HPT370 driver in its
    driver package and prevent user to specify a new driver. To solve this 
    problem you can do the upgrade as below:
    
    1. Run XP upgrade program in a running system.
    2. When setup finished copying files and ask reboot, DO NOT reboot.
    3. Open WinXP temporary installation folder ($WIN_NT$.~BT)  and search for 
       txtsetup.sif file.
    4. Open txtsetup.sif with Notepad, remove the line "hpt3xx=hpt3xx.sys,4" 
       under section [scsi.load] by adding a semicolon before that line. 
    5. Save the file and reboot.
    6. Start XP setup as normal. When setup prompt "Press F6 to add SCSI driver",
       press F6 and specify the new driver to be loaded.
    7. During text-mode setup, Windows XP may still copy the built-in HPT370 driver
       to the final Windows installation's System32\Drivers directory. To use the
       new driver, you must replace the old one before you continue into graphic-mode
       setup. This can be done by booting from a DOS floppy if you are using FAT 
       or FAT32 file system; if you use NTFS file system, you have to use some 
       other method to replace the built-in driver.
    
    There are more information about this issue on Microsoft support site:
       http://support.microsoft.com/default.aspx?scid=kb;en-us;Q225125
       http://support.microsoft.com/default.aspx?scid=kb;en-us;Q220845
       
  * Install HPT370/370A controller on an existing Windows XP system
  
    When installing HPT370/370A controller on an existing Windows XP system,
    Windows XP may try to install its HPT370 driver first; this may cause
    system hang when you are using new features the driver don't support.
    To avoid this problem, you shall update the driver first with no drives 
    attached to HPT370/370A controller, shutdown the system, attach the
    drives, then start the system again.

  * Compatibility issue with Adaptec SCSI adapter
  
    If you encounter compatibility problems when you use HPT3xx controller 
    together with Adaptec SCSI adapter, please try to disable EBDA reallocation
    in Adaptec SCSI BIOS, or enable "EBDA reallocation" in HPT3xx BIOS. 
    You can use BIOS loading utility v2.2.07.01 or later to enable this 
    feature (e.g. "load /c bios372.232").

  * Moving disks to other IDE controllers

    When you want to use disks previously attached to HPT370/370A/372 controller on
    other IDE controllers, please first delete any array information on the 
    disks. Otherwise your data may be lost when you want to put it back later.

  * Rescanning disks

    There is a limitation for the refresh function in RAID Management Software.
    If you remove a disk from the controller but the software does not notice this
    event, it is also unable to notice the event when you plug another disk back
    to that location. You must force a refresh action before changing the disk.

  * Problem on two disks with same signature under Windows 98/ME
  
    If you break a RAID 1 array into two single disks without destroying data and 
    use both of them under Windows 98/ME, Windows will behave abnormally since
    there are two volumes with same Windows signature. To solve the problem, boot
    into MS-DOS mode and run "fdisk /mbr".
