***********************************
*                                 *
* MegaRAID IDE Driver Diskette    *
*                                 *
***********************************


====================
Contents on the disk
====================
README   TXT            This readme file
MEGAIDE                 Microsoft Windows miniport disk label file 
TXTSETUP OEM            Microsoft Windows miniport text mode setup file

Win64       <DIR>
  MEGAIDE  SYS          Microsoft Windows miniport driver for 64Bit Platforms.
  MEGAIDE  INF          Microsoft Windows setup file.

Windows       <DIR>
  MEGAIDE  SYS          Microsoft miniport driver.
  MEGAIDE  INF          Microsoft Windows miniport setup file.


================
Software Version
================
Microsoft Windows miniport driver Version - 4.4.0630.2006
 

==========
What's New
==========
Driver Version 4.4.0630.2006
- Added support for new ICH7R Intel IDs.

Driver Version 4.3.0316.2006
- Driver ID list updated.

Driver Version 4.2.0318.2005
- Driver ID list updated.

Driver Version 4.2.0121.2005
- Driver ID list updated.

Driver Version 4.2.0107.2005
- Driver Packaging Issue fixed.

Driver Version 4.2.1118.2004
- hibernation blue screen fix is implemented in this version.

Driver Version 4.2.1109.2004
- Added additional IDs for Intel.

Driver Version 4.2.1012.2004
- CLASS Code check added in driver for ICH6R Controllers.
- Driver was aborting a Rebuild or Check consistency operations on one SPAN of RAID10 when 
  a physical drives changes state on the other leg.

Driver Version 4.2.0929.2004
- Invalid SGLIST was build when the driver was doing the error Handling.
- Driver was programming both the drives on the channel when issuing a reset during error handling.

Driver Version 4.2.0907.2004 - Re-Release
- Missed to update the driver minor version while packaging.

Driver Version 4.2.0907.2004 
- The following Fixes are done.
1. Bump up the Minor Version number.
2. Updated some ID's.
3. RAID 10 logical dirve size change problem fixed.
4. 4 MB rounding done for inserted drive.
5. Always setting spy status change flag in Physical drive IOCTLS. 
   Protected this under IRCD version check since this should be 
   done only for IRCD verion 2x.
6. When the drive is inserted the driver should not put it blindly in to rebuilding state 
   rather it should check the mirror state and then decide in what state this drive should go in.
7. When rebuilding using hotspare drive the logic of moving the failed drive to Ready is changed.
8. Updating the water mark depending on physical drive percentage rather than on logical drive 
   percentage for rebuilding is implemented.
9. When we try to boot from single span the driver was continiously timing out 
   since the driver was touching the offline drives. Strict checks should be 
   implemented in buildIO and offline drives should be removed from the list.
10. Modified the ICH6r drive hot insertion code for drive hot removal.
11. Changed the polling time from 60 Sec to 2 Seconds.

Driver version 4.1.0817.2004[Re-Release]
- This is a Re-Release of 4.1.0817.2004 driver. 
  Only The Package is changed to address 64-Bit installtion issues.
  Spy installation is removed from this package upon request.

Driver version 4.1.0817.2004
- The Driver is updated with the list of latest IDs.
- Problem of driver not loading on 64-Bit operating systems is resolved.
- The Package is updated so that the .dll files left by the package are deleted after installation.

Driver version 4.1.0813.2004
- Driver was not initializing the IRCD Sector Index and Enquiry sector Index properly. 
  Since the value was not initialized we were writing to sector ZERO whenever we were 
  updating the IRCD or Enquiry.

Driver version  4.1.0805.2004 - Re-Release on Aug102004 -Only Changes in Release package
- Added support for Automatic Installation of SPY.

Driver version  4.1.0805.2004
- Added some IDs to Windows Driver.
	
- Added Spport for ATAPI Devices.
- RAID10 Fix incorporated in driver.

Driver version  4.1.0708.2004
- Added Default ICH6R IDs for UT to continue.

Driver version  4.1.0706.2004
- ICH6R support added.
- RAID 10 support added for IRCD3x.
- Soft BBM Support added.
- Please refer release notes for detailed description.

Driver version  4.1.0416.2004
- IA32 E support Added
- LSI Logic string in Txtsetup.oem changed ot Intel name.


Driver version  4.1.0414.2004
- Windows driver has a algorithm for detection of drives. It fires NO_OP command to drive and 
  the reponse of the drive for this command tells us that weather the drive is present or not.
  The time taken by the seagate drives was more than the driver wad waiting for. 
  The seagate drives were taking about 150 Ms while the driver was only waiting for 1 Ms and after 
  this time has elapsed the driver will assume that the drive is not connected. No further attemps to 
  detect the drives will be made by the driver. 

Driver version  4.1.0406.2004
- Driver was not picking Fix&Report/ReportOnly Flag from enquiry. The driver was picking it up when 
  the application send the driver IOCTL_SET_RAID_OPTIONS. This IOCTL will no longer be available for
  IRCD_3x and the driver will fill up these values only from Enquiry. If the application wants to 
  set this value it will have to use set enquiry IOCTL.
- When the drive is pulled while the operating system is booting the driver was not updating IRCD.
  This is taken care in this driver.
- The Drive insertion algorithm is modified because the exisiting algorithm was failing on FSC Hance 
  rapid machine. We were detecting drive present for the drive that is removed.


Driver version  4.1.0329.2004
- Windows was freezing when Rebuilding was done with Heavy IO operations. 
  This was because of the fact that the driver was doing load balancing 
  on the channel basis and switching the drives on different channels. 
  The driver was ending up in a condition where it will keep on switching 
  to channel zero and will not actually post the command because a command 
  is actually pending on the channel zero. In this condition the driver  
  repeatedly switched to channel zero and end up in a infinite loop. The problem 
  is handled by checking for pending interrupt on the target channel before 
  switching to it. 

Driver version  4.1.0308.2004
- Intel Change request for the driver package incorporated.
- Intel IDs updated as per the latest documentation.

Driver version  4.1.0226.2004
- 48Bit LBa Fixes Implemented.
- Error Log Fixes Implemented in FastIDELogError,IOCTLEraseErrorLog,IOCTLGetErrorLog.

Driver version 4.1.0116.2004
- Added the support for the FSC SSID - 1040.
- Removed the Access to the reserved bit of CMD648/649 controllers.

Driver version 4.1.1120.2003
- Changed the SSID from 3429 to 1034. 

Driver version 4.1.1106.2003
- Implemented Drive Extended size Coersion for IRCD Verison 3.1. 

Driver version 4.1.1015.2003
- When the PIO Write command was issued using PASS_THRU interface the Drive was going in to undefined state and 
  driver was timing out the command. This problem was there because the driver was not checking the busy bit before 
  writing on the drive. The driver now checks the BUSY bit and the DRQ bit properly to ensure the proper handshake.

Driver version 4.1.1008.2003
- Rebuilding was getting aborted when heavy IOs were run and the drive is inserted. This was because of the problem that the 
  IRCD update at the start of rebuild was not getting fired. This problem is taken care in this driver release.

- 6300ESB support added.

Driver version 4.1.0912.2003
- This is the initial release for Intel ICH5R product.

Driver version 4.1.0724.2003
- problem of not sending proper error log info to applicaion is fixed.

Driver version 4.1.0721.2003
- The Stripe Size problem is fixed in Driver for all the path and for RAID 1.

Driver Version 4.1.0709.2003
- The INODE fix is changed to a common code so that it is applicable to all the chips.

Driver Version 4.1.0626.2003
- Stripe size reported to application is fixed.
- The Write verify command was not getting completed in Reset bus if the Drive power is pulled.
- Inode Fix is incorporated for all the controllers.

Driver version 4.1.0426.2003
- Fastidefirecommand Modified for better performance.
- Base Class and Sub Class Code check added in driver.


Driver version 4.1.0412.2003
- The Reset bus seen on RAID 10 configuration is fixed.
- Low performance seen on the Disk Transfer Rate test is fixed.


Driver version 4.1.0313.2003
- The system Hang on drive power pulling is fixed.

Driver version 4.1.0312.2003
- The system crash on drive power pulling in case of raid 0 is fixed.
- The reset bus reported by the testing team is resolved in this driver.
- The data integrity test failing on dit32 is fixed.
- Inf checker failing for .Net 2003 is fixed and verified. 

Driver version 4.1.0307.2003
- The Driver now updates the Timestamp Following the protocol provided by the BIOS 
  Team.

Driver version 4.0.0303.2003
- IOCTL IOC_GET_CONTROLLER_INFO modified to provide subsystem device id 
  and vendor id information.

Driver version 4.0.0225.2003
- This Driver has a additional interface for providing the Aspi PASSTHRU IOCTLs.

Driver version 4.0.0129.2003
- The inconsistencies were not reported by the driver for IRCD2x.This Driver reports the inconsistencies to Spy.
- The Hotspare drive was indicated as a part of array for IRCD2x.

Driver version 4.0.0115.2003
- The Driver version in the .INF file is corrected.
- The Driver now updates the time stamp when updating the IRCD.
- Fixes for CSB6. 
- Check added for not to post commands to the removed drive.
- Time stamp update for Ircd 2x.

Ver 4.0.2002.0916-Sept 16,2002 

� Drive insertion and Removal Fine Tuned and Reset bus on Drive insertion eradicated.

� When the Logical Drive is deleted the Drive뭩 Hold Queue is scanned and all the 
  commands for that logical drive will be cleared.

� Nodev.Inf File changed to address the Driver upgrade issue.

� Load Balancing algorithm modified for better performance.

� When the Drive was made Hotspare sometime the system was crashing.
  The problem is taken care in this release.

� Updating IRCD modified to go through the new path.

� Failing of the Raid 0 Drive was previously rejected by the driver. 
  The driver now handles this call.


Ver 4.0.2002.0809-Aug 09,2002 
 * Gate Keeper Opertation update when the Physical Drive status is changed.
 * Deleting the Logical drive when IOs are going on was resulting in Reset BUS. 
   The Dirve was not handling properly the commands in the Queue for that Logical Drive.


Ver 4.0.2002.0805-Aug 05,2002 
 * Physical Drive Status is filled when the New IRCD is obtained.
 * Status Incompatibility for OFFLINE Status between Driver and Application is removed.


Ver 4.0.2002.0801-Aug 01,2002 
 * Error in handling Spurious Interrupts is fixed.
 * The Transfer mode for the drive was not getting programmed with a value set in enquiry. This is taken care in this release.
 * This Driver initiates a bus rescan when a logical drive is inserted or deleted.
 * This Driver initiates a bus rescan when a logical drive is inserted or deleted.
 * This Driver Notifies the Application about the Drive whose power is pulled.
 * TextSetup.Oem Modified to give the Option for Windows .NET and Windows XP.


Ver 4.0.2002.0717-july 17,2002 
  * Requested Subsystem Device ID and Vendor ID supported.

Ver 4.0.2002.0701-july 01,2002 
  * Diagnostics IOCTLS implemented.
  * physical Drive insertion and Removal IOCTLS implemented.
  * Make Drive online now checks for the Deleted drives before making them online.
  * Auto Resume feature of Rebuilding and consistency is now limited only to power 
    failure cases.

Ver 4.0.2002.0618-June 18,2002 
  * Logical Drive insertion and Deletion is Tested and fixed.
  * Installation of OS on any Logical Drive is Implemented.
  * Class Code Check for loading the  Driver is implemented.

Ver 4.0.2002.0531-May 31,2002 
  * Driver was not handling IO's in proper fasion and Internal Queue corruption
    was happening for IO's when check consisteny was going on.This Que corruption 
    was leading to System crash. This driver has the fix for this problem. 
  * Installation strings are changed. 

Ver 4.0.2002.0528-May 28,2002 
  * Driver was not able to Update the IRCD after rebuild.This driver takes care of 
	this issue and Updates the IRCD successfully.

Ver 4.0.2002.0522-May 22,2002 
  * Windows NT Installation problem is Fixed.
  * Dummy Device Is modified so that Windows will not see any RAID dummy device.
  * Additional check for Gate commands While merging the commands is put in.
  * Both the IRCD buffer are synchronized for the IOCTL Path.
  * Strings are modified in TextSetup.oem.
   

Ver 4.0.2002.0516-May 16,2002 
  * The driver was not filling up the stripe size properly and this caused problems in 
    Raid 0.

Ver 4.0.2002.0515-May 15,2002 
  * Additional Validations for the parameters are added for stability of the driver.
  * The driver was not filling up the Checksum for the IRCD and IRCD header in the IOCTL path.
    The Driver now takes care of it.

Ver 4.0.2002.0514-May 14,2002 

  * The IOCTLS Read Write IRCD and Read Write Enquiry were not handled properly and 
    were leading to problems with Drive Rebuilding. The variables used in these IOCTLS 
    are now handled properly.

  * The Driver was not filling up the Array information properly in the case of Multiple 
    arrays and hence the Driver was behaving Strange with Two Arrays. Now the proper values are filled up 
    in Driver data Structures and Driver works fine with multiple Arrays. 

Ver 4.0.2002.0509-May 09,2002 
  * The Driver was Crashing after the first phase of windows 2000 installation.

Ver 4.0.2002.0503-May 03,2002 
  * The Message string has been changed in textsetup.oem file. 
  * The driver was not updating the IRCD Checksum and hence had some 
    compatibility problems with bios released on 24th April. 
    Driver now updates the Checksum correctly.
  * Drive Insertion and removal is implemented for Yellow stone.
  * CRC Error handling is implemented for Yellow Stone.

Ver 4.0.2002.0426-April 26,2002 
  * The Driver was not loading with latest Bios Released on 4/24/2002.
    The Problem is fixed.

Ver 4.0.2002.0425-April 25,2002 
  * IOCTL Implementation Enhanced.
  * Some Ioctl implementation bugs were fixed.	

Ver 4.0.2002.0321-March 28,2002
  * The New IRCD (v3.x) as documented in Rev1.03 is supported by this driver. 
    The old IRCD (v2.x) is also supported for compatibility reasons. 
  * The new ioctls documented in the IDE Driver Interface Rev2.7 are supported with some restrictions.
  * 48-bit addressing support was fully implemented.
  * Rebuilding is done on a Physical Drive basis.
  * Check Consistency is done on a Logical Drive basis, so multiple Check Consistency per array are feasible.
  * Auto resume of rebuilding is supported by the driver, ie., a rebuild which has been aborted by the user can be restarted.
  * The following ioctls have been added :
  * IOCTL Get Version
  * IOCTL Physical Drive Info
  * IOCTL Logical Drive Info
  * IOCTL Raid Status Info_EX
  * IOCTL SetDrive Status
  * IOCTL Send Activity_EX
  * IOCTL Get Activity_EX
  * GET / SET EnquiryData
  * GET / SET IRCD Data ( With some restriction)

 
Ver 3.0.2002.0321-March 21,2002
  * The Event count was not reduced even when we were discarding the Oldest event from 
   the log and now is taken care in the code.
 

Ver 3.0.2002.0320-March 20,2002

  * Queue manupulating fix is made to the buffer holding the events	

Ver 3.0.2002.0319-March 19,2002
  *When the write error the the reason for command now logs as OTHER Error 
   rather than medium error. Though the last release 3.0.2002.0318 also address this 
   issue due to some inconsistencies in the driver the issue was not resolved. 

Ver 3.0.2002.0318-March 18,2002
  * When the write error the reason for command now logs as OTHER Error 
    rather than medium error.


Ver 3.0.2002.0317-March 17,2002
  * The Driver Now removes the hotSpare drives from the Logical Drives and hence fills the 
	information corretly to the Spy.
 
Ver 3.0.2002.0315-March 15,2002
  * The Driver differentiates medium errors from other errors and Logs the messeges accordingly.
 

Ver 3.0.2002.0313-March 13,2002
  * Fixed the problem of Write Errors were being posted as Medium Errors to Logs.
  * Instead of posting Sector of the actual error we were posting the offset where error occured.
  

Ver 3.0.2002.0312-March 12,2002
  * Smart status and Command type for read error.
  * Adding new drive only to spare pool.
  * Blue panic when boot from degraded array.
  * Additional Sub system Device Id and subsystem Vendor ID added for Toshiba
ver 3.0.2002.0308 -March 08, 2002
  * Fixed the problem for drive disappearing on write error.
  * NVRAM Events fixed.

ver 3.0.2002.0305 -March 05, 2002
  * Boot up Problem fixed.
  * Fix for Making the Drive hotspare.
  * Fixed the bug for Write Errors.
  
ver 3.0.2002.0301 -March 01, 2002
  * Rebuild initiation error is fixed.
  * Structures Packed identically in Application and driver.	 

ver 3.0.2002.0226 -Feb 26, 2002
  * I/O Error Recover is implemented.
  * Rebuilding Error Recovery is implemented.
  * Error Injection and Validation is implemented.

ver 3.0.2002.0219 -Feb 19, 2002
  * This Driver implements the new Error handling Algorithms.

ver 3.0.2002.0214 -Feb 14, 2002
  * ServerWorks Support is added and tested for WindowsNT 4.0 and Windows2000.
ver 3.0.2002.0205 -Feb 05, 2002
  * Driver Crash when the spy was started under windows 2000.
  * Added Support for Serverworks Board.	
ver 3.0.2002.0125 -Jan 25, 2002
  * Driver Crash During Bootup when SPY installed as service is fixed.
  * Problem of not firing commands to the slave Drive is fixed.	
ver 3.0.2002.0114 -Jan 14, 2002
  * Some problems in Starting the rebuilds are fixed.
ver 3.0.2002.0108 -Jan 08, 2002
  * Some problems in Drive insertion and removals fixed.
  * Now supports higher capacity drives
  * 680 chip support added
  * Some problems with NVRAM events fixed.
  * Error handling enhanced.

ver 3.0.2001.1218 - Dec 18, 2001
  * Problem of drive removal after inserting causing system freeze fixed
  * Driver application interface changed for NVRAM events.
  * provided new IOCTL interface to the application

ver 3.0.2001.1130 - Nov 30, 2001
  * Drive insertion problems fixed
  * Now the error path will use the Drive's block reassignment feature
  * Provided extra function for the application
  * Drive removal notification will now work for spare drives and failed drives also

ver 3.0.2001.1121 - Nov 21, 2001
  * Blue Screen Fix while inserting the Drive is incorporated.
  * Error Log IOCTL implementation is done.
  * Timeout Problem is fixed.
  * SMART Implementation is done.
  * PASSTHRU implementation is done.
ver 3.0.2001.1120 - Nov 20, 2001
  * Error Log is implemented
  * PassThru and Smart implementation done
  * Problem with NVRam events posting is fixed
  * IRCD updation problem fixed.
ver 3.0.2001.1115 - Nov 15, 2001
  * Windows NT Installation Bug fixed.
  * Flag updation corrected.  
ver 3.0.2001.1105 - Nov 05, 2001
  * Fixed the Consistancy check Issues.
  * Fixed Rebuild Issues.
  * Fixed Verify command issues.
ver 3.0.2001.1026 - Oct 26, 2001
  * Fixed all IRCD updation problems.
ver 3.0.2001.1024 - Oct 24, 2001
  * Disabled LSI backplane support, since it is malfunctioning in NT.
  * Ported previously 2k driver for NT.
ver 3.0.2001.1019 - Oct 19, 2001
  * Initial Binary for 3.0.

