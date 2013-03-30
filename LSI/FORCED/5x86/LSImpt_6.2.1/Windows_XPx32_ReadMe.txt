***************************************************************************** 
                         Windows_XPx32_ReadMe.TXT  
***************************************************************************** 

Installation Guide for the LSI Logic Fusion-MPT (TM) Windows XP 32-bit Driver
                                                 
This file describes the features and use of the LSI Logic Fusion-MPT
SCSI/Fibre Channel device drivers for the Windows XP 32-bit operating system
environment. It is divided into the following sections:   

Introduction for Windows XP 32
     Features
     LSI Logic Devices Supported

Installing the Driver(s)
     New System Installation
          CD-ROM Installation
     Existing System Installation 
     Performance Tuning for Windows XP 
          Large Block Size Support 
          Maximum Number of Concurrent I/Os 
     Hibernation Support
     Troubleshooting 



1.0 Introduction for Windows XP 32
..................................  


Windows XP 32 is an operating system designed to run on Intel-architecture
(32-bit) processors using current technology. It provides a graphical user 
interface environment incorporating many high-level features. Refer to the 
Microsoft Windows XP documentation for details.

An I/O manager handles I/O requests in Windows XP. To address a peripheral, 
the I/O manager goes through the appropriate drivers. Windows XP
provides class drivers for hard disk, optical, CD-ROM, printer, and scanner
peripherals. Other class drivers, provided by peripheral manufacturers, may be
added to support new devices. Tape device support is built into the operating 
system itself and does not require a class driver. 

Microsoft provides the port driver and LSI Logic provides the miniport driver,
which is called SYMMPI.SYS.  This driver completes the path to the LSI Logic 
controller or processor with an optional Fibre Channel BIOS.


1.1 Features
............ 

The Windows XP driver supports these features:

o  PCI, PCI-X and PCIe bus protocols 
o  1 Gb, 2Gb link rates (for LSIFC929 and LSI929XL)
o  4 Gb link rates (for LSI949X and LSI949e)
o  LSI Logic Fusion-MPT common software interface 
o  Multiple host adapters 
o  Multiple Logical Unit Numbers (LUNs) 
o  Scatter-Gather 
o  SCSI pass-through functionality 
o  Disk array configurations with no LUN 0 
o  Disk array configurations with non-contiguous LUNs 
o  Auto request sense 
o  Maximum block size support: 1 Mbyte (32-bit), 2 Mbyte (64-bit)


1.2 LSI Logic Devices Supported
............................... 

The Windows XP driver supports the following devices and host adapters:

o  LSIFC919 (LSI40919O, LSI40919LO, LSI40919H, LSI40919LH)
o  LSIFC929 (LSI44929O, LSI44929LO, LSI44929H, LSI44929LH, 7004G2-LC)
o  LSIFC919X (LSI7102XP)
o  LSIFC929X (LSI7202XP, LSI7402XP)
o  LSIFC949X (LSI7104XP, LSI7204XP, LSI7404XP)
o  LSIFC949E (LSI7104EP, LSI7204EP, LSI7404EP)


2.0 Installing the Driver
.........................  


This procedure installs the SYMMPI.SYS driver onto a new or existing
Windows XP system. 

New system Installation (section 2.1) requires the driver files to be
burned onto a CD-ROM. Installation using boot floppy diskettes is not 
supported by Windows XP 64. 

Existing System Installation (section 2.2) allows the driver files to be
copied onto a hard drive, CD or DVD, or a USB flash drive.

Copy the files listed in this section to the root directory of the
installation media as shown below.  Create subdirectories as specified. 
You will use this media during the installation process.


        \txtsetup.oem
        \symmpi.tag
        \MPI100IO.REG
        \MPI_256K.REG
        \MPIDEFIO.REG
        \MPIDFBLK.REG

        \32_bit\lsipseud.inf
        \32_bit\mpixp32.cat
        \32_bit\symmpi.inf
        \32_bit\symmpi.sys
        \32_bit\symmpi.pdb



2.1 New System Installation
........................... 

This procedure installs the SYMMPI.SYS driver onto a Windows XP system.
Use this procedure when installing Windows XP onto an unused drive.
Windows XP automatically adds the driver to the registry and copies the
driver to the appropriate directory.


1. Start the Windows XP installation by booting from the Windows XP CD-ROM:

   The system BIOS must support booting from a CD-ROM. BIOS settings may need
   to be changed to allow CD-ROM booting.

2. Press the F6 key to install the SYMMPI.SYS driver when the screen displays
   "Windows Setup".

   This must be done or else the new driver will not be recognized.

   Note: Be sure to press the F6 key as any driver loaded later in the
         installation process is not recognized by Windows XP Setup. 
         If F6 is not pressed, all devices controlled by the drivers are
         not available during Windows XP setup.

3. Choose S to specify an additional device when the screen displays "Setup
   was unable to load support for the mass storage device you specified...". 

   NOTE: If this screen is not displayed as the first user input, then 
         pressing the F6 key was not seen by the setup program. Reboot the 
         system and try again.

   The system prompts for the manufacturer-supplied hardware support disk.

4. Insert the driver CD-ROM containing the Windows XP drivers and press Enter.
    
5. The screen will display a list of two drivers to select from:

       "LSI Logic PCI SCSI/FC MPI Driver (XP 32-bit)"

   Press Enter to proceed.

   Return to the Windows XP Setup screen.

6. Press Enter to proceed.

   The message about setup loading files appears.

7. Follow the Microsoft Windows XP installation procedure at this point.


2.2 Existing System Installation
................................

This procedure installs or upgrades the drivers onto an existing Windows XP system.

NOTE: When a LSI Logic Fibre Channel adapter is added to an existing
      system installation, the new adapter is automatically detected at the
      next reboot. When the Device Driver Wizard appears at boot, click on the
      Next button and continue at step 8 below.

1. Boot Windows XP and logon as a user that has Administrator privileges.

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
    on the Browse button.  After the path to the driver has been established, 
    click the OK button.

11. Select the driver from the list and click on the Next button.

12. Click on the Next button again to start the driver update.

    In some cases, a message will display saying that this driver has not
    passed logo testing. This message informs you that a nonsigned driver is
    being installed.

13. Click STOP Installation to cancel the installation if a nonsigned driver
    is not desired.

      or

    Click Continue Anyway to continue the installation.

    The system will load the driver from the Windows XP driver CD-ROM.
    A message box may display indicating that the target (existing) driver is
    newer than the source (upgrade) driver.

14. Click No to cancel the driver upgrade at this point.

      or

    Click Yes to continue the installation.

    The system copies the driver to the system disk. For any adapter other
    than the boot adapter, the updated driver will become active immediately.
    For the boot adapter, a message box displays indicating that you must
    reboot your system for the new driver to take effect.

15. Click on the Finish button to complete the driver upgrade.


2.3 Performance Tuning for Windows XP
.....................................

Windows XP has registry entries that can be used to tune the performance 
of SCSI I/O for certain configurations. The tunable parameters are large 
transfer block size support and a guaranteed number of concurrent I/Os for a 
particular SCSI bus.


2.3.1 Large Block Size Support 
..............................

The 32-bit drivers can support up to a 1 Mbyte transfer size in 
Windows XP; however, the default Windows XP transfer size is 64 Kbytes. To 
enable better performance, the driver installation process adds a registry 
entry to enable the maximum 1 Mbyte transfer size.  Also, the mpi_256K.reg 
file can be used to set or enable a 256 Kbytes maximum, but it can be 
edited to set other desired maximum transfer sizes. There are two methods to 
add this registry setting.

1. Locate the mpi_256K.reg data file (supplied with the driver files) using
   Windows Explorer and double-click on the file.
 
   -OR-

2. Type at the command prompt:

   regedit mpi_256K.reg

This inserts an entry in the registry to enable 256 Kbytes block size support. 

Editing the mpi_256K.reg can set any maximum block size between 64 Kbytes and
1 Mbyte. The formula to calculate the proper value for MaximumSGList is:

     MaximumSGList = ((Maximum Block Size)/4 Kbytes) +1

For 256 Kbytes: 256 Kbytes/4 Kbytes = 64. Add 1 for 65 (decimal) or 
0x41 (hexadecimal). The maximum value allowed for MaximumSGLIst is 255 or 
0xFF. For the particular value of 0xFF, the internal value passed to Windows 
is increased to 0x101, allowing support for a full 1 Mbyte transfer. Be sure 
to read the information in the mpi_256K.reg data file before editing it.

The system must be rebooted for the new registry setting to be effective.

To reset the maximum block size to the operating system default of 64 Kbytes,
follow the instructions above, except use mpidfblk.reg as the data file.

NOTE: For 64-bit systems, the OS page size is 8 Kbytes instead of 4 Kbytes.  
      Therefore, the maximum transfer size is 2 Mbytes, the default driver 
      installation enables support for 512 Kbytes transfer size, and the 
      formula becomes:
      
          MaximumSGList = ((Maximum Block Size)/8 Kbytes) +1

............................................................................
2.3.2 Maximum Number of Concurrent I/Os (Guaranteed)   
  
Windows XP guarantees a maximum of 32 concurrent I/Os active on a 
particular SCSI bus. However, due to the method of memory allocation, the 
actual limit of concurrent I/Os can vary greatly between various drivers or 
versions of drivers. This can have a huge impact on performance benchmarking 
between different driver versions or adapter vendors. In effect, one adapter 
may actually be able to have 70 or 80 I/Os outstanding, while another adapter 
could only have 32. This can also affect systems with high performance storage 
subsystems, such as disk arrays.

In order to enable better performance, the driver installation process adds a
registry entry to support 255 concurrent I/Os. If a different maximum value is
desired, the file mpi100io.reg can be used to add a registry entry to guarantee
the desired number of concurrent I/Os.

There are two methods to add this registry setting. One is to locate the
mpi100io.reg data file (supplied with the driver files) using Windows Explorer
and double click on the file. The other method is to type at the command
prompt:

     regedit mpi100io.reg

This inserts an entry in the registry to guarantee a maximum of 100 
concurrent I/Os per adapter.

If a maximum other than 100 is desired, the mpi100io.reg can be edited;
however, setting this value to a high number uses increasing amounts of
non-paged pool memory, a critical NT resource. High values for this setting
can degrade system performance. Be sure to read the information in the
mpi100io.reg data file before editing it.

The system must be rebooted for the new registry setting to be effective.

To reset the guaranteed number of concurrent I/Os to the operating system
default of 32, follow the instructions above, except use mpidefio.reg as the
data file.  



............................................................................
3.0 Hibernation Support

The LSI Fusion-MPT storage adapters and the SYMMPI.SYS driver are high
performance storage solutions.  This performance level requires a level of
resources above that of typical storage adapters.  This resource level is
supported adequately by Windows XP during normal operations.  However, due to
limitations imposed by Windows XP, when attempting to Hibernate the system may
fail to Hibernate and display the following error message:

    Windows - System Error
    Insufficient system resources exist to complete the API.

To allow Windows XP to Hibernate successfully, all critical Windows Update
patches should be applied to the system.  These patches can be downloaded at:

http://windowsupdate.microsoft.com

............................................................................
4.0 Troubleshooting 

The SYMMPI.SYS driver will log error messages to the system error log. For
these errors, the system errorlog EventID will be 11, and the specific error
code values will be displayed at offset 0x10. Data should be displayed in
words.
