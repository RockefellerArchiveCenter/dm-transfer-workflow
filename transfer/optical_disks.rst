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

1. Insert the disk in the drive.

2. In the command prompt, run the script.


Imaging with the FTK Imager GUI
*******************************


1.	Open FTK Imager.

2.	Insert the disk into the CD/DVD drive .

3.	Click File > Create Disk Image. Select Logical Drive as the source evidence type.

4.	Select the Source Drive Location. On the FRED, the CD and DVD drive  is the G: drive.

5.	A dialog box will appear, this time asking where to store the image. Click Add.

6.	The next screen prompts you to identify where the disk image will be
stored. Select the appropriate Image Destination Folder and enter the Image Filename . Image fragment size and compression do not apply to DVDs/CDs. The disks are also automatically saved as ISO-type disk
images. In the source directory you should have four files: a CUE
file, a cue.csv file (directory listing), and cue.txt file (image
verification) and an .iso file (the actual image).

7.   Click Finish to return to the Create Image dialog window, this time with the necessary information completed. Double check the
Image Source, the Image Destination, and that both
Verify images after they are created and Create directory
listings of all files in the image after they are created are
checked. Click Start to initiate the imaging process.


8.   A Creating Image dialog window will appear. It will indicate how
much time has elapsed during the creation of the image.


9.   Once completed, the Status will read Image created
successfully. You will also receive notification that the
Directory Listing was created successfully. In the image
destination folder, you will see the image (.iso), the Directory
Listing file (.csv), and the Verify Results file (.txt). The
Verify Results Summary contains the same data presented in the
Image Summary area below. This information contains the image
checksum information needed for the Digital Media database.



10.  In addition to the image checksum, checksums for each of the
individual files should be generated. To do so, select the
appropriate level in the file system of the attached disk. In the
screenshot below, this is the NONAME [FAT32] area on Partition 1.



Audio CDs
*********


