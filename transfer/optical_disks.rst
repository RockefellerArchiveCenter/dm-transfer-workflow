CDs & DVDs
================================
In general, optical disk images will be forensically imaged using FTK Imager or BitCurator. Forensics images cannot be made for Audio CDs. Please see `Audio CDs`_ for instructions.

The following describes how to create disk images using FTK Imager. FTK
Imager is digital forensics software used to create disk images of
digital media separated either at accessioning, processing or during the
Legacy Digital Media Survey. FTK Imager is a different program than the
Forensic Toolkit, which is usually referred to as FTK.

Imaging with the FTK Imager Command Line
****************************************



Imaging with the FTK Imager GUI
*******************************


1.   Open FTK Imager.


2.  Insert the disk into the CD/DVD drive .

3.   Click **File > Create Disk Image.** Select the source evidence
      type. For CDs and DVDs, select **Logical Drive**.


4.   Select the **Source Drive Location**. This can be a little
      confusing, as the program picks up all connected drives –
      including the one you’re working on. The FRED machine has quite a
      few drives. The CD and DVD drive  is the **G: drive**.
      Click **Finish** to continue.


5.  A dialog box will appear, this time asking where to store the image.
    Click **Add. **

6.  The next screen prompts you to identify where the disk image will be
    stored. All images should be stored on the
    TransferFiles(\\\\raqiq01)(Z:) drive, in a folder that lists the
    accession number of the material. If the accession number isn’t
    available, use the FA number. Complete the fields as listed below.

    a.  **Image Destination Folder:** Save the image on
         TransferFiles(\\\\raqiq01)(Z:). The folder the image is stored
         in follows the naming convention of: [accession
         number]\_[digital media ID] or [FA number]\_[digital media
         number].
        *Example: Z:\\2013\_054\\2013\_054\_DM0000023564 or
         Z:\\FA012\\FA012\_DM0000000759*

    b.  **Image Filename:** The Image Filename is constructed with the
         accession number or FA number followed by the digital media
         number.
        *Example: 2012\_077\_DM0000000001 or FA012\_DM0000000759
         *\

    c. **Image fragment size** and **compression** do not apply to
       DVDs/CDs. The disks are also automatically saved as ISO-type disk
       images. In the source directory you should have four files: a CUE
       file, a cue.csv file (directory listing), and cue.txt file (image
       verification) and an .iso file (the actual image).

7.   Click **Finish** to return to the Create Image dialog window, this
      time with the necessary information completed. Double check the
      **Image Source**, the **Image Destination**, and that both
      **Verify images after they are created** and **Create directory
      listings of all files in the image after they are created** are
      checked. Click **Start** to initiate the imaging process.


8.   A Creating Image dialog window will appear. It will indicate how
      much time has elapsed during the creation of the image.


9.   Once completed, the Status will read **Image created
      successfully**. You will also receive notification that the
      Directory Listing was created successfully. In the image
      destination folder, you will see the image (.iso), the Directory
      Listing file (.csv), and the Verify Results file (.txt). The
      Verify Results Summary contains the same data presented in the
      **Image Summary** area below. This information contains the image
      checksum information needed for the Digital Media database.



10.  In addition to the image checksum, checksums for each of the
      individual files should be generated. To do so, select the
      appropriate level in the file system of the attached disk. In the
      screenshot below, this is the NONAME [FAT32] area on Partition 1.


11. In the vast majority of cases, unpartitioned disks will contain only
    unallocated space, and thus will not contain any files. You can
    navigate the file system hierarchy in FTK Imager to verify that this
    is the case. If you do discover files in unpartitioned space, please
    contact the Head of Digital Programs.


Audio CDs
*********


