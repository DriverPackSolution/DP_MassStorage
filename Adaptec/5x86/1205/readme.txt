
Adaptec's SATAConnect Readme
For Adaptec's ASH-1205SA Host Adapter
Supporting Windows 98SE, Windows Me, Windows 2000, and Windows XP
=======================================================

The default location of the expanded files are on your system disk 
in the following folder: \adaptec\ash1205sa\.


Documentation
=============
Much of our documentation is released in PDF format.  To view these 
Documents you must have Adobe Acrobat Reader version 4 or later 
installed on your system. You can find a copy of this software on the 
CD shipped with your product or you can download the latest version 
from <www.adobe.com>.


Notes
=====
- Please refer to the User's Guide on the CD and the Adaptec Support 
  Knowledgebase (ASK) at <ask.adaptec.com> for general troubleshooting
  tips.

- Newer versions of the BIOS and drivers will be posted on the Adaptec
  Web site as they are developed. For maximum adapter performance and
  functionality, please update to the latest drivers as they become
  available. Go to <www.adaptec.com/support> for more information.

- Please check your device manufacturer's Web site for the latest 
  updates to their software.

- Although SATA technology supports hot-plugging, you should never
  attempt to connect or disconnect internal SATA devices while your
  computer is powered on. Hot-plugging internal SATA devices may
  cause electic shock and/or damage to your computer.

- While some ATAPI devices connected through a PATA-to-SATA bridge 
  may function properly, they have not been tested completely to ensure 
  full compatibility.



Installation Procedure
======================
Please refer to the User's Guide on the CD for instructions on how to 
install the SATAConnect ASH-1205SA card and its associated drivers.


Known Issues
==========
If you have Western Digital WD300 PATA (Parallel ATA) hard disk
connected to  the ASH-1205SA by a PATA-to-SATA bridge, the ASH-1205SA
BIOS may not recognize the device and will display "Drive not found" 
during POST (Power-on Self Test). However when POST is complete the 
device will be accessible when the system completes booting and will 
appear in the device manager.

In Windows 98SE and Windows Me, identical devices connected to the 
ASH-1205SA card will appear as a single device entry in the Device 
Manager. However, both devices will be accessible and will function 
normally.

In Windows Me, the system will not awaken from suspend (S1) sleep if 
a device is connected to the card. If you encounter this problem you
will need to reboot your system. To avoid this problem disable sleep 
in the control panel.

If you have Parallel ATA 33 or Parallel ATA 66 devices connected to 
the ASH-1205SA by a Marvell PATA-to-SATA bridge, the system may lock up 
during the boot process or could take up to five (5) minutes to boot.


