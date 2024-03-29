---
layout: docs
title: "Transfer Instructions"
---

## Transfer Overview & Setup

An item must be inventoried in the Digital Media Log before it is transferred. See instructions for [Inventorying Digital Media Items](/dm-transfer-workflow/inventory). When a digital media item is imaged or otherwise has its contents transferred, this must be [recorded in the Digital Media Log](#recording-transfers-in-digital-media-log).

### Destination Folders and File Names

Newly created disk transfers are stored on the [virus checking](/dm-transfer-workflow/virus_scan) workstation and the transfers are accessible via mounted shares on the FRED ([Forensic Recovery of Evidence Device](https://digitalintelligence.com/products/fred/)) workstation. On the virus checking workstation and the X drive, all transfers are stored in a directory with the name of the ID auto-generated (digital media ID) by the Digital Media Log. On the X drive, these directories are located in a parent directory with the FA or Accession Number.

The BitCurator workstation is not connected to the virus checking workstation. Disk images created on the BitCurator must first be moved to the FRED, and then once on the FRED, they can be moved to the virus checking workstation.

### Disk Imaging

Disk imaging is currently the primary process by which the content and structure of a digital media item are transferred at the RAC. Disk images are single files containing the complete content and structure representing a data storage medium or device. By imaging legacy digital media, archivists can help ensure the long term preservation and management of records stored on devices vulnerable to deterioration and obsolescence.

At this point in time, disk images are created in-house for [optical disks (CDs and DVDs)](#cds-and-dvds), [external hard drives](#hard-drives-and-usb-flash-drives), [USB flash drives](#hard-drives-and-usb-flash-drives), and [3 1/2 inch floppy disks and 5 1/4 inch floppy disks](#3-and-a-half-inch-and-5-and-one-quarter-inch-floppy-disks) (recently dated disks that are PC-formatted).

### Choosing Transfer Method

The programs and hardware used to create disk images will vary depending on the type of digital media you are attempting to transfer.

Workstations Used to Transfer Digital Media Items:
- **BitCurator:** Used to image CDs and DVDs; connected to the FRED
- **FRED:** Used to image audio CDs, hard drives and USB flash drives, and 3 1/2 inch and 5 1/4 inch floppy disks; connected to the BitCurator machine and the virus checking workstation

Other Significant Hardware for Transferring Digital Media Items:
- **KryoFlux:** Used when imaging 3 1/2 inch and 5 1/4 inch floppy disks

Significant Software for Transferring Digital Media Items:

- **FTK Imager:** Used when imaging hard drives and USB flash drives

The sections below describe the options available for imaging each specific type of digital media as well as the step-by-step workflows for executing those imaging options.

**If/when an error is recorded during the imaging process, make a maximum of five attempts to create a disk image, with no more than three attempts made for the same error.**

## CDs and DVDs

In general, optical disk images will be forensically imaged on BitCurator. Forensic images cannot be made for audio CDs. Please see [audio CDs](#audio-cds) for instructions.

### Imaging with the Command Line on BitCurator

1. Insert the disk into the drive
2. Open the command line and navigate to the desktop by entering: `cd Desktop`
3. In the command prompt, run the bash script `./optical_disks.sh` (View this script on [GitHub](https://github.com/RockefellerArchiveCenter/scripts/blob/base/imaging/optical_disks.sh))
4. BitCurator will ask you to select from one of the following formats: cdrom, cdrw, dvd, dvdrw; in the command prompt, enter your disk's format

    <div class="docs-example">
      <p>Example: <code>cdrw</code></p>
    </div>

5. BitCurator will then image the disk
6. Update the item's transfer status in the Digital Media Log (See [Recording Transfers in Digital Media Log](#recording-transfers-in-digital-media-log) for further instruction).

If you receive an error message from BitCurator when attempting to complete any of the steps above consult [Imaging Script Errors](/dm-transfer-workflow/troubleshooting#imaging-script-errors) on the troubleshooting page.

### Audio CDs

Audio CDs are imaged on the FRED, using the program Exact Audio Copy.

1. On the FRED, open **Exact Audio Copy** and insert the CD into the optical disk drive.
2. In the **CD Title field**, enter the digital media ID of the CD. Remove text from the **CD author field**.
3. On the lefthand side, click the button that says **IMG**. This will create 1 uncompressed WAV file (containing all tracks) and a CUE file.
4. Select the appropriate folder to store the files and click **Save**. See [Destination Folders and File Names](#destination-folders-and-file-names) for information on where files should be stored.
5. Exact Audio Copy will begin ripping tracks and create a log file.
6. Update the item's transfer status in the Digital Media Log (See [Recording Transfers in Digital Media Log](#recording-transfers-in-digital-media-log) for further instruction).

## Hard Drives and USB Flash Drives

The following describes how to create disk images using FTK Imager on the FRED. Provide link to a picture of the FRED. FTK Imager is a digital forensics software used to create disk images of digital media separated either at accessioning, processing, or during the Legacy Digital Media Survey. FTK Imager is a different program than the Forensic Toolkit which is usually referred to as FTK.

### Imaging Instructions

1. Make sure the Tableau UltraBay write blocker on the FRED is OFF then plug in the drive. After the drive is connected, turn on the UltraBay write blocker. Two green lights should appear - the Power light and the WrtBlk light. After a short period of time, the Act light should turn also turn on which indicates the UltraBay recognizes the drive.
2. Open **FTK Imager**. Click **Create Disk Image** in the **File Menu** Select the source evidence type. Hard drives and thumb drives are physical media, so select **Physical Drive**.
3. Select the **Source Drive Location**. This can be a little confusing, as the program picks up all connected drives – including the one you’re working on. The FRED machine has quite a few drives. You can distinguish between them by using the data size listed in the dialog box. For example, two of the drives are listed at 2000GB and 7999GB, respectively. You can also disregard the WIBU Codemeter Stick USB device, which is a USB key to run the Forensic Toolkit. Click **Finish** to continue
4. A dialog box will appear, this time asking where to store the image. Click **Add.** Before the location of the image file can be identified, the type of image file to create needs to be selected. We use the E01 file format. Click **Next** to move forward.
5. The Evidence Item dialog box will appear. Insert the digital media ID associated with the item into the **Evidence Number** field. This is generated by the Digital Media Log. All other fields can be left blank.
6. The next screen prompts you to identify where the disk image will be stored. See [Destination Folders and File Names](#destination-folders-and-file-names) for information on the **Image Destination Folder:** and **Image Filename:**. Additionally, the **Compression** level and **Image Fragment Size** should both be set to 0 and **Use AD Encryption:** should be left unchecked.    
7. Click **Finish** to return to the Create Image dialog window, this time with the necessary information completed. Double check the **Image Source**, the **Image Destination**, and that both **Verify images after they are created** and **Create directory listings of all files in the image after they are created** are checked. Click **Start** to initiate the imaging process.
8. A Creating Image dialog window will appear. It will indicate how much time has elapsed during the creation of the image.
9. Once completed, the Status will read **Image created successfully**. You will also receive notification that the Directory Listing was created successfully. In the image destination folder, you will see the image (.E01), the Directory Listing file (.csv), and the Verify Results file (.txt). The Verify Results Summary contains the same data presented in the Image Summary area below. This information contains the image checksum information needed for the Digital Media database.
10. Make sure to safely eject the hardware you were imaging. Failure to do so can result in irreparable damage to the media.
11. Update the item's transfer status in the Digital Media Log (See [Recording Transfers in Digital Media Log](#recording-transfers-in-digital-media-log) for further instruction).

## 3 and a Half Inch and 5 and One Quarter Inch Floppy Disks

3 1/2 inch and 5 1/4 inch floppy disks are imaged using KryoFlux, a USB-based forensic floppy controller and the accompanying software. 

For guidelines on which directories images should be put in and file naming conventions, see [Destination Folders and File Names](#destination-folders-and-file-names)

The KryoFlux can be used with Windows, Mac, and Linux machines, and has both command line and GUI interfaces. Scripts using the KryoFlux command line tools on the BitCurator machine are preferred in most cases, but it is also possible to use the GUI on the FRED.

**The FRED is currently used at the RAC as the default machine to image 3 1/2 inch and 5 1/4 inch floppy disks.** Keeping the KryoFlux at the FRED station mitigates the chance of potential hardware and connection issues that may result from frequent moves between the FRED and the BitCurator. We would only run the KryoFlux on the BitCurator for the purpose of advanced troubleshooting or if an instance were to arise where the FRED could not be operated.

The following instructions for setup and use of KryoFlux on the FRED can also be used to image 3 1/2 and 5 1/4 inch floppy disks with KryoFlux on the BitCurator.

### KryoFlux Hardware Setup on the FRED

If you encounter issues setting up or using the KryoFlux, consult [KryoFlux Errors](/dm-transfer-workflow/troubleshooting#kryoflux-errors) on the troubleshooting page.

**Warning: Incorrect setup can damage the KryoFlux and void our warranty.** Follow the setup instructions carefully; for more details and images see the [official documentation](https://kryoflux.com/?page=download#docs) or the [Setup and Installation](https://github.com/archivistsguidetokryoflux/archivists-guide-to-kryoflux/tree/master/1%20PART%20ONE%20Getting%20Started) section of the Archivist's Guide to KryoFlux.

1. On a flat, non-conductive surface, connect the drive to the KryoFlux using the floppy data cable.
2. Connect KryoFlux to the FRED using the USB port in the back of the tower.
3. Connect the drive to power. **Important! Never ever connect or remove the floppy data cable while the drive and/or the board are still powered. Power always comes last!** You are connecting two systems with different grounds, so ground (connected via the floppy data cable) must always come first. Always make the drive – board - connection first, then plug the power (PSU & USB).
4. Always unplug and disconnect from mains when not in use! Do not leave unattended!
5. When switching between drives (e.g. from imaging 3 1/2 inch disks to 5 1/4 inch disks) the drive will need to be calibrated.

To calibrate using the command line:

1. Open the command prompt and navigate to the DTC folder
2. Run `dtc -c2`

To calibrate using the GUI:

1. Open the GUI and select the “Drive” tab at the top of the window
2. Select either Drive 0 or Drive 1 in the drop-down menu. **Note:** The drive will not calibrate if the wrong drive is selected. If you are unsure of which Drive to select, reference [Understanding Drive 1/0](https://docs.google.com/document/d/1LViSnYpvr2jf1TrCh6ELuL-FWo14ICw-WZeb8j5GGpU/edit#heading=h.s1zf81h6kdr3) in the “Archivists Guide to KyroFlux”
3. Select "Calibrate" from the drop-down menu

### Imaging with the KryoFlux using the Command Line on the FRED

1. After setting up the KryoFlux hardware, insert the floppy disk into the drive.
2. In the command prompt, navigate to the DTC folder.
3. Run `dtc -f\[filename\].img -i\[imagetype\]`

    <div class="docs-example">
      <p>image types correspond to numbers; "4" is for MFM images</p>
    </div>
4. Update the item's transfer status in the Digital Media Log (See [Recording Transfers in Digital Media Log](#recording-transfers-in-digital-media-log) for further instruction).

### Imaging with the KryoFlux GUI on the FRED
1. Open the **kryoflux-ui.jar – Shortcut** on the desktop.
2. After setting up the KryoFlux hardware, insert the floppy disk into the drive.
3. For each image you create, you must change the output file. In order to do so, go to **File &gt; Settings**. and navigate to the **Output** tab. Enter the directory that the image will be in. Make sure **Logs** is checked.
4. On the main KryoFlux screen, enter the name of the image in the text field. The image name is the auto-generated ID (digital media ID) created by the Digital Media Log.

    <div class="docs-example">
      <p>Example: 2lz4u8myrs or a9wf7at7r</p>
    </div>

5. Choose the appropriate image format from the drop down menu.

    <div class="docs-example">
      <p> If the disk format is unknown, but is a 3 1/2 inch floppy, first try “MFM Sector Image.” “FM sector image” and “MFM sector image” support basically any normal disk used for systems that contain a generic FM or MFM FDC.
      </p>
      <p>For 3 1/2 inch disks, if MFM or FM does not work, try FM Sector Information, CBM DOS sector image, AmigaDOS sector image, Amiga DiskSpare sector image, Apple DOS 400k/800k sector image, or CBM DOS extended sector image.</p>
    </div>

6. KryoFlux is separated into three sub-windows. The upper left window contains the track grid. Each block of the grid represents a track on the disk’s surface. The upper right window contains the track info block, with two more tabs called **Histogram** and **Scatter**. The lower part of the window is the control section, where the current track, drive controls, and the filename are displayed. Below the filename is the format selector which is dependent on profiles. The complete last line of the window is the status line which displays additional information. During dumping, blocks change their color according to the result of the process.
  - **Green** – track decoded, no errors found
  - **Grey** – noise (or unknown encoding scheme)
  - **Red** – track decoded, error(s) found, reading will be retried
  - **Yellow** – notifications and warnings, e.g., additional header data found
  - **Glowing** – track is being dumped
  - To get more information about the result of a certain track, move your mouse pointer over it. This will output the result of the operation in the status line.
7. Click **Start** and note what time imaging started.
8. Update the item's transfer status in the Digital Media Log (See [Recording Transfers in Digital Media Log](#recording-transfers-in-digital-media-log) for further instruction).

## Recording Transfers in Digital Media Log

1. When you have finished transferring a digital media item, change the transfer status to **Transferred - Failed** or **Transferred - Success** as appropriate. Note: If transfer fails initially you may need to try again; make a maximum of five attempts, with no more than three attempts made for the same error. Record the transfer method. Record the successful method if multiple methods were attempted.
2. When you change the transfer status from **Not Transferred**, the **Date Transferred** autopopulated with today's date. Correct if needed.

Next Step: [Scanning for Viruses](/dm-transfer-workflow/virus_scan)
