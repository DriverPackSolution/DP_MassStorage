=================================================================
========================
               Broadcom BCM5785 (a.k.a HT1000) SATA Controller README.TXT



             Copyright (c) 2006.  Broadcom Corporation, Inc.
 All rights reserved.

=================================================================

========================

Welcome to the Broadcom HT1000 Series Controller. This document 
provides important release information that should be read before 
using this driver.



ABOUT THIS RELEASE
==================
Date		: 10/21/2008 (WHQL certified)
Release Version : 1.1.8070.1
Certification   : WHQL Certified release of Windows Server 2008 (x86) driver for HT1000 SATA Controller.


OPERATING SYSTEMS SUPPORTED
===========================
Windows Server 2008 (x86) 

Driver Name
===========
bchtsw32.sys 


FEATURES SUPPORTED
==================
1.Hot plug
2.NON NCQ mode on SATA drives.
3.NCQ support on revisions B0 & later.
4.SATA ATAPI support for Removable drives.


BUG FIXES:
=========
1.Fixed the Slow Response during large file copy using a RD1000 SATA ATAPI removable drive. 


KNOWN ISSUES
============
* No known issues.


CONTACT INFORMATION
===================
1.satish@broadcom.com
