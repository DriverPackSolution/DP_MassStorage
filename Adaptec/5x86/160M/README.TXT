===================================================================
=         Adaptec Family Manager Set v4.0a Service Pack 4         =
=                           Update Notes                          =
===================================================================

The Adaptec FMS v4.0a Service Pack 4 diskette can be used for fresh
or an upgrade driver installation. This diskette replaces any 
previous driver found on the FMS 4.0 CD, and works in conjunction 
with previous service packs. Always use the latest applicable 
service pack. Please refer to the readme file found on the Adaptec
FMS 4.0 CD for further instructions on installing these drivers.

===================
= Version History =
===================

-------------------------
Changes in Service Pack 4
-------------------------

Windows XP:

  Driver Name: ADPU160M.SYS (Ultra160)

  Addressed Issues:

  - SCSI Hard Drive LED now stays off during Standby.

  - Resolved an issue where the driver only negotiates to 
    asynchronous/narrow speeds to any non-hard disk device (CD,
    tape drives, etc.).

Windows 2000:

  Driver Name: ADPU160M.SYS (Ultra160)

  Addressed Issues:

  - Adds clustering support.

-------------------------
Changes in Service Pack 3
-------------------------

Windows 2000:

  Driver Name: ADPU160M.SYS, ADF6U160.SYS (Ultra160)

  Addressed Issues:

  - With non-disk device such as HP Ultrium Tape drive, the driver
    did not negotiate transfer rate, all subsequent I/O transfers
    occurred as asynchronous speeds.

  - Tape I/O certification test failure fix.

Windows 98/Me:

  Driver Name: ADPU160M.MPD (Ultra160)

  Addressed Issues:

  - Added \Win98_ME folder and an Ultra160 driver from FMS 4.0 SP1a.

-------------------------
Changes in Service Pack 2
-------------------------

NetWare v4.2/5.x:

  Driver Name: All HAM and DDI files (Ultra, Ultra2 and Ultra160)

  Addressed Issues:

  - A completely rewritten OSM layer to remove the redundant CDA
    layer (provides better peformance and maintainability).
  - Provides a single OSM and CHIM source code base for all the
    drivers.
  - Compatibility with NetWare 4.x and 5.x with the proper CSP’s 
    (no support for NetWare 3.x).

-------------------------
Changes in Service Pack 1
-------------------------

Windows 95/98:

  Driver Name: AIC78XX.MPD (Ultra)

  Addressed Issues:

  - Added support for the AHA-3944AUWD host adapter.

Windows NT 4.0:

  Driver Name: AIC78XX.SYS (Ultra)

  Addressed Issues:

  - Fixed blue screen error when accessing a tape device with a bad
    tape cartridge.

  Driver Name: AIC78U2.SYS (Ultra2)

  Addressed Issues:

  - Fixed blue screen error when accessing a tape device with a bad
    tape cartridge.

  - An event on the PCI bus could occur where an Adaptec Ultra2
    host adapter may fail to respond to a PCI GNT# within 16 clock
    cycles. This will only happen when the master and target on the
    PCI bus are doing 64-bit transfers.

  - SCSI bus starvation was occurring when the bus was fully loaded
    with devices. It was found that commands were timing out for 
    devices that had lower SCSI ID values.

  Driver Name: ADPU160M.SYS (Ultra160)

  Addressed Issues:

  - The termination setting for channel B on the AIC-7899 was being
    set incorrectly. The problem is seen only on motherboards in 
    which the AIC-7899 has been designed to control the termination
    for channel A and B. Motherboards that do not use the AIC-7899
    to control the termination of the bus will not see this 
    problem. Adaptec host adapters do not exhibit this problem
    either.

  - With five Ultra160 Adaptec host adapters installed in a system,
    the system will blue screen right before the login screen.

Windows 2000:

  Driver Name: AIC78U2.SYS (Ultra2)

  Addressed Issues:

  - The host adapter's SCSI ID in the registry does not correspond
    to the host adapter's ID set in the BIOS SCSI-Select Utility. 
    Under Windows NT 4, everything behaves correctly. After trying
    various configurations with different SCSI adapters and driver
    versions, it appears that the failing case occurs under Windows
    2000 when no INT13 devices are attached and the SCSI BIOS is
    disabled.

  - An event on the PCI bus could occur where an Adaptec Ultra2
    host adapter may fail to respond to a PCI GNT# within 16 clock 
    cycles.  This will only happen when the master and target on
    the PCI bus are doing 64-bit transfers.

  - SCSI bus starvation was occurring when the bus was fully loaded
    with devices. It was found that commands were timing out for
    devices that had lower SCSI ID values.

  Driver Name: ADPU160M.SYS (Ultra160)

  Addressed Issues:

  - The termination setting for channel B on the AIC-7899 was being
    set incorrectly. The problem is seen only on motherboards in 
    which the AIC-7899 has been designed to control the termination
    for channel A and B. Motherboards that do not use the AIC-7899
    to control the termination of the bus will not see this 
    problem. Adaptec host adapters do not exhibit this problem
    either.

NetWare v4.2/5.x

  Driver Name: AHA2940.HAM (Ultra)

  Addressed Issues:

  - Added support for the AHA-2940UW Pro. Note that this is the
    first FMS release that will contain a HAM driver for the 
    Ultra/Legacy Adaptec products.

  Driver Name: AHA2940.DDI (Ultra)

  Addressed Issues:

  - Updated the driver definition information file for NetWare
    NWPA.

  Driver Name: AIC78U2.HAM (Ultra2)

  Addressed Issues:

  - SAF_TE processor devices are now supported.

  Driver Name: ADPT160M.DDI (Ultra160)

  Addressed Issues:

  - Updated the DDI file to support the Adaptec 29160N and 29160LP
    host adapters in a fresh installation.

  Driver Name: ADPT160M.HAM (Ultra160)

  Addressed Issues:

  - NetWare 5 installation fails installation in a system using RCC
    chipset. The failure only occurs if an Adaptec 39160 host 
    adapter is in a PCI 66 MHz slot.

------------------
Contacting Adaptec
------------------

   A Technical Support Identification (TSID) Number is required for
   Adaptec technical support.
    - The 12-digit TSID can be found on the white barcode-type
      label included inside the box with your product. The TSID
      helps us provide more efficient service by accurately
      identifying your product and support status.
   Support Options
    - Search the Adaptec Support Knowledgebase (ASK) at
      http://ask.adaptec.com for articles, troubleshooting tips,
      and frequently asked questions for your product.
    - For support via Email, submit your question to Adaptec's 
      Technical Support Specialists at http://ask.adaptec.com.
     
   North America
    - Visit our Web site at http://www.adaptec.com.
    - To speak with a Fibre Channel/RAID/External Storage Technical
      Support Specialist, call 1-321-207-2000,
      Hours: Monday-Friday, 3:00 A.M. to 5:00 P.M., PST.
      (Not open on holidays)
    - For Technical Support in all other technologies including 
      SCSI, call 1-408-934-7274,
      Hours: Monday-Friday, 6:00 A.M. to 5:00 P.M., PST.
      (Not open on holidays)
    - For after hours support, call 1-800-416-8066 ($99/call, 
      $149/call on holidays)
    - To order Adaptec products including software and cables, call
      1-800-442-7274 or 1-408-957-7274. You can also visit our 
      online store at http://www.adaptecstore.com

   Europe
    - Visit our Web site at http://www.adaptec-europe.com.
    - English and French: To speak with a Technical Support 
      Specialist, call one of the following numbers:
        - English: +32-2-352-3470
        - French:  +32-2-352-3460
      Hours: Monday-Thursday, 10:00 to 12:30, 13:30 to 17:30 CET 
             Friday, 10:00 to 12:30, 13:30 to 16:30 CET
    - German: To speak with a Technical Support Specialist,
      call +49-89-456-40660
      Hours: Monday-Thursday, 09:30 to 12:30, 13:30 to 16:30 CET
             Friday, 09:30 to 12:30, 13:30 to 15:00 CET
    - To order Adaptec products, including accessories and cables:
        - UK: +0800-96-65-26 or fax +0800-731-02-95
        - Other European countries: +32-11-300-379

   Australia and New Zealand
    - Visit our Web site at http://www.adaptec.com.au.
    - To speak with a Technical Support Specialist, call 
      +612-9416-0698
      Hours: Monday-Friday, 10:00 A.M. to 4:30 P.M., EAT
      (Not open on holidays)

   Japan
    - To speak with a Technical Support Specialist, call 
      +81-3-5308-6120 
      Hours: Monday-Friday, 9:00 a.m. to 12:00 p.m., 1:00 p.m. to
      6:00 p.m. TSC

   Hong Kong and China
    - To speak with a Technical Support Specialist, call 
      +852-2869-7200
      Hours: Monday-Friday, 10:00 to 17:00.
    - Fax Technical Support at +852-2869-7100.

   Singapore
    - To speak with a Technical Support Specialist, call 
      +65-245-7470
      Hours: Monday-Friday, 10:00 to 17:00.
    - Fax Technical Support at +852-2869-7100

-------------------------------------------------------------------

(c) 2002 Adaptec, Inc. All Rights Reserved. No part of this 
publication may be reproduced, stored in a retrieval system, or 
transmitted in any form or by any means, electronic, mechanical, 
photocopying, recording or otherwise, without prior written consent 
of Adaptec, Inc., 691 South Milpitas Blvd., Milpitas, CA 95035.