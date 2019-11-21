---
layout: docs
title: "Inventorying Digital Media Items"
---

## Overview

Digital media items should be inventoried in the Digital Media Log as they are encountered during processing. In order to save a digital media item record, you must supply the ArchivesSpace Ref ID of the appropriate item-level component representing the digital media item in ArchivesSpace and retrieve the item and resource titles. For [minimal processing](/processing-manual/#processing-levels), you may supply the Ref ID of the series-level or subseries-level component. Digital media items should be described as a sibling relationship to their parent units (e.g. file for [standard processing](/processing-manual/#processing-levels)) and should have the same box and/or folder instances. Do not create a child relationship to represent the association between the digital media item and the parent unit.

## Setup

The Digital Media Log is a tool for identifying digital media items during processing in order to plan and perform preservation actions like disk imaging and for recording digital media stabilization information. It is integrated with ArchivesSpace, the collection management system used at the RAC for archival records, in order to reduce duplicate data entry, record the location of a digital media item, and ensure more effective and efficient control of collection material. More information about the Digital Media Log can be found on the RAC's [Digital Media Log GitHub repository](https://github.com/RockefellerArchiveCenter/dm_log).

You must have the Digital Media Log opened in order to perform the steps in the following Instructions section. The Digital Media Log is located at [dm-log.rockarch.org](http://dm-log.rockarch.org/). An account is required to access the Digital Media Log.

## Instructions

Below are instructions for using the Digital Media Log to create and save a digital media item record. Digital media item records are created and maintained in order to describe items for the purpose of future stabilization, document preservation actions applied to digital media, and produce unique digital media IDs to track and manage transferred digital media.  

1.  On the homepage for the Digital Media Log, click **Add Digital Media Item**. (Button should be located at the bottom of the homepage, below the list of digital media items)
2.  A record will generate for the digital media item and the digital media item **ID** field will autopopulate.
3.  Copy the ArchivesSpace Ref ID for the parent component from ArchivesSpace into the **ArchivesSpace Ref ID** field and click **Find in ArchivesSpace**. (The parent component is the description of the digital media item in ArchivesSpace that was created during processing. Make sure that the component has been saved in ArchivesSpace before attempting this step.)
4.  The **Parent Component** and **Parent Resource** fields should autopopulate. If they do not, contact the administrator.
5.  Choose the appropriate format from the drop down menu in the **Format** field.
6.  Default entry for **Transfer Status** field - **Not Transferred** - will autopopulate. This field along with the **Transfer Method** and **Date Transferred Field** can be updated after the digital media item record is saved. (You will want to return to the digital media item after transfer actions have been completed or attempted)
7. Click the **Submit** button to save the record. If you are ready to transfer the item, continue to [transfer setup](/dm-transfer-workflow/transfer-instructions#transfer-overview-&-setup)

Next Step: [Transfer Instructions](/dm-transfer-workflow/transfer-instructions)
