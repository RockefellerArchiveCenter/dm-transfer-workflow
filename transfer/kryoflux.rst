Imaging Instructions: 3 1/2 Inch and 5 1/4 Inch Floppy Disks
=================================================

3 1/2 inch and 5 1/4 inch floppy disks need to be imaged using KryoFlux, a USB-based forensic floppy controller and the accompanying software. 
The following describes how to create disk images using KryoFlux.


KryoFlux Hardware Setup
------------------------

Warning: Incorrect setup can damage the KryoFlux and void our warranty. Follow the setup instructions carefully; for more details and images see the `official documentation <http://kryoflux.com/?page=download#docs>`_.

1. On a flat, non-conductive surface, connect the drive to the KryoFlux using the floppy data cable.

2. Connect KryoFlux to the FRED using the USB port in the back of the tower.

3. | Connect the drive to power.
  | Important! Always make the drive – board - connection first,
    then plug the power (PSU & USB). *Power always comes last! You
    are connecting two systems with different grounds, so ground
    (connected via the floppy data cable) must always come first.
    Never ever connect or remove the floppy data cable while the
    drive and / or the board are still powered.*

4. Always unplug and disconnect from mains when not in use! Do not leave unattended!


Imaging with the KryoFlux GUI
-----------------------------

1. Open the **kryoflux-ui.jar – Shortcut** on the desktop.

2. \ Go to **File > Settings**. Navigate to the **Output**
     tab. Copy and paste the path of the directory you created into the
     **Image Path** field. Make sure **Logs** is checked.
	 
3. | On the main KryoFlux screen, enter the name of the image in the
     text field. The image name is constructed with the accession number
     or FA number followed by the digital media ID.
   | *Example: 2012\_077\_DM0000000001 or FA012\_DM0000000759*

4. \ If the disk is Windows formatted, select **<Multiple>**
   from the drop down menu. A new window will appear. Use CTRL+click to
   select **MFM Sector Image** and **KryoFlux stream files,
   preservation**. Click OK.

5. | KryoFlux is separated into three sub-windows. The upper left window
     contains the track gird. Each blog of the grid represents a track
     on the disk’s surface. The upper right window contains the track
     info block, with two more tabs called “Histogram” and “Scatter.”
     The lower part of the window is the control section, where the
     current track, drive controls, and the filename are displayed.
     Below the filename is the format selector, which itself is
     dependent on profiles. The complete last line of the window is the
     status line which displays additional information. During dumping,
     blocks change their color according to the result of the process.
   
   

   a. **Green** – track decoded, no errors found

   b. **Grey** – noise (or unknown encoding scheme)

   c. **Red** – track decoded, error(s) found, reading will be retried

   d. **Yellow** – notifications and warnings, e.g., additional header
      data found

   e. **Glowing** – track is being dumped

   f. To get more information about the result of a certain track, move
      your mouse pointer over it. This will output the result of the
      operation in the status line.

6. Click **Start** and note what time imaging started.

7. Record information in Disk Imaging form in the Digital Media
   Inventory database.

Imaging with the KryoFlux CLI
-----------------------------


Appendices
----------


Likely in Our Collection
~~~~~~~~~~~~~~~~~~~~~~~~

If the disk format is unknown, but is a 3.5” floppy, first try “MFM
Sector Image.” “FM sector image” and “MFM sector image” support
basically any normal disk used for systems that contain a generic FM or
MFM FDC.

For 3.5” disks, if MFM or FM does not work, try FM Sector Information,
CBM DOS sector image, AmigaDOS sector image, Amiga DiskSpare sector
image, Apple DOS 400k/800k sector image, or CBM DOS extended sector
image.


Imaging with the KryoFlux Command Line 
--------------------------------------

Not Likely in Our Collection
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Several of the output options are primarily for computer games and thus
are not likely to be used. These include MFM XFD, Atari 8-bit, Emu
sector image, Emu II sector image, CBM MicroProse sector image, CBM
RapidLok sector image, CBM Datasoft sector image, CBM Vorpal sector
image, CBM V-MAX! sector image, CBM Teque sector image, CBM TDP sector
image, CBM Big Five sector image, CBM OziSoft sector image.

Appendix 1: KryoFlux Errors and Warnings
----------------------------------------

While the Kryoflux is operating, there may be exceptions that trigger
warnings or errors. Confusingly, in the KryoFlux GUI (graphical user
interface—i.e., not the command line) these are all called “errors.” So,
most of what appears to be an “error” is simply a warning. While
warnings are for informational purposes only, errors will have a direct
effect on the operation. Some common warnings and errors:

-  Sector number is not within the allowed range; the sector was NOT
   included in the image. Error.

-  Data checksum could not be verified (might be part of a protection,
   e.g. calculation based on some seed only accessible by the original
   loader); warning only.

-  Slip marks (sector end) found at different positions from their
   expected values; warning only.

-  Header extra data was found. Data is hidden in unused parts of the
   block header. Sector images can't hold such data; warning only. *It
   is likely that this will appear on the beginning tracks; this is
   normal and can be ignored.*

-  Format type/block ID is non-standard; warning only.

-  Sector length is non-standard. If considering it as a protection
   measure it is possible to decode the sector and saving it in the
   image; if not, you'll get another flag saying so; warning only.

-  Sector ignored, sector was found but sector image was not created.
   Reason could be sector having a different size set compared to what
   the image uses; error.

-  Special protection detected which will malform the sector on purpose,
   retry will be suppressed; warning only.

-  Side number found is different from what it should be; warning only.
   *If this warning is appearing for multiple disks, the side selection
   on the drive is broken and a new drive must be used.*

-  Track number found is different from what it should be; warning only.

-  Sector truncated. Sector data is incomplete, decoding stopped. Reason
   is another sync/mark was found in the data block. Almost certainly
   protection that a sector image can't deal with; sector is not
   included in the image; error.

-  Sector offset found is illegal. Sector is still decoded; warning
   only.

.. [1]
   In contrast, the open source option, AFF, is no longer supported by
   its developer and has been discontinued as an option in other imaging
   programs, like Guymager.

Appendix 2: Troubleshooting
---------------------------
If the FRED does not recongize the KryoFlux, it is likely an issue with the driver.   
   Device manager
   
   Ports COM & LPT
   
   Bossa program port
   
   Browse my computer for driver software
   
   let me pick from a list of device drivers
   
   KryoFlux disk system
   http://forum.kryoflux.com/viewtopic.php?t=1038
   

