---
layout: docs
title: "Troubleshooting"
---

## Imaging Script Errors

If/when an error is recorded, make a maximum of five attempts to create a disk image or run a virus scan, with no more than three attempts made for the same error.

### Cannot determine file system type

Solution: Check that you entered the correct format when prompted by the script (cdrom, cdrw, dvd, dvdrw). If this error continues to appear, try mounting the disk image to determine if the contents have been successfully copied. Sometimes a disk image can still be considered successful despite this error.

### Sector offset supplied is larger than disk image (maximum: 0)

This error can mean two things: either the disk is corrupt/empty, or you may be trying to image an audio CD.

Solution: Insert disk into the FRED, open Exact Audio Copy (EAC). If EAC shows a track listing, continue following the [audio CDs](/dm-transfer-workflow/transfer-instructions#audio-cds) transfer workflow. If no track listing appears, the disk may be blank or corrupt.

### Error stat(ing) image file (raw_open: image "ref_id.iso" - No such file or directory)

Solution: Empty the folder containing the .img file and run the script again.

## KryoFlux Errors

### FRED does not recognize the KryoFlux

If the FRED does not recognize the KryoFlux, it is likely an issue that Windows 10 has with the driver. To fix this issue:

1. Open the **Device Manager**
2. Expand **Ports COM & LPT** and right click on **Bossa Program Post**
3. Choose **Browse my computer for driver software** then **let me pick from a list of device drivers**
4. Since KryoFlux has already been installed, you should see the KryoFlux driver in the list
5. Open the command prompt and navigate to the DTC folder. Run `dtc -c2`

### KryoFlux GUI does not run when “Start” is selected

1. Open the command prompt and navigate to the DTC folder
2. Run `java -jar kryoflux-ui.jar`
3. With the command window still open, use the GUI to select “Start” again to being imaging. The command window will provide more detailed output of what the GUI is doing, allowing you to further troubleshoot using any error messages in the output window

### KryoFlux Errors and Warnings

While the KryoFlux is operating, there may be exceptions that trigger warnings or errors. Confusingly, in the KryoFlux GUI (graphical user interface—i.e., not the command line) these are all called “errors.” So, most of what appears to be an “error” is simply a warning. While warnings are for informational purposes only, errors will have a direct effect on the operation. Some common warnings and errors:

- Sector number is not within the allowed range; the sector was NOT included in the image. Error.
- Data checksum could not be verified (might be part of a protection, e.g. calculation based on some seed only accessible by the original loader); warning only.
- Slip marks (sector end) found at different positions from their expected values; warning only.
- Header extra data was found. Data is hidden in unused parts of the block header. Sector images can't hold such data; warning only. It is likely that this will appear on the beginning tracks; this is  normal and can be ignored.
- Format type/block ID is non-standard; warning only.
- Sector length is non-standard. If considering it as a protection measure it is possible to decode the sector and saving it in the image; if not, you'll get another flag saying so; warning only.
- Sector ignored, sector was found but sector image was not created. Reason could be sector having a different size set compared to what the image uses; error.
- Special protection detected which will malform the sector on purpose, retry will be suppressed; warning only.
- Side number found is different from what it should be; warning only. If this warning is appearing for multiple disks, the side selection on the drive is broken and a new drive must be used.
- Track number found is different from what it should be; warning only.
- Sector truncated. Sector data is incomplete, decoding stopped. Reason is another sync/mark was found in the data block. Almost certainly protection that a sector image can't deal with; sector is not included in the image; error.
- Sector offset found is illegal. Sector is still decoded; warning only.

## Virus Script Errors

### Data Scanned and Data Read = 0MB
If the virus scan log file shows no data is being read or scanned, try to scan the disk image using ClamTK, which is installed on the BitCurator machine. This error has occurred most frequently when attempting to scan a disk image of a DVD, although not *all* DVDs have resulted with this error.

1. Disconnect the Ethernet cord on the BitCurator machine
2. Navigate to the virus checking workstation (Ginger) network using the file explorer and locate the disk image on the quarantined network
3. Right click the disk image file and select **Open with... Disk Image Mounter**, the mounted disk image should appear on the left-hand side of the screen. Click on the mounted disk image so that an arrow symbol appears next to it, this will ensure that ClamTK will be able to see the mounted disk image.
4. Run ClamTK with sudo permissions by opening a terminal window and typing `sudo clamtk` + ENTER
5. In ClamTK, select **Scan a directory**
6. Select the mounted disk image, then select the parent directory to run the virus scan
7. Check the results of the virus scan by double-clicking the **History** icon in ClamTK, select today's date, and click **View** (located on the bottom left of the screen)
8. Copy the results of the virus scan, paste them into a new .txt file
9. Save the .txt file as `dmID_scan.txt` inside the folder containing the disk image and log file

If you are using the BitCurator machine to virus check many disk images, be sure to clear the mount points to avoid confusion:
1. Open a new terminal window
2. `sudo su`
3. `losetup -D`

## Advanced Troubleshooting Form
Once all possible troubleshooting actions have been exhausted, please submit the [Advanced Troubleshooting form](https://form.asana.com/?k=EsWapMmv2cZMzHwcrD9_2A&d=4711715224923).

**Please note:** this form should be used to communicate persistent disk imaging errors and attempted troubleshooting actions. *Do not fill this form out if you have not yet conducted any troubleshooting activities.* 

Once the form is submitted, properly label the digital media item and leave it on the "Problematic Media" shelf in the Digital Media (DM) Archivist's office.

If you solved the issue using a method that is not documented on the Troubleshooting page, please contact the Digtial Media (DM) Archivist so it can be added.
