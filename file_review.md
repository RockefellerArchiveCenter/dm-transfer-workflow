---
layout: docs
title: "File Review"
---

## Overview

All disk images are scanned for viruses and malware before they are moved over to the Digital Records (X) drive. The following steps are performed by members of the processing team who have in-office workstations (digital media archivists).

### Step 1: Identify Workflow
Use the digital media log transfer method column to identify which of of the following workflows to use:
- SIP Creator: Option A
- Disk Image: Option B
- Rip Tracks: no review is needed

### Option A: SIP Creator file review
For items transferred using SIP Creator, use the reports created by SIP Creator to ensure there are no viruses or personally identifiable information within the files. All SIP Creator files should have been saved by the processing archivist on the Desktop of the BitCurator Machine.
- For small amounts of digital media (less than 20 items):
  - Manually review the Brunnhilde report for each digital media item by looking in `Desktop/FA#/ASrefID/metadata/submissionsDocumentation/brunnhilde`
  - Open the file called `report.html`. This will open a HTML report in the web browser.
  - Review the **virus report** and **SSN** sections for any viruses or social security numbers that may have been found by SIP Creator.
- For large amounts of digital media:
  - Run bash scripts `find_pii.sh` and `find_viruslog.sh` to automate looking in the log files for specific words or files that would indicate the existence of PII or viruses. `find_pii.sh` looks for a non-empty pii.txt file within the Brunnhilde output directory. `find_viruslog.sh` looks for the words "infected files."
  - Both scripts must be run from the folder containing the SIP Creator outputs. Copy and paste the scripts into the **FA# folder** and run them accordingly.
- Document the results in the Digital Media Log.

### Option B: Checking Disk Images for Viruses
This workflow should be used for .iso and .img files. Digital media files that were transferred using SIP Creator have already been scanned for viruses as part of the SIP Creator tool making this step unnecessary.

- On the BitCurator Machine, open a terminal window and switch to root user: `sudo su`
- Enter password used to sign in to the BitCurator Machine: `bcadmin`
- Navigate to the directory containing the virus script: `cd /Desktop/`
- Run the virus checking script: `./virus_scan.sh` (View this script on [GitHub](https://github.com/RockefellerArchiveCenter/scripts/blob/base/imaging/virus_scan.sh))
- Enter the FA number, digital media ID, and file extension of the disk image, hit `Enter` to run the script.
- Upon completion, the script will notify you of any errors or viruses found during the scanning process. Review output files if necessary.

### Step 2: Move files to the X:Drive
If no viruses are found, transfer the FA# folder containing all SIPs to the `X:Drive/Processing/Disk Images` folder using TeraCopy.

- Prepare the files for transfer: Cut and paste the files from the BitCurator Machine onto the transfer hard drive.
- Reconnect transfer hard drive to a computer with access to the X:Drive.
- Use TeraCopy to move the files. Open TeraCopy, confirm options:
  - Ensure **Timestamps** is checked
  - Ensure **Verify files after transfer** is checked
  - Click **Save as default** to always select these options when using TeraCopy in the future.
  - Select **Create a new list** from the toolbar.
  - Click **Source**, select folder containing files to be transferred from the hard drive. This usually will be a folder named "FA###".
  - Click **Target**, select the destination. This will always be `X:Drive/Processing/Disk Images`.
  - Click **Move**. This will be begin to move the files from the source location to the target location. "Move" is basically cutting/pasting the files into the target location without leaving a copy in the source folder.
