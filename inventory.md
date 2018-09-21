---
layout: docs
title: "Inventorying Digital Media Items"
---

## Overview

Digital media items should be inventoried in the Digital Media Log as they are encountered during processing. In order to save a digital media item record, you must supply the ArchivesSpace RefId of the appropriate item-level component representing the digital media item in ArchivesSpace and retrieve the item and resource titles. For minimal processing, you may supply the RefId of the series-level or subseries-level component. Digital media items should be described as a sibling relationship to their parent units (e.g. file for standard processing) and should have the same box and/or folder instances. Do not create a child relationship to represent the association between the digital media item and the parent unit.

## Setup

The Digital Media Log is a tool for identifying digital media items during processing in order to plan and perform preservation actions like disk imaging and for recording digital media stabilization information. It is integrated with ArchivesSpace, the collection management system used at the RAC for archival records, in order to reduce duplicate data entry, record the location of a digital media item, and ensure more effective and efficient control of collection material. More information about the Digital Media Log can be found on the RAC's [Digital Media Log GitHub repository](https://github.com/RockefellerArchiveCenter/dm_log).

The Digital Media Log needs to be opened in order for the steps in the following Instructions section to be performed. The Digital Media Log is located at [dm-log.rockarch.org](http://dm-log.rockarch.org/). An account is required to access The Digital Media Log.

## Instructions

1.  Add a new digital media item record.
2.  The digital media item ID field will autopopulate.
3.  Copy the ArchivsSpace RefId for the parent component from ArchivesSpace into the
    "ArchivesSpace RefID" field and click "Find in ArchivesSpace." (Make
    sure the component has been saved in ArchivesSpace.)
4.  The component and resource fields should autopopulate. If they do
    not, contact the administrator.
5.  Choose the appropriate format from the drop down menu.
6.  If you are ready to transfer the item, continue to [transfer setup](transfer-instructions#transfer-overview-&-setup)

## Recording Transfers in Digital Media Log

1. When you have finished transferring a digital media item, changed the transfer status to "Transferred - Failed" or "Transferred - Success" as appropriate.
    <div class="docs-example">
      <p>Note: If transfer fails initially you may need to try again; appropriate number of transfer attempts is dependent upon type of media.</p>
    </div>
2. Record the transfer method. Record the successful method if multiple methods were attempted.
3.  When you changed the transfer status from "Not Transferred," the "Date Transferred" autopopulated with today's date. Correct if needed.
4.  Record whether the physical digital media item is to be retained due to artifactual value or disposed of. This is to record the disposition of the physical media item and not the appraisal of the contents of the digital media item.

[Transfer Instructions](transfer-instructions)
