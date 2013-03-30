***************************************************************************** 
                             Windows_Vista_ReadMe.TXT  
***************************************************************************** 

Installation Guide for the LSI Fusion-MPT (TM) Fibre Channel Drivers
                                                 
This file describes the features and installation of the LSI Fusion-MPT 
Fibre Channel device drivers for the Windows Vista operating system. 
It is divided into the following sections:   

Introduction for Windows Vista 
     Features
     LSI Devices Supported
     Description

Installing the Driver(s)
     New System Installation
          DVD-ROM Installation
     Existing System Installation 
     Performance Tuning for Windows Vista 
          Miniport Driver Configuration Options
     WinPE Installation
     Troubleshooting 



1.0 Introduction for Windows Vista  
..................................

Windows Vista is an operating system designed to run on Intel architecture
(x86, 32-bit), Itanium Processor Family (IA64), and Extended-64
(x64, AMD64/EM64T) processors. It provides a graphical user interface 
environment incorporating many high-level features. Refer to the Microsoft 
Windows Vista documentation for details.

An I/O manager handles I/O requests in Windows Vista. To address a peripheral,
the I/O manager goes through the appropriate drivers. Windows Vista provides
class drivers for hard disk, optical, CD-ROM, printer, and scanner peripherals.
Other class drivers, provided by peripheral manufacturers, may be added to
support new devices. Tape device support is built into the operating system
itself and does not require a class driver. 

Microsoft provides the port driver and LSI Corporation provides the miniport
driver for Fibre Channel, called LSI_FC.SYS.  The miniport driver uses the 
Microsoft StorPort port driver (rather than the Microsoft ScsiPort driver 
in earlier versions of Windows).  The StorPort driver has architectural 
enhancements that provide performance improvements on large server systems 
with many storage adapters.  These miniport drivers are designed to take 
advantage of these enhancements for improved performance.


1.1 Features
............ 

The LSI_FC.SYS miniport driver supports these features:

o  Supports 1GB, 2GB and 4GB Fibre Channel transfers (for LSIFC949X,
   LSIFC949E, LSIFC929X, LSIFC919X, LSIFC929 and LSIFC919)
o  Supports PCI, PCI-X, and PCI-Express bus protocols
o  Supports LSI MPT common software interface 
o  Supports multiple host adapters 
o  Supports multiple Logical Unit Numbers (LUNs) 
o  Supports Scatter-Gather 
o  Supports SCSI pass-through functionality 
o  Supports disk array configurations with no LUN 0 
o  Supports disk array configurations with non-contiguous LUNs 
o  Auto request sense 
o  Maximum block size support: 1 Mbyte (32-bit), 2 Mbyte (64-bit)
o  Supports Microsoft WMI HBA API for Fibre Channel devices 
o  Supports End-to-End Data Protection (EEDP) for LSIFC949X, LSIFC949E

1.2 LSI Logic Devices Supported
...............................

The miniport driver names are listed below, along with their supported
devices and associated host adapters:

LSI_FC.SYS - "LSI Fusion-MPT FC Miniport Driver"
o  LSIFC919 (LSI40919O, LSI40919LO, LSI40919H, LSI40919LH)
o  LSIFC929 (LSI44929O, LSI44929LO, LSI44929H, LSI44929LH, 7004G2-LC)
o  LSIFC919X (LSI7102XP)
o  LSIFC929X (LSI7202XP, LSI7402XP)
o  LSIFC949X (LSI7104XP, LSI7204XP, LSI7404XP)
o  LSIFC949E (LSI7104EP, LSI7204EP, LSI7404EP)


1.3 Description
...............

The LSI_FC.SYS driver meets the Microsoft specification for miniport drivers.  
These drivers allow connection of Fibre Channel including disk drives, CD-ROMs,
and tape drives. To support a different Fibre Channel device types, the Windows
Vista architecture requires that a class driver for that type of device be present
(usually supplied by Microsoft, or possibly by the peripheral manufacturer).
No changes to the LSI drivers are required. The driver supports only Windows
Vista and all subsequent Service Packs. 

A Windows application passes SCSI commands directly to the parallel SCSI,
Fibre Channel or SAS Protocol devices by using the SCSI pass-through facility.
This facility allows applications to directly control and access devices by
filling in a data structure and calling into the port or class driver. Refer
to the Microsoft Windows Vista documentation for more details.

2.0 Installing the Driver
.........................


This procedure installs the LSI_FC.SYS driver onto a new or existing Vista
system. 

You will find three different driver package folders, one for each of the 
following system types:

	i386 for Vista 32-bit
	AMD64 for Vista 64-bit
	IA64 for Vista IA64

New system Installation (section 2.1) requires the driver files to be
burned onto a CD-ROM. Installation using boot floppy diskettes is not 
supported by Windows XP 64. 

Existing System Installation (section 2.2) allows the driver files to be
copied onto a hard drive, CD or DVD, or a USB flash drive.

Copy the files listed in this section to the root directory of the
installation media as shown below.  Label the media "Windows Vista Drivers". 
You will use this media during the installation process.
       
        \lsi_fc.inf
        \lsi_fc.sys
        \fvlhx86.cat (for x86) or
        \fvlhia64.cat (for IA64) or
        \fvlhx64.cat (for x64)        
       
Note: Windows Vista drivers must be either Release signed (by LSI) or WHQL
      logo signed (by Microsoft Windows Hardware Quality Labs) to be installed
      on Vista.  Any modifications to any of the above files will invalidate
      the digital signature of the package and Vista will not install the
      driver.


2.1 New System Installation
........................... 

This procedure installs the LSI_FC.SYS driver onto a Windows Vista system. Use
this procedure when installing Windows Vista onto an unused drive. Windows
Vista automatically adds the driver to the registry and copies the driver to
the driver storage area.

Note: Windows Vista contains a bundled LSI_FC driver, which supports a fresh
      installation of Vista.  When a newer driver is installed, the fresh 
      installation can be done with the bundled driver and the driver can 
      be upgraded after installation has completed as described in Section 
      2.2.  Or, the newer driver can be used for fresh installation as 
      described in the following section.

1. Start the Windows Vista installation by booting from the Windows Vista
   DVD-ROM:

   The system BIOS must support booting from a DVD-ROM. BIOS settings may need
   to be changed to allow DVD-ROM booting.
   
2. Process with the installation of Windows Vista. When the screen displays
   "Where do you want to install Windows?", click on the Load Driver icon.
   
3. Be sure the media with the LSI_FC driver install package for the system
   processor architecture is inserted in the system.  Click the Browse button,
   browse to the location of the driver package, then click OK.
   
4. The LSI adapter driver name will be displayed, click Next.

    Note: When using a Release Signed driver, a Windows Secutiry dialog box may
          appear, indicating that the publisher of this software is LSI
	  Corporation. Click the Install button to continue installation of the
	  driver.
            
          A second Windows Security dialog box may appear, indicating that a
          LSI system device is being installed.  This is to install
          drivers for LSI storage enclosure processors.  Click the Install
          button to continue installation of the driver.
   
5. Follow the Microsoft Windows Vista installation procedure at this point.


2.2 Existing System Installation
................................

This procedure installs or upgrades the LSI_FC.SYS drivers onto an existing
Windows Vista system.

NOTE: When a LSI Fibre Channel adapter is added to an existing
	  system installation, the new adapter is automatically detected at the
	  next reboot. When the Update Driver Software Wizard appears at boot,
	  continue at step 8 below.

1. Boot Windows Vista and logon as a user that has Administrator privileges.

2. Click on the Start button, then right-click on the Computer entry in
   the menu.

3. Click on the Properties selection.

4. In the Tasks column on the left side of the Screen, click Device Manager.

   Note: A User Account Control dialog box may be displayed, asking for
         permission to continue.  Click Continue.
         
5. Click the "+" to the left of the Storage Controllers line.  Find the adapter
   desired for the driver upgrade and double-click the entry.  Click on the
   Driver tab.

6. Information on the currently installed driver is displayed, and additional
   driver details can be viewed by clicking the "Driver Details" button.

7. Click on the "Update Driver" button to update the existing driver.  The
   Update Driver Software wizard begins.
   
8. Click on the "Browse my computer for driver software" selection.

9. Click on the "Let me pick..." selection at the bottom of the window.

10. Click on the "Have Disk" button and type the path to the driver, or click
    on the Browse button. Select the location for the driver package which
    matches the processor architecture of the system (x86, IA64, or x64). After
    the path to the driver has been established, click the OK button.

11. Select the driver from the list and click on the Next button.

    Note: When using a Release Signed driver, a Windows Secutiry dialog box may
          appear, indicating that the publisher of this software is LSI
		  Corporation. Click the Install button to continue installation of the
		  driver.
            
          A second Windows Security dialog box may appear, indicating that a
          LSI system device is being installed.  This is to install drivers for
		  LSI storage enclosure processors.  Click the Install button to
		  continue installation of the driver.
          
          
12. The system will load the driver from the Windows Vista driver package
    media. A message box may display indicating that the target (existing)
    driver is newer than the source (upgrade) driver.

14. Click No to cancel the driver upgrade at this point.

      or

    Click Yes to continue the installation.

    The system copies the driver to the system disk. For any adapter other
    than the boot adapter, the updated driver will become active immediately.
    For the boot adapter, a message bdisplays indicating that you must reboot
    your system for the new driver to take effect.

15. Click on the Close button to complete the driver upgrade.


2.3 Performance Tuning for Windows Vista
........................................

The Windows Vista storport driver has been optimized for performance in
I/O intensive and throughput intensive environments. However, parameters
have been provided to fine tune performance for specific applications. 

2.3.1 Maximum Number of Concurrent I/Os
.......................................    
  
The LSI_FC driver guarantees a maximum queue depth of 64, meaning that
a maximum of 64 concurrent I/Os per attached target device are supported. 
This is the recommended high limit, and should be sufficient even for 
high performance Raid devices.  The value is configurable however, using 
the following line in the lsi_fc.inf file:

[LSI_FC_AddReg]
HKLM,SYSTEM\CurrentControlSet\Services\Lsi_fc\Parameters\Device,MaximumTargetQueueDepth,0x00010001,0x40

The 0x40 value at the end of the line represents the default queue depth
of 64 (0x40 hex).

The system must be rebooted for a new registry setting to be effective.

2.3.2 Maximum I/O Size
......................    
  
The LSI_FC storport driver allows a maximum I/O size of 1MB in 32-bit 
environments and 2MB in 64-bit environments. This is the recommended limit,
and should be sufficient for most applications. The value is not configurable. 


............................................................................
2.4 WinPE Installation

WinPE is provided to system OEM's to create a Pre-install Environment image.
To use the LSI_FC.SYS driver with the Windows Vista based WinPE, perform the 
steps listed below.  

1. Create an lsi_fc folder in the winpe_image directory under i386\system32.
   For example: mkdir winpe_image\i386\system32\lsi_fc
 
2. Copy the lsi_fc driver package to the winpe_image\i386\system32\lsi_fc
   folder.

3. Edit the winpe_image\i386\System32\Winpeoem.sif to remove the semicolons
   from the [OemDriverParams] section and add the name of the lsi_fc
   directory to the OemDriverDirs entry. For example:

   [OemDriverParams]
   OemDriverRoot = ""
   OemDriverDirs = lsi_fc
 
4. You can then use oscdimg to create a bootable .iso image, or follow the
   WinPE User’s Guide to create a bootable USB flash device.

............................................................................
3.0 Troubleshooting 

The LSI_FC.SYS driver will log error messages to the system error log. 
For these errors, the system errorlog EventID will be 11, and the specific 
error code values will be displayed at offset 0x10. Data should be displayed 
in words.
