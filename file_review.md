---
layout: docs
title: "File Review"
---

## Overview

All disk images are scanned for viruses and personally identifiable information (PII) before they are moved over to the Digital Records (X) drive. The following steps are performed by members of the processing team who have in-office workstations (digital media (DM) archivists).

### Step 1: Review Digital Media Hand Off Form
Digital Media Hand Off Form submissions will automatically populate in an Asana project. Once a submission is received, additional subtasks are added and Digital Media (DM) Archivists are notified.

DM Archivists will assign themselves to incoming form submissions and continue to "Step 2: Identify Workflow".

### Step 2: Identify Workflow
Use the "Transfer Method" column within the digital media log to identify which of of the following workflows to use:
- SIP Creator: Option A
- Disk Image: Option B
- Rip Tracks: no review is needed

### Option A: SIP Creator File Review
For items transferred using SIP Creator, use the reports created by SIP Creator to ensure there are no viruses or personally identifiable information within the files. All SIP Creator files should have been saved by the processing archivist on the Desktop of the BitCurator Machine.
- For small amounts of digital media (less than 20 items):
  - Manually review the Brunnhilde report for each digital media item by looking in `Desktop/FA#/ASrefID/metadata/submissionsDocumentation/brunnhilde`
  - Open the file called `report.html`. This will open an HTML report in the web browser.
  - Review the **virus report** and **SSN** sections for any viruses or social security numbers that may have been found by SIP Creator.
- For large amounts of digital media:
  - Run bash scripts `find_pii.sh` and `find_viruslog.sh` to automate looking in the log files for specific words or files that would indicate the existence of PII or viruses. `find_pii.sh` looks for a non-empty pii.txt file within the Brunnhilde output directory. `find_viruslog.sh` looks for the words "infected files."
  - Both scripts must be run from the folder containing the SIP Creator outputs. Copy and paste the scripts into the **FA# folder** and run them accordingly.
- Document the results in the Digital Media Log.

### Option B: Disk Image File Review
This workflow should be used for .iso and .img files. It requires the use of the Disk Image Processor tool which can only be used on the BitCurator Machine. Disk Image Processor analyzes the files, creates reports, and carves the files from the disk image. After Disk Image Processor is run, it's required to review the reports to confirm the files are free from viruses and personally identifiable information (PII).

- Confirm files are on the BitCurator Machine. If disk images were created on the FRED, copy the disk images to a hard drive and connect it to the BitCurator Machine.
- Log in the BitCurator Machine using the password: `bcadmin`
- Navigate to: Applications (top toolbar) -> Forensics and Reporting -> SIP Creator
- Use the **Processing** tab
- Configure options:
  - **Bag SIPs:** unchecked
  - **Make SIPs from logical files only (do not include disk image):** check this option
  - **Run bulk_extractor:** check this option
- Select **Source**, click **Browse** and select the folder containing the disk image, not the disk image itself.
  - The source should always look similar to `FA#/ASrefID`
- Create a folder for the output files. Select **Destination**, click **Browse**. Create a new folder within the folder containing the disk image. Name this folder after the ASrefID and use it as the Destination location.
  - The destination should always look similar to `FA#/ASrefID/ASrefID`
- Confirm Source and Destination locations. **The source and destination should never be the same file path.** If the incorrect file paths are selected, the tool may overwrite everything in the **Source** location.
  - Source: `FA#/ASrefID`
  - Destination: `FA#/ASrefID/ASrefID`
- Click **Begin Processing** to run the tool. A pop up will confirm that the operation is complete.
- Review Brunnhilde report by looking in `FA#/ASrefID/metadata/submissionsDocumentation/brunnhilde`
- Open the file called `report.html`. This will open a HTML report in the web browser.
- Review the **virus report** and **SSN** sections for any viruses or social security numbers that may have been found by SIP Creator.
- Document the results in the Digital Media Log.

### Step 3: Move files to the X:Drive
If no viruses are found, transfer the FA# folder containing all SIPs to the `X:Drive/Processing/Disk Images` folder using TeraCopy.

- Prepare the files for transfer. Cut and paste the files from the BitCurator Machine onto the transfer hard drive.
- Reconnect transfer hard drive to a computer with access to the X:Drive.
- Use TeraCopy to move the files. Open TeraCopy, confirm options:
  - Ensure **Timestamps** is checked
  - Ensure **Verify files after transfer** is checked
  - Click **Save as default** to always select these options when using TeraCopy in the future.
  - Select **Create a new list** from the toolbar.
  - Click **Source**, select the folder containing files to be transferred from the hard drive. This usually will be a folder named "FA###".
  - Click **Target**, select the destination. This will always be `X:Drive/Processing/Disk Images`.
  - Click **Move**. This will be begin to move the files from the source location to the target location. "Move" is cutting/pasting the files into the target location without leaving a copy in the source folder, which avoids the need to go back delete the original files from the hard drive.

## Step 3: Update Asana Projects
- **Digital Media Hand Off Project:** check off all tasks (including subtasks). The item will automatically move to the "Completed" section of the Asana project.
- **Digital Media Log:** Once ***all*** items are moved to the X:Drive, update the project's status to "Complete". If there are incomplete items, for any reason, do not mark the project as complete.
