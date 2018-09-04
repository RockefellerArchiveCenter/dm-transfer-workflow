---
layout: docs
title: "Scanning for Viruses"
---

## Overview

All disk images need to be scanned for viruses and malware on the Virus Checking Workstation (Ginger)
before they are moved over to the Digital Records (X) drive.


## Setup

Make sure the disk images you want to virus check can be seen by the Virus Checking Workstation (Ginger). The shared network between the Virus Checking Workstation and the FRED can be found at (D:) on the FRED.


## Running the Script

1. Switch to root: `sudo su`
2. Enter password used to sign in to the virus checking workstation
3. Mount the network: `mount -o username=freduser //fredIPaddress/ginger /mnt`

    <div class-"docs-example">
      <p><i>The IP address for connecting to the FRED on the quarantine network can be found on the "System Info Sheets/FRED Info Sheet" page.</i></p>
    </div>

4. Enter password used to sign in to the FRED
5. Navigate to the directory containing the virus script: `cd /mnt`
6. Run the virus checking script: `./virus_script.sh`
7. Enter the FA number, digital media id, and file extension of the disk image
8. End root session: `exit`

[Troubleshooting](troubleshooting)
