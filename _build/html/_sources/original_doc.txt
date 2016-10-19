Overview
========

Disk images are single files containing the complete content and
structure representing a data storage medium or device. There are
different types of images. Forensic images perfectly replicate the
structure and contents of a storage device, and allow the viewing of
deleted files and slackspace (i.e, the unused space in a disk cluster).
Logical images [AD1] are not true forensic images; and do not include
file slackspace. In general\ *,* all physical media is imaged as a
physical image, and all digital materials received via a network
transfer will be logically imaged. Variations from this policy will be
considered on a case-by-case basis.

At this point in time, disk images are created in-house for optical
disks (DVDs and CDs), external hard drives, USB Flash drives, 5.25-inch
floppy disks and 3.5-inch floppy disks (recently dated disks that are
PC-formatted). We do not have the capacity to image Bernoulli disks, Jaz
disks, and 8-inch floppy disks. Please notify the Head of Digital
Programs if you encounter media not detailed in either list above.

The information entered into these free text fields can be found in the
Digital Media Inventory database. These instructions can be applied to
all disk images when using FTK Imager for capture.

The hardware used to create images will vary depending on the type of
digital media. Optical disks (DVDs and CDs), external hard drives, and
USB Flash drives will be imaged using the FRED.

All Formats: Basic Set-Up
=========================

Location of media
-----------------

Items that are ready to be imaged are located on the digital media
shelves in the 3\ :sup:`rd` floor library and Vault 105. The shelves in
the library are labeled “DIGITAL MEDIA DISK IMAGING WORKFLOW SHELVES.”
The digital media is housed in Paige or Hollinger boxes that are
labeled:

ROCKEFELLER ARCHIVE CENTER DIGITAL MEDIA

-  Digital media number range For example, DM0000000001-DM0000000045

-  Accession number For example, 2012.069

-  Box number For example, BOX 1

Destination Folders
-------------------

Newly created disk images are stored on the transfer server (Z or V
drive). On the Z drive, there is one folder per accession, and within
these folders, one folder per digital media number.

Example:

+----------------------------+
| /2015\_123                 |
|                            |
| /2015\_123\_DM0000001234   |
|                            |
| /2015\_123\_DM0000001235   |
|                            |
| /2015\_123\_DM0000001236   |
+============================+
+----------------------------+

It is much faster to create beforehand the folders where the disk images
will go. This can be done quickly using the command line.

1. From the Start menu, open **Cygwin64 Terminal**.

2. Type cd ../../cygdrive/z and hit enter.

3. If a folder for this accession does not yet exist, type mkdir -p
   2001\_001/2001\_001\_DM000000{4001,4009,4010,4012,4050}. Replace the
   appropriate accession numbers and digital media ID numbers. If this
   accession already has a folder, type the same thing without –p.

4. If the digital media ID numbers are sequential, you can use “..” to
   create directories within a range: mkdir -p
   2001\_001/2001\_001\_DM000000{4001..4050}

5. You can view the folders you created in Windows Explorer.

Time statistics
---------------

Record the time it takes from beginning to end of the imaging process
for each disk image in the Disk imaging time tracking table in the
Digital Media inventory database.

Image time varies greatly depending on the data capacity of the disk
being imaged. For example, floppy disks may take a couple minutes to
image while several-gigabyte hard drives may take much longer.

Digital media inventory 
------------------------

Information about each disk imaging attempt is recorded in the **Digital
Media Inventory database**, which is located in *M:\\Digital
Programs\\Digital Preservation Services\\Digital Media
Tracking\\Database*.

1. In the database, open the **Disk Imaging Form**.\ **
   **\ |image0|

For the item you are about to image, record:

a. | **Disk image filename**: The disk image filename of the digital
     media item imaged. The filename is composed of the accession number
     or FA number followed by the digital media ID.
   | *Example: 2012\_069\_DM0000001354.img*

b. | **Digital Media ID:** successive 10-digital number with the prefix
     DM. Each item receives a digital media ID. If a digital media
     resource has four disks that comprise its whole then each disk
     would be assigned a digital media ID.
   | *Example: DM0000001354*

c. **Date Imaged:** Date the imaging took place.\ **
   **\ *Example: 10/15/2014*

d. | **Examiner:** Record the name of the person imaging the media.
   | *Example: Bonnie Gordon*

e. | **Interface:** The interface used as point of access.
   | *Examples: USB (for USB devices); FC5025; Kryoflux *

f. | **Disk imaging software:** Select the software tool used to image
     the digital media
   | *Example: Kryoflux*

g. | **Disk image format:** Select the disk image format used to create
     a disk image.
   | *Example: E01*

Imaging Instructions: Zip Disks
===============================

The following describes how to create disk images using **FTK Imager**.
FTK Imager is digital forensics software used to create disk images of
digital media separated either at accessioning, processing or during the
Legacy Digital Media Survey. FTK Imager is a different program than the
Forensic Toolkit, which is usually referred to as FTK.

External hard drives and USB Flash drives will be imaged using the FRED.
External hard drives and USB Flash drives need to be connected to the
Tableau UltraBay write blocker on the FRED, and the Tableau UltraBay
needs to be turned ON. Two green lights should appear – the Power light
and the WrtBlk light. Do not plug in your device unless these lights are
on.

1.  Turn on FRED write blocker

2.  Connect zip drive to USB port in write blocker area

3.  | Open FTK Imager. It looks like this on the FRED toolbar:
    | |image1|

4.  | Click **File > Create Disk Image.** Select the source evidence
      type. This determines if you create a physical image or a logical
      image. For physical media, such as hard drives, thumb drives, and
      floppy disks, select **Physical Drive**. For CDs, DVDs, and data
      received via network transfer (rsync, ftp, Dropbox, email) select
      **Logical Drive**.
    | |image2|

5.  | Select the **Source Drive Location**. This can be a little
      confusing, as the program picks up all connected drives –
      including the one you’re working on. The FRED machine has quite a
      few drives. You can distinguish between them by using the data
      size listed in the dialog box. For example, two of the drives are
      listed at 2000GB and 7999GB, respectively. You can also disregard
      the WIBU Codemeter Stick USB device, which is a USB key to run the
      Forensic Toolkit. In the screenshot below, the last drive,
      “Generic Flash Di USB Device (4GB USB)” is the drive we want to
      image. Click **Finish** to continue
    | |image3|

6.  | A dialog box will appear, this time asking where to store the
      image. Click **Add.** Before the location of the image file can be
      identified, the type of image file to create needs to be selected.
      We are currently using the E01 file format. While this format is
      proprietary, it is the de facto image format used in law
      enforcement and is well-supported [1]_. Click **Next** to move
      forward.
    | |image4|

7.  The Evidence Item dialog box will appear. Fill in the boxes as
    described below.

    a. | **Case Number:** Insert the Accession number or FA number of
         the item being imaged in the Case Number field. The accession
         number should be formatted as shown: YEAR ACCESSIONED.
         SEQUENTIAL NUMBER OF ACCESSIONED MATERIAL DURING YEAR
         ACCESSIONED
       | *Example\ **:** 2011.040 or FA012*

    b. | **Evidence Number:** Insert the Digital Media number associated
         with the item into the Evidence Number field. This is a
         successive 10-digit number with DM as a prefix. It is tracked
         in the Digital Media inventory.
       | *Example: DM0000000001*

    c. | **Unique Description:** This field contains the Accession Title
         from *the Special Formats Tracking Form*, the name of the disk,
         and any information written on the disk is captured in the
         Unique Description field. Each instance of information should
         be separated by a pipe character “\|” to clearly delinate the
         separate data fields. This information is also captured in the
         Digital Media Inventory database. The information should be
         formatted as such: accession title\|name of the disk\| any
         information written on the disk.
       | *Example\ **:** Rockefeller Foundation records, Grants\|PACT
         Report YZ, Alutiiq Museum Kodiak, AK\|Office Depot CD-R
         Recordable 80 min 700 MB. *

    d. | **Examiner:** The Imager name is captured in the Examiner
         field. The Imager name should be formatted with the first and
         last name of the Imager.
       | *Example: Laura Montgomery*

    e. | **Notes:
         **\ Use this field to capture additional information that is
         not captured elsewhere, such as information on the disk
         enclosure or signs of physical damage.
       | *Example: CD case has sticker with “200100184” written in red
         ink. There are surface scratches on disk.
         *\ |image5|

8.  The next screen prompts you to identify where the disk image will be
    stored. All images should be stored on the
    **TransferFiles**\ *(\\\\raqiq01*)(\ *Z:*) drive, in a folder that
    lists the accession number of the material. If the accession number
    isn’t available, use the FA number. Complete the fields as listed
    below.

    a. | **Image Destination Folder:** Save the image on
         TransferFiles(\\\\raqiq01)(Z:). The folder the image is stored
         in follows the naming convention of: [accession
         number]\_[digital media number] or [FA number]\_[digital media
         number].
       | *Example: Z:\\2013\_054\\2013\_054\_DM0000023564 or
         Z:\\FA012\\FA012\_DM0000000759*

    b. | **Image Filename:** The Image Filename is constructed with the
         accession number or FA number followed by the digital media
         number.
       | *Example: 2012\_077\_DM0000000001 or FA012\_DM0000000759
         *\ |image6|

    c. **Image Fragment Size:** The Image Fragment Size should be set to
       0 (zero).

    d. **Compression:** The Compression level should be set to 0 (zero).

    e. **Use AD Encryption:** Leave this unchecked.

9.  | Click **Finish** to return to the Create Image dialog window, this
      time with the necessary information completed. Double check the
      **Image Source**, the **Image Destination**, and that both
      **Verify images after they are created** and **Create directory
      listings of all files in the image after they are created** are
      checked. Click **Start** to initiate the imaging process.
    | |image7|

10. | A Creating Image dialog window will appear. It will indicate how
      much time has elapsed during the creation of the image.
    | |image8|

11. | Once completed, the Status will read **Image created
      successfully**. You will also receive notification that the
      Directory Listing was created successfully. In the image
      destination folder, you will see the image (.E01), the Directory
      Listing file (.csv), and the Verify Results file (.txt). The
      Verify Results Summary contains the same data presented in the
      Image Summary area below. This information contains the image
      checksum information needed for the Digital Media database.
    | |image9|
    | |image10|

12. | In addition to the image checksum, checksums for each of the
      individual files should be generated. To do so, select the
      appropriate level in the file system of the attached disk. In the
      screenshot below, this is the NONAME [FAT32] area on Partition 1.
    | |image11|

13. In the vast majority of cases, unpartitioned disks will contain only
    unallocated space, and thus will not contain any files. You can
    navigate the file system hierarchy in FTK Imager to verify that this
    is the case. If you do discover files in unpartitioned space, please
    contact the Head of Digital Programs.

14. | From the **File** menu, select **Export File Hash List**. This
      option will only appear in areas where hashes (ie. checksums) can
      be generated. Save the file in the same directory as the image and
      the other files that were generated during imaging. Name the file
      with the accession number and digital media number as used before,
      appending “\_hash” to the end of the file name.
    | *Example: 2012\_077\_DM0000000001\_hash or
      FA012\_DM0000000759\_hash*

15. Make sure to safely eject the hardware you were imaging. Failure to
    do so can result in irreparable damage to the media.

16. Notify the appropriate D-Team member that the image(s) are ready to
    be scanned for viruses.

Imaging Instructions: Hard Drives & USB Flash Drives
====================================================

The following describes how to create disk images using **FTK Imager**.
FTK Imager is digital forensics software used to create disk images of
digital media separated either at accessioning, processing or during the
Legacy Digital Media Survey. FTK Imager is a different program than the
Forensic Toolkit, which is usually referred to as FTK.

External hard drives and USB Flash drives will be imaged using the FRED.
External hard drives and USB Flash drives need to be connected to the
Tableau UltraBay write blocker on the FRED, and the Tableau UltraBay
needs to be turned ON. Two green lights should appear – the Power light
and the WrtBlk light. Do not plug in your device unless these lights are
on.

1.  | Open FTK Imager. It looks like this on the FRED toolbar:
    | |image12|

2.  | Click **File > Create Disk Image.** Select the source evidence
      type. This determines if you create a physical image or a logical
      image. For physical media, such as hard drives, thumb drives, and
      floppy disks, select **Physical Drive**. For CDs, DVDs, and data
      received via network transfer (rsync, ftp, Dropbox, email) select
      **Logical Drive**.
    | |image13|

3.  | Select the **Source Drive Location**. This can be a little
      confusing, as the program picks up all connected drives –
      including the one you’re working on. The FRED machine has quite a
      few drives. You can distinguish between them by using the data
      size listed in the dialog box. For example, two of the drives are
      listed at 2000GB and 7999GB, respectively. You can also disregard
      the WIBU Codemeter Stick USB device, which is a USB key to run the
      Forensic Toolkit. In the screenshot below, the last drive,
      “Generic Flash Di USB Device (4GB USB)” is the drive we want to
      image. Click **Finish** to continue
    | |image14|

4.  | A dialog box will appear, this time asking where to store the
      image. Click **Add.** Before the location of the image file can be
      identified, the type of image file to create needs to be selected.
      We are currently using the E01 file format. While this format is
      proprietary, it is the de facto image format used in law
      enforcement and is well-supported [2]_. Click **Next** to move
      forward.
    | |image15|

5.  The Evidence Item dialog box will appear. Fill in the boxes as
    described below.

    a. | **Case Number:** Insert the Accession number or FA number of
         the item being imaged in the Case Number field. The accession
         number should be formatted as shown: YEAR ACCESSIONED.
         SEQUENCIAL NUMBER OF ACCESSIONED MATERIAL DURING YEAR
         ACCESSIONED
       | *Example\ **:** 2011.040 or FA012*

    b. | **Evidence Number:** Insert the Digital Media number associated
         with the item into the Evidence Number field. This is a
         successive 10-digit number with DM as a prefix. It is tracked
         in the Digital Media inventory.
       | *Example: DM0000000001*

    c. | **Unique Description:** This field contains the Accession Title
         from *the Special Formats Tracking Form*, the name of the disk,
         and any information written on the disk is captured in the
         Unique Description field. Each instance of information should
         be separated by a pipe character “\|” to clearly delinate the
         separate data fields. This information is also captured in the
         Digital Media Inventory database. The information should be
         formatted as such: accession title\|name of the disk\| any
         information written on the disk.
       | *Example\ **:** Rockefeller Foundation records, Grants\|PACT
         Report YZ, Alutiiq Museum Kodiak, AK\|Office Depot CD-R
         Recordable 80 min 700 MB. *

    d. | **Examiner:** The Imager name is captured in the Examiner
         field. The Imager name should be formatted with the first and
         last name of the Imager.
       | *Example: Laura Montgomery*

    e. | **Notes:
         **\ Use this field to capture additional information that is
         not captured elsewhere, such as information on the disk
         enclosure or signs of physical damage.
       | *Example: CD case has sticker with “200100184” written in red
         ink. There are surface scratches on disk.
         *\ |image16|

6.  The next screen prompts you to identify where the disk image will be
    stored. All images should be stored on the
    **TransferFiles**\ *(\\\\raqiq01*)(\ *Z:*) drive, in a folder that
    lists the accession number of the material. If the accession number
    isn’t available, use the FA number. Complete the fields as listed
    below.

    a. | **Image Destination Folder:** Save the image on
         TransferFiles(\\\\raqiq01)(Z:). The folder the image is stored
         in follows the naming convention of: [accession
         number]\_[digital media number] or [FA number]\_[digital media
         number].
       | *Example: Z:\\2013\_054\\2013\_054\_DM0000023564 or
         Z:\\FA012\\FA012\_DM0000000759*

    b. | **Image Filename:** The Image Filename is constructed with the
         accession number or FA number followed by the digital media
         number.
       | *Example: 2012\_077\_DM0000000001 or FA012\_DM0000000759
         *\ |image17|

    c. **Image Fragment Size:** The Image Fragment Size should be set to
       0 (zero).

    d. **Compression:** The Compression level should be set to 0 (zero).

    e. **Use AD Encryption:** Leave this unchecked.

7.  | Click **Finish** to return to the Create Image dialog window, this
      time with the necessary information completed. Double check the
      **Image Source**, the **Image Destination**, and that both
      **Verify images after they are created** and **Create directory
      listings of all files in the image after they are created** are
      checked. Click **Start** to initiate the imaging process.
    | |image18|

8.  | A Creating Image dialog window will appear. It will indicate how
      much time has elapsed during the creation of the image.
    | |image19|

9.  | Once completed, the Status will read **Image created
      successfully**. You will also receive notification that the
      Directory Listing was created successfully. In the image
      destination folder, you will see the image (.E01), the Directory
      Listing file (.csv), and the Verify Results file (.txt). The
      Verify Results Summary contains the same data presented in the
      Image Summary area below. This information contains the image
      checksum information needed for the Digital Media database.
    | |image20|
    | |image21|

10. | In addition to the image checksum, checksums for each of the
      individual files should be generated. To do so, select the
      appropriate level in the file system of the attached disk. In the
      screenshot below, this is the NONAME [FAT32] area on Partition 1.
    | |image22|

11. In the vast majority of cases, unpartitioned disks will contain only
    unallocated space, and thus will not contain any files. You can
    navigate the file system hierarchy in FTK Imager to verify that this
    is the case. If you do discover files in unpartitioned space, please
    contact the Head of Digital Programs.

12. | From the **File** menu, select **Export File Hash List**. This
      option will only appear in areas where hashes (ie. checksums) can
      be generated. Save the file in the same directory as the image and
      the other files that were generated during imaging. Name the file
      with the accession number and digital media number as used before,
      appending “\_hash” to the end of the file name.
    | *Example: 2012\_077\_DM0000000001\_hash or
      FA012\_DM0000000759\_hash*

13. Make sure to safely eject the hardware you were imaging. Failure to
    do so can result in irreparable damage to the media.

14. Notify the appropriate D-Team member that the image(s) are ready to
    be scanned for viruses.

Further Information
~~~~~~~~~~~~~~~~~~~

A detailed Manual for FTK Imager is available as a PDF. It is located on
the M drive or through this link on the web.

M:\\Digital
Programs\\Digital\_Media\_Tracking\\digitalMedia\_Documentation\\Imaging\\ImagerUsersGuide.pdf

http://ad-pdf.s3.amazonaws.com/ImagerUsersGuide.pdf

Imaging Instructions: CDs & DVDs
================================

The following describes how to create disk images using FTK Imager. FTK
Imager is digital forensics software used to create disk images of
digital media separated either at accessioning, processing or during the
Legacy Digital Media Survey. FTK Imager is a different program than the
Forensic Toolkit, which is usually referred to as FTK.

1.  | Open FTK Imager. It looks like this on the FRED toolbar:
    | |image23|

2.  Insert the disk into the CD/DVD drive on the FRED.

3.  | Click **File > Create Disk Image.** Select the source evidence
      type. For CDs and DVDs, select **Logical Drive**.
    | |image24|

4.  | Select the **Source Drive Location**. This can be a little
      confusing, as the program picks up all connected drives –
      including the one you’re working on. The FRED machine has quite a
      few drives. The CD and DVD drive on the FRED is the **G: drive**.
      Click **Finish** to continue.
    | |image25|

5.  A dialog box will appear, this time asking where to store the image.
    Click **Add. **

6.  The next screen prompts you to identify where the disk image will be
    stored. All images should be stored on the
    TransferFiles(\\\\raqiq01)(Z:) drive, in a folder that lists the
    accession number of the material. If the accession number isn’t
    available, use the FA number. Complete the fields as listed below.

    a. | **Image Destination Folder:** Save the image on
         TransferFiles(\\\\raqiq01)(Z:). The folder the image is stored
         in follows the naming convention of: [accession
         number]\_[digital media number] or [FA number]\_[digital media
         number].
       | *Example: Z:\\2013\_054\\2013\_054\_DM0000023564 or
         Z:\\FA012\\FA012\_DM0000000759*

    b. | **Image Filename:** The Image Filename is constructed with the
         accession number or FA number followed by the digital media
         number.
       | *Example: 2012\_077\_DM0000000001 or FA012\_DM0000000759
         *\ |image26|

    c. **Image fragment size** and **compression** do not apply to
       DVDs/CDs. The disks are also automatically saved as ISO-type disk
       images. In the source directory you should have four files: a CUE
       file, a cue.csv file (directory listing), and cue.txt file (image
       verification) and an .iso file (the actual image).

7.  | Click **Finish** to return to the Create Image dialog window, this
      time with the necessary information completed. Double check the
      **Image Source**, the **Image Destination**, and that both
      **Verify images after they are created** and **Create directory
      listings of all files in the image after they are created** are
      checked. Click **Start** to initiate the imaging process.
    | |image27|

8.  | A Creating Image dialog window will appear. It will indicate how
      much time has elapsed during the creation of the image.
    | |image28|

9.  | Once completed, the Status will read **Image created
      successfully**. You will also receive notification that the
      Directory Listing was created successfully. In the image
      destination folder, you will see the image (.iso), the Directory
      Listing file (.csv), and the Verify Results file (.txt). The
      Verify Results Summary contains the same data presented in the
      **Image Summary** area below. This information contains the image
      checksum information needed for the Digital Media database.
    | |image29|
    | |image30|

10. | In addition to the image checksum, checksums for each of the
      individual files should be generated. To do so, select the
      appropriate level in the file system of the attached disk. In the
      screenshot below, this is the NONAME [FAT32] area on Partition 1.
    | |image31|

11. In the vast majority of cases, unpartitioned disks will contain only
    unallocated space, and thus will not contain any files. You can
    navigate the file system hierarchy in FTK Imager to verify that this
    is the case. If you do discover files in unpartitioned space, please
    contact the Head of Digital Programs.

12. | From the **File** menu, select **Export File Hash List**. This
      option will only appear in areas where hashes (ie. checksums) can
      be generated. Save the file in the same directory as the image and
      the other files that were generated during imaging. Name the file
      with the accession number and digital media number as used before,
      appending “\_hash” to the end of the file name.
    | *Example: 2012\_077\_DM0000000001\_hash or
      FA012\_DM0000000759\_hash*

13. Make sure to safely eject the hardware you were imaging. Failure to
    do so can result in irreparable damage to the media.

14. Notify the appropriate D-Team member that the image(s) are ready to
    be scanned for viruses.

Imaging Instructions: 3.5” and 5.25” Floppy Disks
=================================================

The following describes how to create disk images using KryoFlux.
KryoFlux is software and hardware used to create disk images of 3.5” and
5.25” floppy disks.

1. In the Disk Imaging Form, record “KryoFlux” as the interface and disk
   imaging software, and select the drive that you are using from the
   drop-down list.

2. Set up the hardware.

   a. Connect the drive to the KryoFlux

   b. Connect KryoFlux to the FRED using the USB port in the back.

   c. | Connect the drive to power.
      | Important! Always make the drive – board - connection first,
        then plug the power (PSU & USB). *Power always comes last! You
        are connecting two systems with different grounds, so ground
        (connected via the floppy data cable) must always come first.
        Never ever connect or remove the floppy data cable while the
        drive and / or the board are still powered.*

   d. Always unplug and disconnect from mains when not in use! Do not
      leave unattended!

3. Open the **kryoflux-ui.jar – Shortcut** on the desktop.

4. | |image32|\ Go to **File > Settings**. Navigate to the **Output**
     tab. Copy and paste the path of the directory you created into the
     **Image Path** field. Make sure **Logs** is checked.
   | *Example: Z:\\2013\_054\\2013\_054\_DM0000023564 or
     Z:\\FA012\\FA012\_DM0000000759
     *

5. | On the main KryoFlux screen, enter the name of the image in the
     text field. The image name is constructed with the accession number
     or FA number followed by the digital media number.
   | *Example: 2012\_077\_DM0000000001 or FA012\_DM0000000759*

6. |image33|\ If the disk is Windows formatted, select **<Multiple>**
   from the drop down menu. A new window will appear. Use CTRL+click to
   select **MFM Sector Image** and **KryoFlux stream files,
   preservation**. Click OK.

7. | KryoFlux is separated into three sub-windows. The upper left window
     contains the track gird. Each blog of the grid represents a track
     on the disk’s surface. The upper right window contains the track
     info block, with two more tabs called “Histogram” and “Scatter.”
     The lower part of the window is the control section, where the
     current track, drive controls, and the filename are displayed.
     Below the filename is the format selector, which itself is
     dependent on profiles. The complete last line of the window is the
     status line which displays additional information. During dumping,
     blocks change their color according to the result of the process.
   | |image34|
   | |image35|

   a. **Green** – track decoded, no errors found

   b. **Grey** – noise (or unknown encoding scheme)

   c. **Red** – track decoded, error(s) found, reading will be retried

   d. **Yellow** – notifications and warnings, e.g., additional header
      data found

   e. **Glowing** – track is being dumped

   f. To get more information about the result of a certain track, move
      your mouse pointer over it. This will output the result of the
      operation in the status line.

8. Click **Start** and note what time imaging started.

9. Record information in Disk Imaging form in the Digital Media
   Inventory database.

Appendices
==========

Appendix 1: KryoFlux Outputs
----------------------------

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

The following is a table of output options, the computer systems and
drives the disks would have been used with, the size of the disk, and
the approximate production dates of the disks.

+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| Options                            | Used with                                                                 | Disk size      | Production Dates   |
+====================================+===========================================================================+================+====================+
| FM sector image                    | BBC Micro, PC-8801, Atari 8-bit                                           | 5.25”          | Early 1980s        |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| FM XFD, Atari 8-bit                | Atari 8-bit bit-negated images                                            | 5.25”          | 1979-1992?         |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| MFM sector image                   | 1.44MB Macintosh disks; Commodore 128; Amiga, Atari ST, PC, many others   | 3.5” & 5.25”   | 1970-2000s         |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| AmigaDOS sector image              | Amiga                                                                     | 3.5” & 5.25”   | 1985-1992          |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| CBM DOS sector image               | Commodore's 8-bit computers                                               | 3.5” & 5.25”   | 1981-1994          |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| Apple DOS 3.2 sector image         | Apple DOS 3.2                                                             | 5.25”          | 1978-1983          |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| Apple DOS 3.3+ sector image        | Apple DOS 3.3, ProDOS                                                     | 5.25”          | 1978-1983          |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| DSK, DOS 3.3 interleave            | Apple DOS 3.3 interleave order images                                     | 5.25”          | 1978-1983          |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| Apple DOS 400k/800k sector image   | Macintosh, including Macintosh 128k, Apple II                             | 3.5”           | 1984-1987          |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| Amiga DiskSpare sector image       | Amiga                                                                     | ?              | 1985-1992?         |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| CBM GCR image                      | Commodore 1541 drive for Commodore 64                                     | 5.25”          | 1982-1988          |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+
| CBM DOS extended sector image      | Commodore's 8-bit computers                                               | 3.5” & 5.25”   | 1981-1994          |
+------------------------------------+---------------------------------------------------------------------------+----------------+--------------------+

Not Likely in Our Collection
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Several of the output options are primarily for computer games and thus
are not likely to be used. These include MFM XFD, Atari 8-bit, Emu
sector image, Emu II sector image, CBM MicroProse sector image, CBM
RapidLok sector image, CBM Datasoft sector image, CBM Vorpal sector
image, CBM V-MAX! sector image, CBM Teque sector image, CBM TDP sector
image, CBM Big Five sector image, CBM OziSoft sector image.

Appendix 2: KryoFlux Errors and Warnings
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

Appendix 3: Hardware & Setup Images
-----------------------------------

|image36|

|image37|

|image38|

|image39|

Appendix 4: Physical Problems, Cleaning, & Repair
-------------------------------------------------

.. [1]
   In contrast, the open source option, AFF, is no longer supported by
   its developer and has been discontinued as an option in other imaging
   programs, like Guymager.

.. [2]
   In contrast, the open source option, AFF, is no longer supported by
   its developer and has been discontinued as an option in other imaging
   programs, like Guymager.

.. |image0| image:: media/image1.png
   :width: 3.84709in
   :height: 3.39105in
.. |image1| image:: media/image2.png
   :width: 0.64340in
   :height: 0.41509in
.. |image2| image:: media/image3.png
   :width: 4.27510in
   :height: 3.40302in
.. |image3| image:: media/image4.png
   :width: 4.13417in
   :height: 3.27250in
.. |image4| image:: media/image5.png
   :width: 4.35417in
   :height: 3.07292in
.. |image5| image:: media/image6.jpeg
   :width: 4.79167in
   :height: 3.56108in
.. |image6| image:: media/image7.png
   :width: 4.69792in
   :height: 3.47917in
.. |image7| image:: media/image8.png
   :width: 3.47917in
   :height: 3.12892in
.. |image8| image:: media/image9.png
   :width: 3.90938in
   :height: 2.82188in
.. |image9| image:: media/image10.png
   :width: 4.34375in
   :height: 3.13542in
.. |image10| image:: media/image11.png
   :width: 5.35010in
   :height: 3.00943in
.. |image11| image:: media/image12.png
   :width: 5.68868in
   :height: 1.59030in
.. |image12| image:: media/image2.png
   :width: 0.64340in
   :height: 0.41509in
.. |image13| image:: media/image3.png
   :width: 4.27510in
   :height: 3.40302in
.. |image14| image:: media/image4.png
   :width: 4.13417in
   :height: 3.27250in
.. |image15| image:: media/image5.png
   :width: 4.35417in
   :height: 3.07292in
.. |image16| image:: media/image6.jpeg
   :width: 4.79167in
   :height: 3.56108in
.. |image17| image:: media/image7.png
   :width: 4.69792in
   :height: 3.47917in
.. |image18| image:: media/image8.png
   :width: 3.47917in
   :height: 3.12892in
.. |image19| image:: media/image9.png
   :width: 3.90938in
   :height: 2.82188in
.. |image20| image:: media/image10.png
   :width: 4.34375in
   :height: 3.13542in
.. |image21| image:: media/image11.png
   :width: 5.35010in
   :height: 3.00943in
.. |image22| image:: media/image12.png
   :width: 5.68868in
   :height: 1.59030in
.. |image23| image:: media/image2.png
   :width: 0.64340in
   :height: 0.41509in
.. |image24| image:: media/image13.png
   :width: 3.98860in
   :height: 3.15727in
.. |image25| image:: media/image14.png
   :width: 3.98860in
   :height: 3.15727in
.. |image26| image:: media/image7.png
   :width: 4.33115in
   :height: 3.20755in
.. |image27| image:: media/image15.png
   :width: 4.14406in
   :height: 3.72687in
.. |image28| image:: media/image16.png
   :width: 3.90938in
   :height: 2.82187in
.. |image29| image:: media/image10.png
   :width: 4.34375in
   :height: 3.13542in
.. |image30| image:: media/image17.png
   :width: 5.87002in
   :height: 3.30189in
.. |image31| image:: media/image12.png
   :width: 6.49097in
   :height: 1.81458in
.. |image32| image:: media/image18.png
   :width: 4.46528in
   :height: 1.53889in
.. |image33| image:: media/image19.png
   :width: 1.79861in
   :height: 1.79861in
.. |image34| image:: media/image20.png
   :width: 3.83333in
   :height: 2.57492in
.. |image35| image:: media/image21.png
   :width: 3.88194in
   :height: 2.60757in
.. |image36| image:: media/image22.png
   :width: 6.95833in
   :height: 4.25232in
.. |image37| image:: media/image23.jpeg
   :width: 6.39583in
   :height: 3.60417in
.. |image38| image:: media/image24.jpeg
   :width: 5.39583in
   :height: 2.92708in
.. |image39| image:: media/image25.jpeg
   :width: 4.16667in
   :height: 3.12500in
