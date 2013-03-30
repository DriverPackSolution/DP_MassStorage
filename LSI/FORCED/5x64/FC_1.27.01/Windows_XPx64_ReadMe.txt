***************************************************************************** 
                             Windows_XPx64_ReadMe.TXT  
***************************************************************************** 

Installation Guide for the LSI Logic Fusion-MPT (TM) Windows XP 64-bit Driver
                                                 
This file describes the features and use of the LSI Logic Fusion-MPT
SCSI/Fibre Channel device drivers for the Windows XP 64-bit operating system
environment. It is divided into the following sections:   

Introduction for Windows XP 64
     Features
     LSI Devices Supported

Installing the Driver(s)
     New System Installation
     Existing System Installation 
     Performance Tuning for Windows XP x64
     Troubleshooting 


1.0 Introduction for Windows XP 64
...................................


Windows XP 64 is an operating system designed to run on Extended-64 (x64)
(AMD64/EM64T) processors using current technology. It provides a graphical
user interface environment incorporating many high-level features. Refer to the
Microsoft Windows XP x64 documentation for details.

An I/O manager handles I/O requests in Windows XP x64. To address a
peripheral, the I/O manager goes through the appropriate drivers. Windows
XP provides class drivers for hard disk, optical, CD-ROM, printer,
and scanner peripherals. Other class drivers, provided by peripheral
manufacturers, may be added to support new devices. Tape device support is
built into the operating system itself and does not require a class driver. 

Microsoft provides the port driver and LSI Corporation provides the storport
drivers, which are called LSI_FC.SYS.  These drivers complete the path to 
the LSI controller or processor with an optional Fibre Channel BIOS.

The driver uses the Microsoft StorPort port driver (rather than the Microsoft 
ScsiPort driver in earlier versions of Windows).  The StorPort driver has 
architectural enhancements that provide performance improvements on large 
server systems with many storage adapters.  These miniport drivers are
designed to take advantage of these enhancements for improved performance.


1.1 Features
............ 

The LSI_FC.SYS driver supports these features:

o  PCI, PCI-X, and PCI-Express bus protocols
o  1 Gb, 2Gb link rates (for LSIFC929 and LSI929XL)
o  4 Gb link rates (for LSI949X and LSI949e)
o  LSI MPT common software interface 
o  Multiple host adapters 
o  Multiple Logical Unit Numbers (LUNs) 
o  Scatter-Gather 
o  SCSI pass-through functionality 
o  Disk array configurations with no LUN 0 
o  Disk array configurations with non-contiguous LUNs 
o  Auto request sense 
o  Maximum block size support: 1 Mbyte (32-bit), 2 Mbyte (64-bit)
o  End-to-EnSupports Microsoft WMI HBA API for Fibre Channel devices 


1.2 LSI Devices Supported 
.........................

The Windows XP driver supports the following devices and host adapters:

o  LSIFC919 (LSI40919O, LSI40919LO, LSI40919H, LSI40919LH)
o  LSIFC929 (LSI44929O, LSI44929LO, LSI44929H, LSI44929LH, 7004G2-LC)
o  LSIFC919X (LSI7102XP)
o  LSIFC929X (LSI7202XP, LSI7402XP)
o  LSIFC949X (LSI7104XP, LSI7204XP, LSI7404XP)
o  LSIFC949E (LSI7104EP, LSI7204EP, LSI7404EP)



2.0 Installing the Driver
.........................


This procedure installs the LSI_FC.SYS driver onto a new or existing 
Windows XP 64 system.

New system Installation (section 2.1) requires the driver files to be
burned onto a CD-ROM. Installation using boot floppy diskettes is not 
supported by Windows XP 64. 

Existing System Installation (section 2.2) allows the driver files to be
copied onto a hard drive, CD or DVD, or a USB flash drive.

Copy the files listed in this section to the root directory of the
installation media as shown below.  Label the media "Windows XP 64 Driver". 
You will use this media during the installation process.

        
        \txtsetup.oem
        \lsi_fc.tag
        \fxpam64.cat
        \lsi_fc.inf
        \lsi_fc.sys
        
               

2.1 New System Installation
........................... 

This procedure installs the LSI_FC.SYS driver onto a Windows XP 64 system. 
Use this procedure when installing Windows XP 64 onto an unused drive. 
Windows XP 64 automatically adds the driver to the registry and copies the 
driver to the appropriate directory.

Note: Windows XP 64 contains a SYMMPI.SYS driver that supports the
      U320, 919 and 929 devices.  When performing a fresh installation with a
      device that is supported by the bundled SYMMPI.SYS driver, loading
      of the LSI_FC.SYS driver using the F6 key will have no effect and
      the SYMMPI.SYS driver will be used.  To use the LSI_FC.SYS driver,
      upgrade the driver after installation has completed as described
      in Section 2.2.

1. Start the Windows XP 64 installation by booting from the Windows XP 64 
   CD-ROM:

   The system BIOS must support booting from a CD-ROM. BIOS settings may need
   to be changed to allow CD-ROM booting.

2. Press the F6 key to install the LSI_FC.SYS driver when the screen displays
   "Windows Setup".

   This must be done or else the new driver will not be recognized.

   Note: Be sure to press the F6 key as any driver loaded later in the
         installation process is not recognized by Windows XP 64 Setup.
         If F6 is not pressed, all devices controlled by the drivers are
         not available during Windows XP 64 setup.

3. Choose S to specify an additional device when the screen displays "Setup
   could not determine the type of one or more mass storage devices...". 

   NOTE: If this screen is not displayed as the first user input, then 
         pressing the F6 key was not seen by the setup program. Reboot the 
         system and try again.

   The system prompts for the manufacturer-supplied hardware support disk.

4. Insert the CD-ROM containing the Windows XP 64 drivers and press Enter.
    
5. The screen will display the driver to be installed:

       "LSI Fusion-MPT FC Driver (XP x64)"
       
   Press Enter to proceed.

   Return to the Windows XP 64 Setup screen.

6. Press Enter to proceed.

   The message about setup loading files appears.

7. Follow the Microsoft Windows XP 64 installation procedure at this point.


2.2 Existing System Installation
................................

This procedure installs or upgrades the LSI_FC.SYS drivers onto an existing
Windows XP 64 system.

NOTE: When a LSI Fibre Channel adapter is added to an existing system installation,
          the new adapter is automatically detected at the next reboot. When the 
          Device Driver Wizard appears at boot, click on the Next button and 
          continue at step 8 below.

1. Boot Windows XP 64 and logon as a user that has Administrator
   privileges.

2. Click on the Start button, then right-click on the My Computer entry in
   the menu.

3. Click on the Properties selection.

4. Click on the Hardware tab, and then the Device Manager button.

5. Click the "+" to the left of the SCSI and RAID controllers line.  Find the
   adapter desired for the driver upgrade and double-click the entry.  Click
   on the Driver tab.

6. Information on the currently installed driver is displayed, and additional
   driver details can be viewed by clicking the "Driver Details" button.

7. Click on the "Update Driver" button to update the existing driver.  The
   Hardware Update Wizard begins.
   
8. Click on the "Install from a list or specific location..." button to select
   it, then click on the Next button.

9. Click on the "Don't search, I will choose the driver to install." button
   to select it, then click on the Next button.

10. Click on the "Have Disk" button and type the path to the driver, or click
    on the Browse button.  Click the OK button.

11. Select the driver from the list and click on the Next button.

12. Click on the Next button again to start the driver update.

    In some cases, a message will display saying that this driver has not
    passed logo testing. This message informs you that a nonsigned driver is
    being installed.

13. Click STOP Installation to cancel the installation if a nonsigned driver
    is not desired.

      or

    Click Continue Anyway to continue the installation.

    The system will load the driver from the Windows XP 64 driver
    diskette. A message box may display indicating that the target (existing)
    driver is newer than the source (upgrade) driver.

14. Click No to cancel the driver upgrade at this point.

      or

    Click Yes to continue the installation.

    The system copies the driver to the system disk. For any adapter other
    than the boot adapter, the updated driver will become active immediately.
    For the boot adapter, a message box displays indicating that you must
    reboot your system for the new driver to take effect.

15. Click on the Finish button to complete the driver upgrade.


2.3 Performance Tuning for Windows XP 64
.........................................

The Windows XP 64 storport driver has been optimized for performance in
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
  
The LSI_FC storport driver allows a maximum I/O size of 2MB in 64-bit environments. 
This is the recommended limit, and should be sufficient for most applications. 
The value is not configurable. 


3.0 Troubleshooting 
...................

The LSI_FC.SYS driver will log error messages to the system error log. For 
these errors, the system errorlog EventID will be 11, and the specific error 
code values will be displayed at offset 0x10. Data should be displayed in words.
