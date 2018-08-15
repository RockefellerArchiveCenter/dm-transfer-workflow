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
2. Enter password used for the virus checking workstation
3. Navigate to the directory containing the scripts: `cd Desktop`
4. Run the expect script: `./script.exp` (this automatically spawns vc_setup.sh which mounts the network and enters the credentials)
5. Run the virus checking script: `./virus_script.sh`
6. Enter the FA number, digital media id, and file extension of the disk image
7. End root session: `exit`



[Troubleshooting](troubleshooting)
