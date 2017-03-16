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
    

2.  | Click **File > Create Disk Image.** Select the source evidence
      type. This determines if you create a physical image or a logical
      image. For physical media, such as hard drives, thumb drives, and
      floppy disks, select **Physical Drive**. For CDs, DVDs, and data
      received via network transfer (rsync, ftp, Dropbox, email) select
      **Logical Drive**.
    

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
    

4.  | A dialog box will appear, this time asking where to store the
      image. Click **Add.** Before the location of the image file can be
      identified, the type of image file to create needs to be selected.
      We are currently using the E01 file format. While this format is
      proprietary, it is the de facto image format used in law
      enforcement and is well-supported [2]_. Click **Next** to move
      forward.
    

5.  The Evidence Item dialog box will appear. Fill in the boxes as
    described below.

    a. | **Case Number:** Insert the Accession number or FA number of
         the item being imaged in the Case Number field. The accession
         number should be formatted as shown: YEAR ACCESSIONED.
         SEQUENCIAL NUMBER OF ACCESSIONED MATERIAL DURING YEAR
         ACCESSIONED
       | *Example\ **:** 2011.040 or FA012*

    b. | **Evidence Number:** Insert the digital media ID associated
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
         formatted as such: accession title\ any
         information written on the disk.
       PACT
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
         *\ 

6.  The next screen prompts you to identify where the disk image will be
    stored. All images should be stored on the
    **TransferFiles**\ *(\\\\raqiq01*)(\ *Z:*) drive, in a folder that
    lists the accession number of the material. If the accession number
    isn’t available, use the FA number. Complete the fields as listed
    below.

    a. | **Image Destination Folder:** Save the image on
         TransferFiles(\\\\raqiq01)(Z:). The folder the image is stored
         in follows the naming convention of: [accession
         number]\_[digital media ID] or [FA number]\_[digital media
         number].
       | *Example: Z:\\2013\_054\\2013\_054\_DM0000023564 or
         Z:\\FA012\\FA012\_DM0000000759*

    b. | **Image Filename:** The Image Filename is constructed with the
         accession number or FA number followed by the digital media
         number.
       | *Example: 2012\_077\_DM0000000001 or FA012\_DM0000000759
         *\ 

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
    

8.  | A Creating Image dialog window will appear. It will indicate how
      much time has elapsed during the creation of the image.
    

9.  | Once completed, the Status will read **Image created
      successfully**. You will also receive notification that the
      Directory Listing was created successfully. In the image
      destination folder, you will see the image (.E01), the Directory
      Listing file (.csv), and the Verify Results file (.txt). The
      Verify Results Summary contains the same data presented in the
      Image Summary area below. This information contains the image
      checksum information needed for the Digital Media database.
    
    

10. | In addition to the image checksum, checksums for each of the
      individual files should be generated. To do so, select the
      appropriate level in the file system of the attached disk. In the
      screenshot below, this is the NONAME [FAT32] area on Partition 1.
    

11. In the vast majority of cases, unpartitioned disks will contain only
    unallocated space, and thus will not contain any files. You can
    navigate the file system hierarchy in FTK Imager to verify that this
    is the case. If you do discover files in unpartitioned space, please
    contact the Head of Digital Programs.

12. | From the **File** menu, select **Export File Hash List**. This
      option will only appear in areas where hashes (ie. checksums) can
      be generated. Save the file in the same directory as the image and
      the other files that were generated during imaging. Name the file
      with the accession number and digital media ID as used before,
      appending “\_hash” to the end of the file name.
    | *Example: 2012\_077\_DM0000000001\_hash or
      FA012\_DM0000000759\_hash*

13. Make sure to safely eject the hardware you were imaging. Failure to
    do so can result in irreparable damage to the media.
	
Further Information
~~~~~~~~~~~~~~~~~~~

A detailed Manual for FTK Imager is available as a PDF. It is located on
the M drive or through this link on the web.

M:\\Digital
Programs\\Digital\_Media\_Tracking\\digitalMedia\_Documentation\\Imaging\\ImagerUsersGuide.pdf

http://ad-pdf.s3.amazonaws.com/ImagerUsersGuide.pdf
