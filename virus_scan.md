---
layout: docs
title: "Scanning for Viruses"
---

## Overview

All disk images need to be scanned for viruses and malware on the virus checking workstation (Ginger) before they are moved over to the Digital Records (X) drive.

**Note:** Before you begin this step, please make sure the transfer process was successful. If you've experienced difficulties using the available tools for transferring digital media refer to the [Troubleshooting](/dm-transfer-workflow/troubleshooting) page. If the item still failed to transfer, document that in the Digital Media Log and do not attempt to scan the item for viruses. Otherwise, proceed to the instructions below for scanning digital media items for viruses.

## Setup

Make sure the disk images you want to virus check can be seen by the virus checking workstation (Ginger). The shared network between the virus checking workstation and the FRED can be found at (D:) on the FRED.

## Checking a Disk Image for Viruses
This workflow should be used for .iso & .img files.

1. Switch to root: `$ sudo su`
2. Enter password used to sign in to the virus checking workstation
3. Mount the network: `$ mount -o username=freduser //fredIPaddress/ginger /mnt`_(The IP address for connecting to the FRED on the quarantine network can be found on the ["System Info Sheets/FRED Info Sheet"](/info-sheets/fred-info-sheet))_
4. Enter password used to sign in to the FRED
5. Navigate to the directory containing the virus script: `$ cd /mnt`
6. Run the virus checking script: `$ ./virus_scan.sh`(View this script on [GitHub](https://github.com/RockefellerArchiveCenter/imaging_scripts/blob/master/virus_scan.sh))
7. Enter the FA number, digital media ID, and file extension of the disk image
8. End root session: `$ exit`

## Checking a Folder for Viruses

This workflow should be used for .wav files (audio cds) and scenarios where a disk image is not present.

1. Switch to root: `$ sudo su`
2. Enter password used to sign in to the virus checking workstation
3. Mount the network: `$ mount -o username=freduser //fredIPaddress/ginger /mnt`_(The IP address for connecting to the FRED on the quarantine network can be found on the ["System Info Sheets/FRED Info Sheet"](/info-sheets/fred-info-sheet))_
4. Enter password used to sign in to the FRED
5. Navigate to the directory containing the virus script: `$ cd /mnt`
6. Run the virus checking script: `$ ./directory_virus_scan.sh` (View this script on [GitHub](https://github.com/RockefellerArchiveCenter/imaging_scripts/blob/master/directory_virus_scan.sh))
7. Enter the FA number and digital media ID
8. End root session: `$ exit`

## Review Log File
Please check the log file after each scan to ensure all the files have been read and scanned. The results of the the virus scan can be found inside the folder containing the disk image and will follow a similar naming convention to digitalmediaID_scan.txt.
