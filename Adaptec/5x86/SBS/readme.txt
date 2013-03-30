--------------------------------------------------------------------
README.TXT
                          
Adaptec ASR-5085/ASR-5405/ASR-5445/ASR-5805/ASR-51245/ASR-51645/ASR-52445 Unified Serial Controllers                       
Adaptec ASR-5405Z/ASR-5445Z/ASR-5805Z Unified Serial Controllers
Adaptec ASR-5805Q/ASR-5805ZQ Unified Serial Controllers
Adaptec ASR-3405/ASR-3805 Unified Serial Controllers
Adaptec ASR-2045/ASR-2405/ASR-2405Q/ASR-2805 Unified Serial Controllers
                          
NOTE:  All Adaptec products are UL listed and for use only with UL listed ITE.

as of December 15, 2010
--------------------------------------------------------------------
Please review this file for important information about issues
and errata that were discovered after completion of the standard
product documentation. In the case of conflict between various
parts of the documentation set, this file contains the most
current information.

NOTE: The latest firmware, BIOS, drivers and documentation can be 
downloaded from www.adaptec.com when they become available.

The following information is available in this file:

   1. Software and Documentation
      1.1  Controller & Utility Software
      1.2  Documentation on this CD
   2. Installation and Setup
      2.1  Installation Instructions
      2.2  MaxIQ Cache Software Setup
      2.3  Power Management Setup
      2.4  Linux Setup
   3. General Cautions
   4. Known Limitations
      4.1  ACU Utility
      4.2  AFU Utility      
      4.3  Creating an Array from the Adaptec Installation CD
      4.4  Using the Controller with an Adaptec S50 JBOD Enclosure
      4.5  UnixWare and OpenServer
      4.6  OpenServer 6.0
      4.7  SuSE Linux Enterprise Server 10 with Service Pack 2
      4.8  Hot-adding Disk Drives
      4.9  SuperMicro Disk Drive Enclosures
      4.10 Using the Controller with a Seagate Barracuda 1TB SATA Drive 
      4.11 Intel SE7525RP2 and SE7320EP2 Motherboards
      4.12 Windows Server 2008 64-Bit SCSIport Driver
      4.13 Boot Drive Failure after OCE/RLM
      4.14 Online Capacity Expansion (OCE) Limits
      4.15 Power Management under FreeBSD
      4.16 Using RAID10 under FreeBSD
      4.17 Power Management with Seagate SAS Drive ST31000640SS
      4.18 Linux Cache Synchronization
      4.19 Listing Devices in VMware ESX 4.0 Console
      4.20 BIOS Hangs When Booting RAID Controller with Batteryless Backup (ZMCP)
      4.21 Updating Firmware on Hitachi HUS1514xxVLS300 SAS drives
      4.22 Installing Windows OS from Direct-Attached Non-DASD Device     
      4.23 MaxIQ SSD Cache Performance
      4.24 Exceeding 2TB LUN Size on VMware ESX Server 
      4.25 PHY Rate Limitations on Western Digital Hard Drives
      4.26 Changing the Stripe Size for Large RAID Arrays 
      4.27 Hot-Adding MaxIQ SSDs
               
--------------------------------------------------------------------
1. Software and Documentation
   
   1.1. Controller & Utility Software

       - Adaptec Firmware/BIOS/Driver/Utilities Version 5.4

         NOTE: The latest versions of firmware, BIOS, driver software 
         and utilities can be downloaded from the Adaptec Web Site at 
         www.adaptec.com.
                          
       - Windows Drivers, All Controllers
          
          o Windows Server 2008, Enterprise, Standard, Datacenter (32-bit, 64-bit)
          o Windows Server 2008 R2, Enterprise, Standard, Datacenter (64-bit)
          o Windows Server 2003, Enterprise, Standard, Datacenter (32-bit, 64-bit)
          o Windows XP, Windows Vista, Windows 7 (all versions)

       - Windows Drivers, 5-Series & 2-Series Controllers Only

          o Windows Server 2003 R2, Enterprise, Standard, Datacenter (32-bit, 64-bit)

        - Linux Drivers, All Controllers

          o Red Hat Enterprise Linux 4.8, IA-32 and x64
          o Red Hat Enterprise Linux 5.4,  IA-32 and x64
          o SuSE Linux Enterprise Server 9 SP2 SP3 SP4, IA-32 and x64     
          o SuSE Linux Enterprise Server 10 SP2, IA-32 and x64     

        - Linux Drivers, 5-Series & 2-Series Controllers Only

          o SuSE Linux Enterprise Server 11, IA-32 and x64

        - FreeBSD Drivers, 3-Series Controllers Only

          o FreeBSD 6.1, 6.0

        - FreeBSD Drivers, 5-Series & 2-Series Controllers Only

          o FreeBSD 6.4, 7.2, 8.0
        
        - SCO Drivers

          o OpenServer 6.0 MP4
          o UnixWare 7.1.4

        - VMware Drivers, All Controllers
       
          o VMware ESX Server 3.x
          
        - VMware Drivers, 5-Series & 2-Series Controllers Only
 
          o VMware ESX Server 4.0
          
        - Sun Solaris Drivers
        
          o Solaris 10 Update 7
       
   1.2 Documentation on this CD
   
        - Adaptec SAS RAID Controllers Installation and User's Guide
        - Adaptec SAS RAID Controllers Quick Start Guide
        - Adaptec Storage Manager User's Guide for Direct Attached Storage
        - Adaptec RAID Controller Command Line Utility User's Guide
        - Adaptec SAS RAID Controllers README.TXT file
        
--------------------------------------------------------------------
2. Installation and Setup

  2.1  Installation Instructions

       The Adaptec SAS RAID Controllers Installation and User's Guide
       contains complete installation information for the controllers
       and drivers, as well as complete instructions for all 
       utilities. The Adaptec Storage Manager User's Guide 
       contains complete installation information for the Adaptec 
       Storage Manager software.
       
  2.2  MaxIQ SSD Cache Software Setup (5-Series & 2-Series Controllers Only)
  
       o The Adaptec MaxIQ SSD Cache Performance Kit supports 
         Adaptec MaxIQ-branded/Intel X25-E Solid State Drives only.
         
       o Adaptec Q-series controllers support any MaxIQ-compatible
         SSD on the compatibility list; see www.adaptec.com/compatibility.
         
       o You can install a maximum of 8 SSDs on a controller for 
         MaxIQ caching.       
                
       See the user's guide for complete MaxIQ SSD installation and
       setup instructions.
    
  2.3  Power Management Setup (5-Series & 2-Series Controllers Only)

       You must use a compatible combination of Adaptec Storage Manager  
       and controller firmware and driver software to use the power  
       management feature. All software components must support power
       management. You can download the latest controller firmware 
       and drivers from the Adaptec Web site at www.adaptec.com.

  2.4  Linux Setup
  
       Before installing the Linux operating system on a logical drive,  
       Adaptec recommends clearing (removing) old data first. If you
       do not remove old data prior to installation, the OS may
       not boot. As a workaround, use the boot parameter 'aacraid.wwn=2'.     
                     
--------------------------------------------------------------------
3. General Cautions 

   - While an array is being built or cleared, do NOT remove and 
     re-insert any drive in that array. Doing so may cause 
     unpredictable results for any of the controller's arrays.
     
   - Do NOT move drives containing an array from one controller
     to another while the power is on. Doing so could cause
     the loss of the array configuration or data, or both. 
     Instead, power off both affected controllers, move the  
     drives, and then restart.
          
--------------------------------------------------------------------
4. Known Limitations

  4.1  ACU Utility

       o If a non-MaxIQ (generic) SSD is connected to the controller
         on a lower port number than an Adaptec MaxIQ SDD, you cannot
         use the ACU utility to add the MaxIQ SSD to the MaxIQ pool. 
         You must use Adaptec Storage Manager. 
       
         NOTE: Adaptec Q-series controllers do not have this limitation.               
       
       o On some Intel and IBM systems, when you try to run the ACU
         utility, this message appears:
       
         "Not enough free memory to load the utility!
          Press any key to attempt loading the utility forcibly
          OR Wait for the system initialization to be completed 
          [Default]"
       
         This is normal. On Intel systems, wait for the system 
         initialization to be completed. Then the ACU will run. On IBM
         systems, press any key when prompted to load the utility 
         forcibly.
         
       o The ACU erroneously displays deleted logical drives in the
         JBOD list. The logical drive(s) continue to appear in the  
         JBOD list until you delete all of the JBODs.
         
       o With some enclosures, the ACU displays incorrect box/slot 
         information for managed disk drives; for example, 
         Exp/Phy instead of Box/Slot.             

  4.2  AFU Utility

       o When running the AFU in Menu Mode, you can update (flash) only 
         one controller at a time. You must reboot the system before 
         updating the next controller.
       
       o Flashing a 5-series high-port controller (51245, 51645, 52445)
         with down-level firmware and an older version of the AFU crashes
         the system. To recover, you must use a Mode 0 reset using the
         latest firmware version. See the user's guide for details on 
         the Mode 0 method. 

  4.3  Creating an Array from the Adaptec Installation CD

       When you create an array with Adaptec Storage Manager in
       bootable-CD Mode, the maximum size of the array is 2 TB.

  4.4  Using the Controller with an Adaptec S50 JBOD Enclosure

       Temperature warnings from the Adaptec S50 JBOD Enclosure with 
       firmware version T016 are not shown in Adaptec Storage Manager 
       (or on the enclosure). To correct the problem, upgrade to the 
       latest firmware version.

  4.5  UnixWare and OpenServer

       Adding or moving controllers in an existing UnixWare or OpenServer 
       system may cause some device resources to change, which may lead 
       to the operating system being unable to boot. Currently, there 
       is no workaround available in the operating system. Before 
       installing the operating system, make sure all PCI devices are 
       either enabled or installed.        
       
  4.6  OpenServer 6.0

       Arrays may not be displayed correctly, even after you restart
       your computer. 

       To resolve the problem:

       As root, run 'resmgr -r -m vtoc' until it fails. Then, as 
       root, run '/etc/conf/bin/idconfupdate -f'. Then, reboot.
       
  4.7  SuSE Linux Enterprise Server 10 with Service Pack 2
  
       If your boot array is installed on the controller, and the boot
       OS is SLES10 SP2 with driver version 1.1.5-2458, you must add 
       'aacraid.wwn=1' to the kernel boot command line. Alternatively, 
       install the latest aacraid driver.                      
       
  4.8  Hot-adding Disk Drives

       o If you hot-add multiple disks simultaneously to a large 
         configuration (100 disk drives or more), it may take a great 
         deal of time before those disk drives appear in Adaptec 
         Storage Manager.

       o With Intel Backplanes AXX4DRV3GEXP and AXX6DRV3GEXP, if a drive 
         bay is empty at enclosure power on and then a SATA disk drive  
         is hot-added into the empty bay, the controller does not detect
         the new disk drive. To work around this issue, remove and  
         re-insert the SATA disk. 

  4.9  SuperMicro Disk Drive Enclosures

       If the controller does not detect disk drives installed in a 
       SuperMicro M28E2 Mobile Rack, use backplane SAS connectors  
       marked with "SAS In" only.       
       
  4.10 Using the Controller with a Seagate Barracuda 1TB SATA Drive 
       
       To ensure reliability when using Adaptec 2-series and 5-series 
       controllers with a Seagate Barracuda ES.2 1TB SATA Drive 
       (ST31000340NS), Adaptec recommends using Seagate firmware 
       version AN05 or SN06 or higher. 
                
  4.11 Intel SE7525RP2 and SE7320EP2 Motherboards       
    
       The Intel SE7525RP2 and SE7320EP2 motherboards do not support 
       Mode 0 flash. These motherboards use 64-bit PCI addressing.
       The AFU currently supports 32-bit PCI addresses only.

  4.12 Windows Server 2008 64-Bit SCSIport Driver
  
       The Windows Server 2008 64-Bit SCSIport driver is in the process
       of being certified and is not supported in this release. Use 
       the Storport driver instead.
              
  4.13 Boot Drive Failure after OCE/RLM
       
       The system may fail to boot after a boot drive OCE/RLM (online
       capacity expansion/RAID level migration). To correct the problem, 
       verify that the boot drive is still listed as the first logical 
       device in Adaptec Storage Manager (ASM). If not, use the 
       Control-A BIOS utility to reselect the proper boot device.
  
  4.14 Online Capacity Expansion (OCE) Limits
  
       This release supports a maximum of 8 concurrent OCE tasks in 
       the RAID array migration wizard.         
  
  4.15 Power Management under FreeBSD
  
       The FreeBSD driver does not support power management in  
       this release.
       
  4.16 Using RAID10 under FreeBSD
  
       If a RAID10 array fails under FreeBSD the firmware may crash
       causing the system to reboot automatically.
  
  4.17 Power Management with Seagate SAS Drive ST31000640SS
     
       Power Management is not supported by the Seagate ST31000640SS
       SAS drive. (The drive powers down but will not power up without 
       rebooting.)       
                  
  4.18 Linux Cache Synchronization

       With Linux driver 1.1-5-2459 (or higher), you may see an improvement
       in performance if you suppress cache synchronization. For a 
       controller with battery back-up, add 'options aacraid cache=6' to 
       the /etc/modprobe.conf.local file. To completely suppress cache 
       synchronization, add 'options aacraid cache=2'. Then, reboot. 
       Note that the smaller value provides no protection in case of a       
       power outage.
       
  4.19 Listing Devices in VMware ESX 4.0 Console
  
       After deleting an array with ARCCONF, the VMware ESX 4.0 Console
       will hang if you list available devices with 'fdisk -l'. As a 
       work-around, rescan first, then try 'fdisk -l'.
       
  4.20 BIOS Hangs When Booting RAID Controller with Batteryless Backup (ZMCP)

       Possible Cause: After a system shutdown, the ZMM-100DB daughterboard 
       remains active for several minutes. The Super Cap connector may have  
       been improperly removed and/or re-inserted with a charge still present. 

       Solution: Plug the Super Cap connector in when the system is off 
       and, if the yellow activity LED is illuminated on the ZMM-100DB  
       daughterboard attached to RAID Controller, wait for the LED 
       activity indicator to go out. This may take several minutes.  
       The system should then boot normally. 

  4.21 Updating Firmware on Hitachi HUS1514xxVLS300 SAS drives       

       Firmware upgrade on Hitachi HUS151473VLS300 and HUS151436VLS300 
       SAS drives is not supported for packet sizes below 4K (512/1024/2048).

  4.22 Installing Windows OS from Direct-Attached Non-DASD Device
  
       Adaptec RAID controllers do not support Windows OS installation from  
       direct-attached Non-DASD devices ("Direct Access Storage Devices"),    
       such as a tape drive, CD-ROM, or DVD-ROM. Adaptec recommends  
       using a motherboard IDE or SATA DVD-ROM/CD-ROM device to install
       the Windows OS on a RAID array.

  4.23 MaxIQ SSD Cache Performance
            
       The MaxIQ cache contents is lost if the OS is not shut down
       cleanly (for example, by pressing the reboot button or
       pulling the power). When the system is restarted, the cache
       is rebuilt. Until that time, you may see a temporary loss
       in performance.
       
  4.24 Exceeding 2TB LUN Size on VMware ESX Server
  
       Under VMware, if you create a logical drive with greater than 
       2TB of capacity, the OS will only be able to access the remaining 
       storage above 2TB. For instance, with the 3.5TB LUN, only
       1.5TB will be accessible; with a 5TB LUN, only 1TB will
       be accessible (first 2TB+2TB are skipped); and so on.      
       
  4.25 PHY Rate Limitations on Western Digital Hard Drives
    
       To avoid data-phase errors with certain Western Digital hard 
       drives, the PHY rate must be set 1.5Gb/s rather than the 
       maximum rate of 3.0Gb/s. 
       
       o For Western Digital WD2002FYPS and WD20EADS hard drives, the 
         PHY rate is set automatically to 1.5Gb/s.
                     
       You can set the PHY rate to Auto (default), 1.5Gb/s, or 3.0Gb/s. 
       in the Control-A/BIOS utility.       
              
       NOTE: For Adaptec low-port RAID controllers, the device  
             properties in ASM and the BIOS utility will continue    
             to report the maximum PHY rate (3.0Gb/s), not the reduced 
             rate. For high-port controllers, the PHY rate is 
             reported correctly.
             
  4.26 Changing the Stripe Size for Large RAID Arrays
  
       For large RAID arrays, a RAID-level migration may fail with a 
       firmware crash if you reconfigure the array with a different
       stripe size. No data is lost, however. 
       
       Known migrations that result in a FW crash include:
       
       o 16/32/64/128 drive R0- 256/16 to 16/256 stripe change
       o 16/32/64/128 drive R0- 512/16 to 16/512 stripe change
       o 16/32/64/128 drive R0- 1024/16 to 16/1024 stripe change
       o 16/32 drive R5- 16 to 512/1024 stripe change
       o 16/32 drive R5- 512/1024 to 16 stripe change
       o 16/32 drive R6- 1024/16 to 16/1024 stripe change
       
  4.27 Hot-Adding MaxIQ SSDs
       
       If you remove two or more MaxIQ SSDs and then re-insert  
       them at the same time, only one will be recognized as part 
       of the MaxIQ pool. To reconstitute the pool, use Adaptec
       Storage Manager or the BIOS Utility to reconfigure  
       the MaxIQ cache. 

                    .                                    
--------------------------------------------------------------------
(c) 2010 Adaptec by PMC. All Rights Reserved. 

This software contains the valuable trade secrets of Adaptec or its
licensors. The software is protected under international copyright
laws and treaties. This software may only be used in accordance with 
the terms of its accompanying license agreement.

No part of this publication may be reproduced, stored in a retrieval
system, or transmitted in any form or by any means, electronic,
mechanical, photocopying, recording or otherwise, without prior
written consent of --------------------------------------------------------------------
README.TXT
                          
Adaptec ASR-5085/ASR-5405/ASR-5445/ASR-5805/ASR-51245/ASR-51645/ASR-52445 Unified Serial Controllers                       
Adaptec ASR-5405Z/ASR-5445Z/ASR-5805Z Unified Serial Controllers
Adaptec ASR-5805Q/ASR-5805ZQ Unified Serial Controllers
Adaptec ASR-3405/ASR-3805 Unified Serial Controllers
Adaptec ASR-2045/ASR-2405/ASR-2405Q/ASR-2805 Unified Serial Controllers
                          
NOTE:  All Adaptec products are UL listed and for use only with UL listed ITE.

as of August 17, 2010
--------------------------------------------------------------------
Please review this file for important information about issues
and errata that were discovered after completion of the standard
product documentation. In the case of conflict between various
parts of the documentation set, this file contains the most
current information.

NOTE: The latest firmware, BIOS, drivers and documentation can be 
downloaded from www.adaptec.com when they become available.

The following information is available in this file:

   1. Software and Documentation
      1.1  Controller & Utility Software
      1.2  Documentation on this CD
   2. Installation and Setup
      2.1  Installation Instructions
      2.2  MaxIQ Cache Software Setup
      2.3  Power Management Setup
      2.4  Linux Setup
   3. General Cautions
   4. Known Limitations
      4.1  ACU Utility
      4.2  AFU Utility      
      4.3  Creating an Array from the Adaptec Installation CD
      4.4  Using the Controller with an Adaptec S50 JBOD Enclosure
      4.5  UnixWare and OpenServer
      4.6  OpenServer 6.0
      4.7  SuSE Linux Enterprise Server 10 with Service Pack 2
      4.8  Hot-adding Disk Drives
      4.9  SuperMicro Disk Drive Enclosures
      4.10 Using the Controller with a Seagate Barracuda 1TB SATA Drive 
      4.11 Intel SE7525RP2 and SE7320EP2 Motherboards
      4.12 Windows Server 2008 64-Bit SCSIport Driver
      4.13 Boot Drive Failure after OCE/RLM
      4.14 Online Capacity Expansion (OCE) Limits
      4.15 Power Management under FreeBSD
      4.16 Using RAID10 under FreeBSD
      4.17 Power Management with Seagate SAS Drive ST31000640SS
      4.18 Linux Cache Synchronization
      4.19 Listing Devices in VMware ESX 4.0 Console
      4.20 BIOS Hangs When Booting RAID Controller with Batteryless Backup (ZMCP)
      4.21 Updating Firmware on Hitachi HUS1514xxVLS300 SAS drives
      4.22 Installing Windows OS from Direct-Attached Non-DASD Device     
      4.23 MaxIQ SSD Cache Performance
      4.24 Exceeding 2TB LUN Size on VMware ESX Server 
      4.25 PHY Rate Limitations on Western Digital Hard Drives
      4.26 Changing the Stripe Size for Large RAID Arrays 
      4.27 Hot-Adding MaxIQ SSDs
               
--------------------------------------------------------------------
1. Software and Documentation
   
   1.1. Controller & Utility Software

       - Adaptec Firmware/BIOS/Driver/Utilities Version 5.4

         NOTE: The latest versions of firmware, BIOS, driver software 
         and utilities can be downloaded from the Adaptec Web Site at 
         www.adaptec.com.
                          
       - Windows Drivers, All Controllers
          
          o Windows Server 2008, Enterprise, Standard, Datacenter (32-bit, 64-bit)
          o Windows Server 2008 R2, Enterprise, Standard, Datacenter (64-bit)
          o Windows Server 2003, Enterprise, Standard, Datacenter (32-bit, 64-bit)
          o Windows XP, Windows Vista, Windows 7 (all versions)

       - Windows Drivers, 5-Series & 2-Series Controllers Only

          o Windows Server 2003 R2, Enterprise, Standard, Datacenter (32-bit, 64-bit)

        - Linux Drivers, All Controllers

          o Red Hat Enterprise Linux 4.8, IA-32 and x64
          o Red Hat Enterprise Linux 5.4,  IA-32 and x64
          o SuSE Linux Enterprise Server 9 SP2 SP3 SP4, IA-32 and x64     
          o SuSE Linux Enterprise Server 10 SP2, IA-32 and x64     

        - Linux Drivers, 5-Series & 2-Series Controllers Only

          o SuSE Linux Enterprise Server 11, IA-32 and x64

        - FreeBSD Drivers, 3-Series Controllers Only

          o FreeBSD 6.1, 6.0

        - FreeBSD Drivers, 5-Series & 2-Series Controllers Only

          o FreeBSD 6.4, 7.2, 8.0
        
        - SCO Drivers

          o OpenServer 6.0 MP4
          o UnixWare 7.1.4

        - VMware Drivers, All Controllers
       
          o VMware ESX Server 3.x
          
        - VMware Drivers, 5-Series & 2-Series Controllers Only
 
          o VMware ESX Server 4.0
          
        - Sun Solaris Drivers
        
          o Solaris 10 Update 7
       
   1.2 Documentation on this CD
   
        - Adaptec SAS RAID Controllers Installation and User's Guide
        - Adaptec SAS RAID Controllers Quick Start Guide
        - Adaptec Storage Manager User's Guide for Direct Attached Storage
        - Adaptec RAID Controller Command Line Utility User's Guide
        - Adaptec SAS RAID Controllers README.TXT file
        
--------------------------------------------------------------------
2. Installation and Setup

  2.1  Installation Instructions

       The Adaptec SAS RAID Controllers Installation and User's Guide
       contains complete installation information for the controllers
       and drivers, as well as complete instructions for all 
       utilities. The Adaptec Storage Manager User's Guide 
       contains complete installation information for the Adaptec 
       Storage Manager software.
       
  2.2  MaxIQ SSD Cache Software Setup (5-Series & 2-Series Controllers Only)
  
       o The Adaptec MaxIQ SSD Cache Performance Kit supports 
         Adaptec MaxIQ-branded/Intel X25-E Solid State Drives only.
         
       o Adaptec Q-series controllers support any MaxIQ-compatible
         SSD on the compatibility list; see www.adaptec.com/compatibility.
         
       o You can install a maximum of 8 SSDs on a controller for 
         MaxIQ caching.       
                
       See the user's guide for complete MaxIQ SSD installation and
       setup instructions.
    
  2.3  Power Management Setup (5-Series & 2-Series Controllers Only)

       You must use a compatible combination of Adaptec Storage Manager  
       and controller firmware and driver software to use the power  
       management feature. All software components must support power
       management. You can download the latest controller firmware 
       and drivers from the Adaptec Web site at www.adaptec.com.

  2.4  Linux Setup
  
       Before installing the Linux operating system on a logical drive,  
       Adaptec recommends clearing (removing) old data first. If you
       do not remove old data prior to installation, the OS may
       not boot. As a workaround, use the boot parameter 'aacraid.wwn=2'.     
                     
--------------------------------------------------------------------
3. General Cautions 

   - While an array is being built or cleared, do NOT remove and 
     re-insert any drive in that array. Doing so may cause 
     unpredictable results for any of the controller's arrays.
     
   - Do NOT move drives containing an array from one controller
     to another while the power is on. Doing so could cause
     the loss of the array configuration or data, or both. 
     Instead, power off both affected controllers, move the  
     drives, and then restart.
          
--------------------------------------------------------------------
4. Known Limitations

  4.1  ACU Utility

       o If a non-MaxIQ (generic) SSD is connected to the controller
         on a lower port number than an Adaptec MaxIQ SDD, you cannot
         use the ACU utility to add the MaxIQ SSD to the MaxIQ pool. 
         You must use Adaptec Storage Manager. 
       
         NOTE: Adaptec Q-series controllers do not have this limitation.               
       
       o On some Intel and IBM systems, when you try to run the ACU
         utility, this message appears:
       
         "Not enough free memory to load the utility!
          Press any key to attempt loading the utility forcibly
          OR Wait for the system initialization to be completed 
          [Default]"
       
         This is normal. On Intel systems, wait for the system 
         initialization to be completed. Then the ACU will run. On IBM
         systems, press any key when prompted to load the utility 
         forcibly.
         
       o The ACU erroneously displays deleted logical drives in the
         JBOD list. The logical drive(s) continue to appear in the  
         JBOD list until you delete all of the JBODs.
         
       o With some enclosures, the ACU displays incorrect box/slot 
         information for managed disk drives; for example, 
         Exp/Phy instead of Box/Slot.             

  4.2  AFU Utility

       o When running the AFU in Menu Mode, you can update (flash) only 
         one controller at a time. You must reboot the system before 
         updating the next controller.
       
       o Flashing a 5-series high-port controller (51245, 51645, 52445)
         with down-level firmware and an older version of the AFU crashes
         the system. To recover, you must use a Mode 0 reset using the
         latest firmware version. See the user's guide for details on 
         the Mode 0 method. 

  4.3  Creating an Array from the Adaptec Installation CD

       When you create an array with Adaptec Storage Manager in
       bootable-CD Mode, the maximum size of the array is 2 TB.

  4.4  Using the Controller with an Adaptec S50 JBOD Enclosure

       Temperature warnings from the Adaptec S50 JBOD Enclosure with 
       firmware version T016 are not shown in Adaptec Storage Manager 
       (or on the enclosure). To correct the problem, upgrade to the 
       latest firmware version.

  4.5  UnixWare and OpenServer

       Adding or moving controllers in an existing UnixWare or OpenServer 
       system may cause some device resources to change, which may lead 
       to the operating system being unable to boot. Currently, there 
       is no workaround available in the operating system. Before 
       installing the operating system, make sure all PCI devices are 
       either enabled or installed.        
       
  4.6  OpenServer 6.0

       Arrays may not be displayed correctly, even after you restart
       your computer. 

       To resolve the problem:

       As root, run 'resmgr -r -m vtoc' until it fails. Then, as 
       root, run '/etc/conf/bin/idconfupdate -f'. Then, reboot.
       
  4.7  SuSE Linux Enterprise Server 10 with Service Pack 2
  
       If your boot array is installed on the controller, and the boot
       OS is SLES10 SP2 with driver version 1.1.5-2458, you must add 
       'aacraid.wwn=1' to the kernel boot command line. Alternatively, 
       install the latest aacraid driver.                      
       
  4.8  Hot-adding Disk Drives

       o If you hot-add multiple disks simultaneously to a large 
         configuration (100 disk drives or more), it may take a great 
         deal of time before those disk drives appear in Adaptec 
         Storage Manager.

       o With Intel Backplanes AXX4DRV3GEXP and AXX6DRV3GEXP, if a drive 
         bay is empty at enclosure power on and then a SATA disk drive  
         is hot-added into the empty bay, the controller does not detect
         the new disk drive. To work around this issue, remove and  
         re-insert the SATA disk. 

  4.9  SuperMicro Disk Drive Enclosures

       If the controller does not detect disk drives installed in a 
       SuperMicro M28E2 Mobile Rack, use backplane SAS connectors  
       marked with "SAS In" only.       
       
  4.10 Using the Controller with a Seagate Barracuda 1TB SATA Drive 
       
       To ensure reliability when using Adaptec 2-series and 5-series 
       controllers with a Seagate Barracuda ES.2 1TB SATA Drive 
       (ST31000340NS), Adaptec recommends using Seagate firmware 
       version AN05 or SN06 or higher. 
                
  4.11 Intel SE7525RP2 and SE7320EP2 Motherboards       
    
       The Intel SE7525RP2 and SE7320EP2 motherboards do not support 
       Mode 0 flash. These motherboards use 64-bit PCI addressing.
       The AFU currently supports 32-bit PCI addresses only.

  4.12 Windows Server 2008 64-Bit SCSIport Driver
  
       The Windows Server 2008 64-Bit SCSIport driver is in the process
       of being certified and is not supported in this release. Use 
       the Storport driver instead.
              
  4.13 Boot Drive Failure after OCE/RLM
       
       The system may fail to boot after a boot drive OCE/RLM (online
       capacity expansion/RAID level migration). To correct the problem, 
       verify that the boot drive is still listed as the first logical 
       device in Adaptec Storage Manager (ASM). If not, use the 
       Control-A BIOS utility to reselect the proper boot device.
  
  4.14 Online Capacity Expansion (OCE) Limits
  
       This release supports a maximum of 8 concurrent OCE tasks in 
       the RAID array migration wizard.         
  
  4.15 Power Management under FreeBSD
  
       The FreeBSD driver does not support power management in  
       this release.
       
  4.16 Using RAID10 under FreeBSD
  
       If a RAID10 array fails under FreeBSD the firmware may crash
       causing the system to reboot automatically.
  
  4.17 Power Management with Seagate SAS Drive ST31000640SS
     
       Power Management is not supported by the Seagate ST31000640SS
       SAS drive. (The drive powers down but will not power up without 
       rebooting.)       
                  
  4.18 Linux Cache Synchronization

       With Linux driver 1.1-5-2459 (or higher), you may see an improvement
       in performance if you suppress cache synchronization. For a 
       controller with battery back-up, add 'options aacraid cache=6' to 
       the /etc/modprobe.conf.local file. To completely suppress cache 
       synchronization, add 'options aacraid cache=2'. Then, reboot. 
       Note that the smaller value provides no protection in case of a       
       power outage.
       
  4.19 Listing Devices in VMware ESX 4.0 Console
  
       After deleting an array with ARCCONF, the VMware ESX 4.0 Console
       will hang if you list available devices with 'fdisk -l'. As a 
       work-around, rescan first, then try 'fdisk -l'.
       
  4.20 BIOS Hangs When Booting RAID Controller with Batteryless Backup (ZMCP)

       Possible Cause: After a system shutdown, the ZMM-100DB daughterboard 
       remains active for several minutes. The Super Cap connector may have  
       been improperly removed and/or re-inserted with a charge still present. 

       Solution: Plug the Super Cap connector in when the system is off 
       and, if the yellow activity LED is illuminated on the ZMM-100DB  
       daughterboard attached to RAID Controller, wait for the LED 
       activity indicator to go out. This may take several minutes.  
       The system should then boot normally. 

  4.21 Updating Firmware on Hitachi HUS1514xxVLS300 SAS drives       

       Firmware upgrade on Hitachi HUS151473VLS300 and HUS151436VLS300 
       SAS drives is not supported for packet sizes below 4K (512/1024/2048).

  4.22 Installing Windows OS from Direct-Attached Non-DASD Device
  
       Adaptec RAID controllers do not support Windows OS installation from  
       direct-attached Non-DASD devices ("Direct Access Storage Devices"),    
       such as a tape drive, CD-ROM, or DVD-ROM. Adaptec recommends  
       using a motherboard IDE or SATA DVD-ROM/CD-ROM device to install
       the Windows OS on a RAID array.

  4.23 MaxIQ SSD Cache Performance
            
       The MaxIQ cache contents is lost if the OS is not shut down
       cleanly (for example, by pressing the reboot button or
       pulling the power). When the system is restarted, the cache
       is rebuilt. Until that time, you may see a temporary loss
       in performance.
       
  4.24 Exceeding 2TB LUN Size on VMware ESX Server
  
       Under VMware, if you create a logical drive with greater than 
       2TB of capacity, the OS will only be able to access the remaining 
       storage above 2TB. For instance, with the 3.5TB LUN, only
       1.5TB will be accessible; with a 5TB LUN, only 1TB will
       be accessible (first 2TB+2TB are skipped); and so on.      
       
  4.25 PHY Rate Limitations on Western Digital Hard Drives
    
       To avoid data-phase errors with certain Western Digital hard 
       drives, the PHY rate must be set 1.5Gb/s rather than the 
       maximum rate of 3.0Gb/s. 
       
       o For Western Digital WD2002FYPS and WD20EADS hard drives, the 
         PHY rate is set automatically to 1.5Gb/s.
                     
       You can set the PHY rate to Auto (default), 1.5Gb/s, or 3.0Gb/s. 
       in the Control-A/BIOS utility.       
              
       NOTE: For Adaptec low-port RAID controllers, the device  
             properties in ASM and the BIOS utility will continue    
             to report the maximum PHY rate (3.0Gb/s), not the reduced 
             rate. For high-port controllers, the PHY rate is 
             reported correctly.
             
  4.26 Changing the Stripe Size for Large RAID Arrays
  
       For large RAID arrays, a RAID-level migration may fail with a 
       firmware crash if you reconfigure the array with a different
       stripe size. No data is lost, however. 
       
       Known migrations that result in a FW crash include:
       
       o 16/32/64/128 drive R0- 256/16 to 16/256 stripe change
       o 16/32/64/128 drive R0- 512/16 to 16/512 stripe change
       o 16/32/64/128 drive R0- 1024/16 to 16/1024 stripe change
       o 16/32 drive R5- 16 to 512/1024 stripe change
       o 16/32 drive R5- 512/1024 to 16 stripe change
       o 16/32 drive R6- 1024/16 to 16/1024 stripe change
       
  4.27 Hot-Adding MaxIQ SSDs
       
       If you remove two or more MaxIQ SSDs and then re-insert  
       them at the same time, only one will be recognized as part 
       of the MaxIQ pool. To reconstitute the pool, use Adaptec
       Storage Manager or the BIOS Utility to reconfigure  
       the MaxIQ cache. 

                    .                                    
--------------------------------------------------------------------
(c) 2010 Adaptec by PMC. All Rights Reserved. 

This software contains the valuable trade secrets of PMC-Sierra or its
licensors. The software is protected under international copyright
laws and treaties. This software may only be used in accordance with 
the terms of its accompanying license agreement.

No part of this publication may be reproduced, stored in a retrieval
system, or transmitted in any form or by any means, electronic,
mechanical, photocopying, recording or otherwise, without prior
written consent of:

PMC-Sierra, Inc. 
Mission Towers One 
3975 Freedom Circle 
Santa Clara, CA, 95054