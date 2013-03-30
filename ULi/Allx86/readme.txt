======================================================================
     ALi ATA/RAID Controller and SATA/RAID controller driver

                  Copyright 2003-2004 ALi Corporation. 
                       All Rights Reserved
======================================================================

------------
INTRODUCTION
------------
This driver supports ALi ATA/RAID Controller and SATA/RAID controller.


-------------------------
CONTENTS OF THIS DOCUMENT
-------------------------
1. Installation Instructions
2. Uninstallation Instructions
3. Driver File List
4. Driver Change List


----------------------------
1. Installation Instructions
----------------------------
  After the adapter is installed and recognized by computer, user can 
  start the installation of driver.


----------------------------------------------------------------------
* Windows 98/ME
Installation
  After Windows 98/ME is start-up, Windows system will automatically
  find the newly installed adapter and prompt user to install its 
  driver. Follow these steps to install the driver:

  A) With installation setup program:
   1. When the Found New Hardware Wizard windows appear, click Next
      button all the following windows. Then the driver will not be 
      installed. 
   2. Double click setup.exe;
   3. Confirm the following dialogue windows, and restart the computer
      when system prompt user to restart.

  B) Manual installation:
   1. After the Add New Hardware Wizard window appears(PCI Mass Storage 
      Controller), press Next button until the window with Specify a location 
      item appears;
   2. Insert the driver diskette, then select the Specify a location
      item and type in the driver loaction: A:\Win98_ME, then click on
      Next button to continue;
   3. Confirm the following dialogue windows, and restart the computer
      when system prompt user to restart;
   4. After rebooting, Windows will automatically find ALi SATA/RAID 
      Controller and install its drivers.
   5. Repeat step 1 to install ALi ATA/RAID Controller.

----------------------------------------------------------------------
* Windows NT4.0
Install driver under existing Windows NT4.0

  A) With installation setup program:
   1. Double click setup.exe;
   2. Confirm the following dialogue windows, and restart the computer
      when system prompt user to restart.

  B) Manual installation:
   1. Click Start-->Settings-->Control Panel, then double-click on the 
      SCSI Adapters icon;
   2. Within the follow-up window, select Driver item, then click on 
      Add button;
   3. Within the follow-up window, click on Have Disk...button, the 
      "Install From Disk" window will appear.
   4. Insert the driver diskette, and type in the path of driver 
      location: A:\Win_NT in the above window, then click OK;
   5. Within the follow-up window, select ALi SATA/RAID Controller
      item, then click OK;
   6. Confirm the follow-up system prompts to finish the driver
      installation; 
   7. Repeat step 1, but select ALi ATA/RAID Controller at step 5;
      If both controllers are installed, go to next step;
   8. When installation finshed, restart the computer.

Install driver during WindowsNT4.0 installation
   0. After you unpack driver, please copy files and subdirectory under 
      SATA50XX to a floppy diskette (called driver diskette).
      Therefore, in root directory of floppy diskette you will see:
      (1) Files "disk1" and "txtsetup.oem",
      (2) Directory "win98_me", "win_nt", "win_2000", "win_xp" and related
          driver files in each directory.
      (please refer to "Driver File List" as below)
   1. Press F6 key when the installation program prompt "Setup is 
      inspecting your computer's hardware configuration";
   2. The installation will continue. Later, installation program will
      prompt user to press S key to specify other devices, then press
      S key;
   3. Within the follow-up device type window, select Other, then 
      press ENTER to confirm;
   4. Installation program will prompt user to insert the driver 
      diskette and then press ENTER to confirm;
   5. Within the follow-up window, select ALi SATA/RAID Controller,
      then press ENTER to confirm;
   6. The follow-up window will list out the devices to be installed, 
      in which selected ALi controller(s) will be included;
   7. Repeat step 2, but select ALi ATA/RAID Controller at step 5;
      If both controllers are installed, go to next step;
   8. If users want to install other devices, please operate at this time. 
      If all devices have been installed, go to next step
   9. Press ENTER to confirm the devices to be installed and continue 
      the installation of Windows NT4.0. 

----------------------------------------------------------------------
* Windows 2000
Install driver under existing Windows 2000
  After Windows 2000 is start-up, Windows system will automatically
  find the newly installed adapter and prompt user to install its
  driver. Please follow these steps to install the driver:

  A) With installation setup program:
   1. When the Found New Hardware Wizard windows appear, click Cancel
      button to end the Wizard.
   2. Double click setup.exe;
   3. Confirm the following dialogue windows, and restart the computer
      when system prompt user to restart.

  B) Manual installation:
   1. When the Found New Hardware Wizard windows appear(Mass Storage 
      Controller), click Next button to continue, in the follow-up window, 
      please select Display a list... and then click Next to continue;
   2. In the follow-up window, select SCSI and RAID Controllers and 
      then click Next to continue;
   3. In the follow-up window, click Have Disk..., then insert the 
      driver diskette and type in the driver location: A:\Win_2000,
      then click OK to continue;
   4. In the follow-up window, select ALi SATA/RAID Controller, 
      then click Next to continue;
   5. Confirm the followup windows and click the Finish button to
      continue;
   6. Please 'confirm' the Digital Signature Not Found window when it
      appears, when finshed, please restart the computer;
   7. Repeat step 1, but select ALi ATA/RAID Controller at step 4.

Install driver during Windows 2000 installation
   0. After you unpack driver, please copy files under subdirectory
      SATA50XX to the root directory of floppy diskette (called driver
      diskette).
      Therefore, in root directory of floppy diskette you will see:
      (1) Files "disk1" and "txtsetup.oem",
      (2) Directory "win98_me", "win_nt", "win_2000", "win_xp" and related
          driver files in each directory.
      (please refer to "Driver File List" as below)
   1. Booting from CD-ROM, when the Windows 2000 Setup blue screen
      appear and prompt user to Press F6 if you need to install third
      party SCSI or RAID driver, please press F6 key:
   2. The setup program will continue, later when the setup program
      prompts user to specify additional adapters, please press S
      Key.
   3. Then the setup program prompt user to insert the driver
      diskette. Please insert the driver diskette, then press ENTER 
      to continue;
   4. The follow-up window will list out the installation choices, 
      please select ALi SATA/RAID Controller for Windows 2000 and 
      press ENTER to continue;
   5. The Follow-up window will list out the devices to be installed,
      in which selected ALi controller should be included;
   6. Repeat step 2, but select ALi ATA/RAID Controller at step 5;
      If both controllers are installed, go to next step;
   7  If users want to install other devices, please operate at this time. 
      If all devices have been successfully installed, go to next step.
   8. Press ENTER to continue Windows 2000 setup.  


----------------------------------------------------------------------
* Windows XP / Windows Server 2003
Install driver under existing Windows XP
  After Windows XP is start-up, Windows system will automatically
  find the newly installed adapter and prompt user to install its
  driver. Please follow these steps to install the driver:

  A) With installation setup program:
   1. When the Found New Hardware Wizard windows appear, click Cancel
      button to end the Wizard.
   2. Double click setup.exe;
   3. Confirm the following dialogue windows, and restart the computer
      when system prompts user to restart.

  B) Manual installation:
   1. When the Found New Hardware Wizard windows appear(Mass Storage 
      Controller), select Install from a list or specify location(Advanced) 
      and click Next to continue;
   2. In the follow-up window, please select "Don't search, I will 
      choose the driver to install", then click Next to continue;
   3. In the follow-up window, please select SCSI and RAID 
      controllers, and then click Next to continue;
   3. In the follow-up window, click Have Disk..., then insert the 
      driver diskette and type in the driver location: A:\Win_XP,
      then click OK to continue;
   4. In the follow-up window, select ALi SATA/RAID Controller,
      then click Next to continue;
   5. Confirm the followup windows and click the Finish button to
      continue;
   6. Please "confirm" the Digital Signature Not Found window when it
      appears, when finshed, please restart the computer;
   7. Repeat step 1, but select ALi ATA/RAID Controller at step 4.   

Install driver during Windows XP installation
   0. After you unpack driver, please copy files under subdirectory
      SATA50XX to the root directory of floppy diskette (called driver
      diskette).
      Therefore, in root directory of floppy diskette you will see:
      (1) Files "disk1" and "txtsetup.oem",
      (2) Directory "win98_me", "win_nt", "win_2000", "win_xp" and related
          driver files in each directory.
      (please refer to "Driver File List" as below)
   1. Booting from CD-ROM, when the Windows XP Setup blue screen
      appear and prompt user to Press F6 if you need to install third
      party SCSI or RAID driver, please press F6 key:
   2. The setup program will continue, later when the setup program
      prompts user to specify additional adapters, please press S
      Key.
   3. Then the setup program will prompt user to insert the driver
      diskette. Please insert the driver diskette, then press ENTER 
      to continue;
   4. The follow-up window will list out the installation choices, 
      please select ALi ALi SATA/RAID Controller for Windows XP 
      and press ENTER to continue;
   5. The follow-up window will list out the devices to be installed,
      in which selected ALi controller(s) should be included;
   6. Repeat step 2, but select ALi ATA/RAID Controller at step 5;
      If both controllers are installed, go to next step;
   7  If users want to install other devices, please operate at this time. 
      If all devices have been successfully installed, please go to next 
      step.
   8. Press ENTER to continue Windows XP setup.


------------------------------
2. Uninstallation Instructions
------------------------------
* Uninstall from Add/Remove Programs
(This method is recommended if driver is previously installed by Setup program.)
1. Start Add/Remove Programs from Control Panel.
2. Select "ALi RAID Driver" item.
3. Click on "Remove" button.

* Uninstall from Device Manager
1. Start Device Manager from Control Panel's System applet.
2. Right click on "ALi ATA/RAID Controller" or "ALi SATA/RAID Controller" item, 
   then select "Remove" (or "Uninstall") item from the popup menu.


-------------------
3. Driver File List
-------------------
    SATA50XX                    Driver Folder
     |- win98_me                Windows 98/ME driver
     |  |_ m5228.inf
     |  |_ m5228.mpd
     |  |_ ulipower.vxd
     |  |_ m5281.inf
     |  \_ m5281.mpd
     |- win_nt                  Windows NT 4.0 driver
     |  |_ m5228.inf
     |  |_ m5228.sys
     |  |_ m5281.inf
     |  \_ m5281.sys
     |- win_2000                Windows 2000 driver
     |  |_ m5228.inf
     |  |_ m5228.sys
     |  |_ m5281.inf
     |  \_ m5281.sys
     |- win_xp                  Windows XP/Server 2003 driver
     |  |_ m5228.inf
     |  |_ m5228.sys
     |  |_ m5281.inf
     |  \_ m5281.sys
     |- WINXPA64                Windows XP/Server 2003 x64 driver
     |  |_ m5228.inf
     |  |_ m5228.sys
     |  |_ m5281.inf
     |  \_ m5281.sys
     |- disk1                   Driver disk label
     \_ txtsetup.oem            Windows NT/2k/XP setup file

--------------
4. insatll.ini
--------------
[OS Option]
x64Reboot = 0
XPReboot = 0
2000Reboot = 0
MEReboot = 0
98Reboot = 0
NT40Reboot = 0

There are 3 choices 0,1,2 for each OS
Default for all os is set to be 0
0 = Displays a dialog box that allows the end user to reboot the computer.
1 = It won't do anything after installing
2 = System will reboot immediately after 4seconds

[AP Items]
ULi5281=Y
JMAPP5281=N

Choosing "Y" will enable  RAID or JMAPP function for M5281/M5228
Choosing "N" will disable RAID or JMAPP function for M5281/M5228

Default is ULi5281=Y, JMAPP5281=N

---------------------
5. Driver Change List
---------------------

   5.0.2.3    07/0X/2003
   1. Fix 5283 PATA first channel detection problem.
   2. Fix JBOD partition format error.
   3. Fix NT4 can't create RAID error.

   5.0.2.4    09/03/2003
   1. Support Hibernation in DMA mode (Win2000/XP)
   2. Support RAID0, 1 on the same parallel ATA IDE channel
   3. Support Standby and Hibernation (WinMe)
   4. Fix the problem that sometimes system is failed to enter standby or
      hibernation (Win2000/XP)
   5. Fix the problem that system hangs up while accessing CDROM and disc 
      is in it. (Win98/Me/NT4.0)
   6. Solve the problem that sometimes it's hard to boot into OS (Win98/Me
      /NT4.0)
 	   
   5.0.2.5
   1. Fix the problem that blue screen appears while formatting (not Quick 
      Format) RAID 1 disk (Win2000/XP)
   2. Fix the problem that Seagate SATA HDD cannot be detected while hot-plug
      in (Win2000/XP)
   3. Fix the problem that blue screen appears while creating RAID 1 or JBOD
      by ALi RAID Utility (Win2000/XP)
   4. Fix the problem that sometimes system is unable to boot into OS when
      CDROM is connected (Win98/Me)
   5. Fix the problem that blue screen may appear by following these steps:
      (1) Restart system in OS
      (2) Boot into OS
      (Win98/Me)
      
   5.0.2.6
   1. Support Hot plug message on screen (Win2000/XP).
   2. Fix the problem that system may hang up by the following conditions: 
      (1) Booting from RAID 1 (mirror) disks
      (2) In OS, remove one of the mirrored disks
      (Win2000/XP)
   3. Add patch code for SAMSUNG DVD/CD-RW SM-316 to fix the problem that 
      system may hang up during booting when this DVD is installed on ATA 
      interface.
      (Win2000/XP)
   4. Fix the problem that system may hang up or get "Blue Screen" while 
      installing OS to WD 200GB HDD (Win2000/XP).
   5. Fix the problem that sometime system is unable to finish Hibernation
      when booted from SATA HDD. (Win2000/XP)
   6. Fix the problem that OS is unable to be installed when Hitachi 
      SATA HDD is connected. (Win2000/XP)
   7. Fix the problem that system may wait too long or hang up while doing
      transition to MS-DOS mode by these steps:
      Start->Shut Down->Restart in MS-DOS mode. (Win98)
   8. Support Hitachi SATA HDD.
      (Win98/Me/NT4.0/Win2000/XP)
      
   5.0.2.6a
   1. Support Windows Server 2003.
   2. Support M5285 hot-plug function. (Win2000/XP)
   3. Support Windows x64bit Edition

   5.0.2.8
   1. To support CD burning in DMA mode.
   
----
Note
----
 1. If your RAID BIOS is V0.92 or V0.93, you can use new released driver.
    But keep in mind, only use Setup Utility of RAID BIOS to create or 
    delete RAID.
 2. Don't remove ALi RAID Driver by "Add/Remove Program" if hard drives are
    boot devices and OS is Win2000 or WinXP. (Boot device means you boot OS 
    from it)
