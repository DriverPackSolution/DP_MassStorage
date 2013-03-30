******************************************************************************************
**
**        ARECA "SATA & SAS PCI" Driver Release 
**
******************************************************************************************
**        O.S   : Microsoft windows server 2K3 or later
**   FILE NAME  : ares_x86.sys
**        BY    : Erich Chen  ,mail address: erich@areca.com.tw
**   Description: Microsoft Windows STORPORT Device Driver 
**                for ARECA Co. Ltd. PCI RAID Host adapter
******************************************************************************************
** History:
**        REV#         DATE	            NAME	         DESCRIPTION
**     1.0.0.0     2/31/2008	       Erich Chen	     First release
**     1.0.0.1     3/19/2010           Erich Chen        Support 6G SAS HBA ARC1320    
**     6.0.0.0    10/10/2010           Erich Chen        1: bug fix ARC1300 ARC1320 running on windows 7 while hibernate S4 ,hibersleep S3.
**                                                       2: bug fix ARC1300 running if attached with TAPE device and Infortrain external SAS RAID system.
**                                                       3: improve ARCSAS max transfer length up to 4MB each command.  
**     6.0.0.2    08/19/2011           Erich Chen        add ioctl support
**     6.0.0.4    11/17/2011           Erich Chen        enhance ioctl support
**     6.0.0.5    03/06/2012           Erich Chen        bug fix for PMC-HP EXPANDER SES Page
**                                                       bug fix for DVD RW , TAPE Device media error
**                                                       cause device remove
**                                                       bug fix with cli device information consistence
**     6.0.0.6    03/28/2012           Erich Chen        bug fix for "HP TAPE testing utility"
**                                                       while Tape erase ,cause command timeout
**                                                       add SATA SSD TRIM command and SAS SSD UNMAP command 
**                                                       support    
******************************************************************************************








