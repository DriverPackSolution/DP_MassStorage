******************************************************************************************
**
**        ARECA "SATA & SAS PCI RAID" Driver Release 
**
******************************************************************************************
**        O.S   : Microsoft windows 2K XP 2K3
**   FILE NAME  : arcm_a64.sys
**        BY    : Erich Chen  ,mail address: erich@areca.com.tw
**   Description: Microsoft Windows SCSIPORT Device Driver 
**                for ARECA Co. Ltd. PCI RAID Host adapter
******************************************************************************************
** History:
**        REV#         DATE	            NAME	         DESCRIPTION
**     1.00.00.00     3/31/2004	       Erich Chen	        First release
**     1.01.00.00    11/29/2004	       Erich Chen	 Bug fix with Bus reset if PHY error(Device error)
**     1.02.00.00     6/29/2005	       Erich Chen	 Bug fix with abort command,add ARC1x70 serial adapters support
**     1.20.00.13    11/29/2005	       Erich Chen	 add ioctl code 'ARCMSR_IOCTL_FLUSH_ADAPTER_CACHE',
**                                                   customer can send this command for sync its raid volume data,
**                                                   Bug fix with abort command,
**                                                   scheduling pending ccb with first in first out
**						                             add scsi device "iop processor" id 16
**                    7/29/2006	       Erich Chen    add SAS RAID adapters support
**     6.20.00.14    03/22/2007	       Erich Chen	 Bug on shutdown notify
**     6.20.00.15    04/04/2007	       Erich Chen	 add new host adapter
**     6.20.00.16    04/04/2008	       Erich Chen	 add Bus change notify
**     6.20.00.17    09/04/2008	       Nick  Cheng	 add system event log text notify
**     6.20.00.18    04/04/2009	       Erich Chen	 support max transfer length into 16M bytes 
**                                                   for each request        
**     6.20.00.19    06/04/2009	       Erich Chen	 fix storport ioctl  
**     6.20.00.20    01/25/2010	       Erich Chen	 support ARC1880   
**     6.20.00.21    07/13/2011	       Erich Chen	 modify os scsi id map for raid scsi id  
**                                                   scsi 0...127 into scsi 0...15 lun 0...7
******************************************************************************************









