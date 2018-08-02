## CDs & DVDs

In general, optical disk images will be forensically imaged using FTK
Imager or BitCurator. Forensics images cannot be made for Audio CDs.
Please see [Audio CDs](#audio-cds) for instructions.

The following describes how to create disk images using FTK Imager. FTK
Imager is digital forensics software used to create disk images of
digital media separated either at accessioning, processing or during the
Legacy Digital Media Survey. FTK Imager is a different program than the
Forensic Toolkit, which is usually referred to as FTK.

### Imaging with the Command Line

1.  Insert the disk in the drive.
2.  In the command prompt, run the script optical\_disks.sh.

### Audio CDs

1.  On the FRED, open Exact Audio Copy and insert the CD into the
    optical disk drive.
2.  In the CD Title field, enter the digital media ID of the CD. Remove
    text from the CD author field.
3.  On the lefthand side, click the button that says "IMG." This will
    create 1 uncompressed WAV file (containing all tracks) and a CUE
    file.
4.  Select the appropriate folder to store the files. See
    transfer-overview for information on where files should be stored.
5.  When copying is complete, click "Create Log File."
