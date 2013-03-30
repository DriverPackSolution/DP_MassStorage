************************************************************
************************************************************
*  Installation Readme for Intel(R) AHCI Storport Miniport Driver.
*
*  Refer to the system requirements for the operating 
*  systems supported by Intel(R) AHCI Storport Miniport Driver.
*
*  This document makes references to products developed by
*  Intel. There are some restrictions on how these products
*  may be used, and what information may be disclosed to
*  others. Please read the Disclaimer section at the bottom
*  of this document, and contact your Intel field
*  representative if you would like more information.
*
************************************************************
************************************************************

************************************************************
*  Intel is making no claims of usability, efficacy or 
*  warranty. The INTEL SOFTWARE LICENSE AGREEMENT contained
*  herein completely defines the license and use of this 
*  software.
************************************************************


************************************************************
*  CONTENTS OF THIS DOCUMENT
************************************************************

This document contains the following sections:

1.  Overview
2.  System Requirements
3.  Determining the System Mode
4.  Installing the Software
5.  Verifying Installation of the Software


************************************************************
* 1.  OVERVIEW
************************************************************

The Intel(R) AHCI Storport Miniport Driver is designed to provide 
functionality for the following Storage Controllers:

    AHCI Controllers:
    - Intel(R) ICH9R SATA AHCI Controller
  
************************************************************
* 2.  SYSTEM REQUIREMENTS
************************************************************

1.  The system must contain an Intel(R) Atom(TM) Processor
    and one of the following Intel products listed in section 1 above.    
    

2.  The system must be running on one of the following
    operating systems:

    - Microsoft* Windows* Home Server Power Pack-3
    - Microsoft* Windows* Storage Server 2008, x32 Edition 
    - Microsoft* Windows* Storage Server 2008, x64 Edition 

NOTE 1: If the system is running Windows* 64-bit version, 
        the Intel(R) AHCI Storport Miniport driver supporting 
        64-bit should be used.

3.  The following operating systems are not supported:

    Any version of Windows that is not listed in section #2


4.  The system should contain at least the minimum system 
    memory required by the operating system.

5.  The 'Intel(R) Chipset Software Installation Utility'
    must be installed prior to installing the 
    Intel(R) AHCI Storport Miniport Driver.


************************************************************
* 3.  DETERMINING THE SYSTEM MODE
************************************************************

To use this Readme effectively, you will need to know what 
mode your system is in. The easiest way to determine the 
mode is to identify how the Serial ATA controller is 
presented within the Device Manager. The following 
procedure will guide you through determining the mode.

1.  On the Start menu:
    1a. For Windows* 2008 or later operating systems,
        select Control Panel.

2.  Open the 'System' applet (you may first 
    have to select 'Switch to Classic View').

3.  Select the 'Hardware' tab. 

4.  Select the 'Device Manager' button.


6.  From the Device Manager, look for an entry named 
    'IDE ATA/ATAPI controllers'. If this entry is 
    present, expand it and look for one of the following
    controllers If this entry is present, 
    expand it and look for one of the controllers listed 
    in the Overview Section1. If an AHCI controller is 
    identified, then the system is in AHCI mode.

    If none of the controllers above are shown, then 
    your system is not in AHCI mode. No other modes are  
    supported by the Intel(R) AHCI Storport Miniport Driver
    and you should continue with step 7 below.

7.  Your system does not appear to be running in AHCI mode. 
    If you feel that your system is running in AHCI mode and
    you do not see any of the controllers listed above, you 
    may choose to contact your system manufacturer or place 
    of purchase for assistance.


************************************************************
* 4.  INSTALLING THE SOFTWARE
************************************************************


4.1 Pre-Installation Using the F6 Method. 

Note: The Steps 1 and 2 can be skipped if you use the F6 Floppy
      disk utility provided by Intel. These methods 
      are applicable to systems configured for
      AHCI mode.

1.  Extract all driver files from the zipped package.
    

2.  Create a floppy* containing the following files in the root 
    directory:
    ich9rmp.sys, ich9rmp.cat,
    TxtSetup.oem, oemsetup.inf 

    * Note: For Windows 2008 you can use a floppy, CD/DVD or USB.

3.  For Windows Home Server operating systems:

    - At the beginning of the operating system installation,
     press F6 to install a third party SCSI or RAID driver.

    - When prompted, select 'S' to Specify Additional Device.

    - Continue to step 5.

4.  For Windows 2008:

    - During the operating system installation, after selecting the 
     location to install Vista, click Load Driver to install a third 
     party SCSI or RAID driver.

    - Continue to step 5.

5.  When prompted, insert the media (floppy, CD/DVD or USB) you 
    created in step 2 and press Enter.

6.  At this point you should be presented with a selection
    for one of the controllers listed in the Overview (Section 1) 
    of this document depending on your hardware version and 
    configuration.

7.  Highlight the selection that is appropriate for the 
    hardware in your system and press Enter.

8.  Press Enter again to continue. Leave the floppy disk in 
    the system until the next reboot as the software will 
    need to be copied from the floppy disk again when setup
    is copying files.


************************************************************
* 5.  VERIFYING INSTALLATION OF THE SOFTWARE
************************************************************

5.1 Verifying Have Disk, F6, or Unattended Installation: 
    depending on your system configuration, refer to the 
    appropriate sub-topic below:


5.1a Systems Configured for AHCI Mode:

1.  On the Start menu:
    1a. For Windows* Home Server Ver. 1.0 select Control Panel.
2.  Open the 'System' applet (you may first 
    have to select 'Switch to Classic View').
3.  Select the 'Hardware' tab in Windows* Home Server Ver 1.0.
4.  Select the 'Device Manager' button.
5.  Expand the 'IDE ATA/ATAPI controllers' entry.
6.  Right-click on Intel(R) AHCI Storport Miniport Driver.
7.  Select 'Properties'.
8.  Select the 'Driver' tab.
9.  Select the 'Driver Details' button.
10. If the 'ich9rmp.sys' file is displayed, the installation 
    was successful.



************************************************************
* DISCLAIMER
************************************************************

Information in this document is provided in connection with
Intel products. Except as expressly stated in the INTEL
SOFTWARE LICENSE AGREEMENT contained herein, no license,
express or implied, by estoppel or otherwise, to any
intellectual property rights is granted by this document.
Except as provided in Intel's Terms and Conditions of Sale
for such products, Intel assumes no liability whatsoever,
and Intel disclaims any express or implied warranty,
relating to sale and/or use of Intel products, including
liability or warranties relating to fitness for a particular
purpose, merchantability or infringement of any patent,
copyright or other intellectual property right. Intel
products are not intended for use in medical, lifesaving,
or life sustaining applications.

************************************************************
* Intel Corporation disclaims all warranties and liabilities
* for the use of this document, the software and the
* information contained herein, and assumes no
* responsibility for any errors which may appear in this
* document or the software, nor does Intel make a commitment
* to update the information or software contained herein.
* Intel reserves the right to make changes to this document
* or software at any time, without notice.
************************************************************

* Third-party brands and names may be claimed as the 
  property of others.

Copyright (c) Intel Corporation, 2001-2010
*******************************************************************************
* INTEL SOFTWARE LICENSE AGREEMENT
*******************************************************************************

INTEL SOFTWARE LICENSE AGREEMENT (OEM / IHV / ISV Distribution & Single User)

IMPORTANT - READ BEFORE COPYING, INSTALLING OR USING. 
Do not use or load this software and any associated materials (collectively, the "Software") until you have carefully read the following terms and conditions. By loading or using the Software, you agree to the terms of this Agreement. If you do not wish to so agree, do not install or use the Software.

Please Also Note:
* If you are an Original Equipment Manufacturer (OEM), Independent Hardware Vendor (IHV), or Independent Software Vendor (ISV), this complete LICENSE AGREEMENT applies;
* If you are an End-User, then only Exhibit A, the INTEL SOFTWARE LICENSE AGREEMENT, applies.

For OEMs, IHVs, and ISVs:

LICENSE. This Software is licensed for use only in conjunction with Intel component products.  Use of the Software in conjunction with non-Intel component products is not licensed hereunder. Subject to the terms of this Agreement, Intel grants to you a nonexclusive, nontransferable, worldwide, fully paid-up license under Intel's copyrights to:
	a) use, modify and copy Software internally for your own development and maintenance purposes; and
	b) modify, copy and distribute Software, including derivative works of the Software, to your end-users, but only under a license agreement with terms at least as restrictive as those contained in Intel's Final, Single User License Agreement, attached as Exhibit A; and
	c) modify, copy and distribute the end-user documentation which may accompany the Software, but only in association with the Software.

If you are not the final manufacturer or vendor of a computer system or software program incorporating the Software, then you may transfer a copy of the Software, including derivative works of the Software (and related end-user documentation) to your recipient for use in accordance with the terms of this Agreement, provided such recipient agrees to be fully bound by the terms hereof.  You shall not otherwise assign, sublicense, lease, or in any other way transfer or disclose Software to any third party. You shall not reverse- compile, disassemble or otherwise reverse-engineer the Software.

Except as expressly stated in this Agreement, no license or right is granted to you directly or by implication, inducement, estoppel or otherwise.  Intel shall have the right to inspect or have an independent auditor inspect your relevant records to verify your compliance with the terms and conditions of this Agreement.

CONFIDENTIALITY. If you wish to have a third party consultant or subcontractor ("Contractor") perform work on your behalf which involves access to or use of Software, you shall obtain a written confidentiality agreement from the Contractor which contains terms and obligations with respect to access to or use of Software no less restrictive than those set forth in this Agreement and excluding any distribution rights, and use for any other purpose.
Otherwise, you shall not disclose the terms or existence of this Agreement or use Intel's name in any publications, advertisements, or other announcements without Intel's prior written consent.  You do not have any rights to use any Intel trademarks or logos.

OWNERSHIP OF SOFTWARE AND COPYRIGHTS. Title to all copies of the Software remains with Intel or its suppliers. The Software is copyrighted and protected by the laws of the United States and other countries, and international treaty provisions. You may not remove any copyright notices from the Software. Intel may make changes to the Software, or to items referenced therein, at any time and without notice, but is not obligated to support or update the Software. Except as otherwise expressly provided, Intel grants no express or implied right under Intel patents, copyrights, trademarks, or other intellectual property rights. You may transfer the Software only if the recipient agrees to be fully bound by these terms and if you retain no copies of the Software.

LIMITED MEDIA WARRANTY. If the Software has been delivered by Intel on physical media, Intel warrants the media to be free from material physical defects for a period of ninety (90) days after delivery by Intel. If such a defect is found, return the media to Intel for replacement or alternate delivery of the Software as Intel may select.

EXCLUSION OF OTHER WARRANTIES. EXCEPT AS PROVIDED ABOVE, THE SOFTWARE IS PROVIDED "AS IS" WITHOUT ANY EXPRESS OR IMPLIED WARRANTY OF ANY KIND, INCLUDING WARRANTIES OF MERCHANTABILITY, NONINFRINGEMENT, OR FITNESS FOR A PARTICULAR PURPOSE.  Intel does not warrant or assume responsibility for the accuracy or completeness of any information, text, graphics, links or other items contained within the Software.

LIMITATION OF LIABILITY. IN NO EVENT SHALL INTEL OR ITS SUPPLIERS BE LIABLE FOR ANY DAMAGES WHATSOEVER (INCLUDING, WITHOUT LIMITATION, LOST PROFITS, BUSINESS INTERRUPTION OR LOST INFORMATION) ARISING OUT OF THE USE OF OR INABILITY TO USE THE SOFTWARE, EVEN IF INTEL HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES. SOME JURISDICTIONS PROHIBIT EXCLUSION OR LIMITATION OF LIABILITY FOR IMPLIED WARRANTIES OR CONSEQUENTIAL OR INCIDENTAL DAMAGES, SO THE ABOVE LIMITATION MAY NOT APPLY TO YOU. YOU MAY ALSO HAVE OTHER LEGAL RIGHTS THAT VARY FROM JURISDICTION TO JURISDICTION. 

TERMINATION OF THIS AGREEMENT. Intel may terminate this Agreement at any time if you violate its terms. Upon termination, you will immediately destroy the Software or return all copies of the Software to Intel.
 
APPLICABLE LAWS. Claims arising under this Agreement shall be governed by the laws of California, excluding its principles of conflict of laws and the United Nations Convention on Contracts for the Sale of Goods. You may not export the Software in violation of applicable export laws and regulations. Intel is not obligated under any other agreements unless they are in writing and signed by an authorized representative of Intel.

GOVERNMENT RESTRICTED RIGHTS. The Software is provided with "RESTRICTED RIGHTS." Use, duplication, or disclosure by the Government is subject to restrictions as set forth in FAR52.227-14 and DFAR252.227-7013 et seq. or their successors. Use of the Software by the Government constitutes acknowledgment of Intel's proprietary rights therein. Contractor or Manufacturer is Intel Corporation, 2200 Mission College Blvd., Santa Clara, CA 95052.


EXHIBIT "A" 
INTEL SOFTWARE LICENSE AGREEMENT (Final, Single User)

IMPORTANT - READ BEFORE COPYING, INSTALLING OR USING. 
Do not use or load this software and any associated materials (collectively, the "Software") until you have carefully read the following terms and conditions. By loading or using the Software, you agree to the terms of this Agreement. If you do not wish to so agree, do not install or use the Software.

LICENSE. You may copy the Software onto a single computer for your personal, noncommercial use, and you may make one back-up copy of the Software, subject to these conditions: 
1. This Software is licensed for use only in conjunction with Intel component products.  Use of the Software in conjunction with non-Intel component products is not licensed hereunder. 
2. You may not copy, modify, rent, sell, distribute or transfer any part of the Software except as provided in this Agreement, and you agree to prevent unauthorized copying of the Software.
3. You may not reverse engineer, decompile, or disassemble the Software. 
4. You may not sublicense or permit simultaneous use of the Software by more than one user.
5. The Software may contain the software or other property of third party suppliers, some of which may be identified in, and licensed in accordance with, any enclosed "license.txt" file or other text or file. 

OWNERSHIP OF SOFTWARE AND COPYRIGHTS. Title to all copies of the Software remains with Intel or its suppliers. The Software is copyrighted and protected by the laws of the United States and other countries, and international treaty provisions. You may not remove any copyright notices from the Software. Intel may make changes to the Software, or to items referenced therein, at any time without notice, but is not obligated to support or update the Software. Except as otherwise expressly provided, Intel grants no express or implied right under Intel patents, copyrights, trademarks, or other intellectual property rights. You may transfer the Software only if the recipient agrees to be fully bound by these terms and if you retain no copies of the Software.

LIMITED MEDIA WARRANTY. If the Software has been delivered by Intel on physical media, Intel warrants the media to be free from material physical defects for a period of ninety (90) days after delivery by Intel. If such a defect is found, return the media to Intel for replacement or alternate delivery of the Software as Intel may select.

EXCLUSION OF OTHER WARRANTIES EXCEPT AS PROVIDED ABOVE, THE SOFTWARE IS PROVIDED "AS IS" WITHOUT ANY EXPRESS OR IMPLIED WARRANTY OF ANY KIND INCLUDING WARRANTIES OF MERCHANTABILITY, NONINFRINGEMENT, OR FITNESS FOR A PARTICULAR PURPOSE.  Intel does not warrant or assume responsibility for the accuracy or completeness of any information, text, graphics, links or other items contained within the Software.

LIMITATION OF LIABILITY.  IN NO EVENT SHALL INTEL OR ITS SUPPLIERS BE LIABLE FOR ANY DAMAGES WHATSOEVER (INCLUDING, WITHOUT LIMITATION, LOST PROFITS, BUSINESS INTERRUPTION, OR LOST INFORMATION) ARISING OUT OF THE USE OF OR INABILITY TO USE THE SOFTWARE, EVEN IF INTEL HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES. SOME JURISDICTIONS PROHIBIT EXCLUSION OR LIMITATION OF LIABILITY FOR IMPLIED WARRANTIES OR CONSEQUENTIAL OR INCIDENTAL DAMAGES, SO THE ABOVE LIMITATION MAY NOT APPLY TO YOU. YOU MAY ALSO HAVE OTHER LEGAL RIGHTS THAT VARY FROM JURISDICTION TO JURISDICTION. 

TERMINATION OF THIS AGREEMENT. Intel may terminate this Agreement at any time if you violate its terms. Upon termination, you will immediately destroy the Software or return all copies of the Software to Intel.
 
APPLICABLE LAWS. Claims arising under this Agreement shall be governed by the laws of California, excluding its principles of conflict of laws and the United Nations Convention on Contracts for the Sale of Goods. You may not export the Software in violation of applicable export laws and regulations. Intel is not obligated under any other agreements unless they are in writing and signed by an authorized representative of Intel.

GOVERNMENT RESTRICTED RIGHTS. The Software is provided with "RESTRICTED RIGHTS." Use, duplication, or disclosure by the Government is subject to restrictions as set forth in FAR52.227-14 and DFAR252.227-7013 et seq. or their successors. Use of the Software by the Government constitutes acknowledgment of Intel's proprietary rights therein. Contractor or Manufacturer is Intel Corporation, 2200 Mission College Blvd., Santa Clara, CA 95052.
 
SLAOEMISV1/RBK/01-21-00

LANGUAGE; TRANSLATIONS.  In the event that the English language version of this Agreement is accompanied by any other version translated into any other language, such translated version is provided for convenience purposes only and the English language version shall control.


