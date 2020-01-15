---
layout: docs
title: "Inventorying Digital Media Items"
---

## Overview

-	Inventory digital media item(s) in ArchivesSpace when the item(s) are encountered during accessioning/processing. Initial description of any digital media items inventoried during accessioning can be created in an FA shell record.
-	Describe digital media items in a sibling relationship to their parent units (e.g. file for [standard processing](/processing-manual/#processing-levels)) with the same box and/or folder instances. Do not create a child relationship to represent the association between the digital media item and the parent unit.
-	Inventory digital media items in the Digital Media Log as they are encountered during accessioning/processing.
-	In order to save a digital media item record, you must supply the ArchivesSpace Ref ID of the appropriate file-level component representing the digital media item in ArchivesSpace and retrieve the file and resource titles.
-	For accessioning or [minimal processing](/processing-manual/#processing-levels), you may supply the Ref ID of the series-level, subseries-level or file-level component. 

## Setup

The Digital Media Log is a tool for identifying digital media items during accessioning/processing in order to plan and perform preservation actions like disk imaging and for recording digital media stabilization information. It is integrated with ArchivesSpace, the collection management system used at the RAC for archival records, in order to reduce duplicate data entry, record the location of a digital media item, track and manage transferred items, and ensure more effective and efficient control of collection material. More information about the Digital Media Log can be found on the RAC's [Digital Media Log GitHub repository](https://github.com/RockefellerArchiveCenter/dm_log).

## Instructions

To create and save a digital media item record:

1.	Inventory the digital media item(s) in ArchivesSpace as described in the Overview section above. For further details on the creation of archival description, please refer to the Guide to Processing Collections at the RAC.
2.	Open the Digital Media Log, located at [dm-log.rockarch.org](http://dm-log.rockarch.org/) and set up an account.
3.  On the homepage for the Digital Media Log, click **Add Digital Media Item**. (Button should be located at the bottom of the homepage, below the list of digital media items)
4.  A record will generate for the digital media item and the digital media item **ID** field will autopopulate.
5.  Copy the ArchivesSpace Ref ID for the parent component from ArchivesSpace into the **ArchivesSpace Ref ID** field and click **Find in ArchivesSpace**. (The parent component is the description of the digital media item in ArchivesSpace. Make sure that the component has been saved in ArchivesSpace before attempting this step.)
6.  The **Parent Component** and **Parent Resource** fields should autopopulate. If they do not, contact the administrator.
7.  Choose the appropriate format from the drop down menu in the **Format** field.
8.  Default entry for **Transfer Status** field - **Not Transferred** - will autopopulate. This field along with the **Transfer Method** and **Date Transferred Field** can be updated after the digital media item record is saved. (You will want to return to the digital media item after transfer actions have been completed or attempted)
9. Click the **Submit** button to save the record. If you are ready to transfer the item, continue to [transfer setup](/dm-transfer-workflow/transfer-instructions#transfer-overview-&-setup)

Next Step: [Transfer Instructions](/dm-transfer-workflow/transfer-instructions)
