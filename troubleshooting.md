---
layout: docs
title: "Troubleshooting by Digital Media Type"
---
## 3 1/2 Inch and 5 1/4 Inch Floppy Disks

### FRED does not recognized the KryoFlux

If the FRED does not recognize the KryoFlux, it is likely an issue that
Windows 10 has with the driver. To fix this issue:

1.  Open the Device Manager
2.  Expand "Ports COM & LPT" and right click on "Bossa Program Post"
3.  Choose "Browse my computer for driver software" then "let me pick
    from a list of device drivers"
4.  Since KryoFlux has already been installed, you should see the
    KryoFlux driver in the list
5.  Open the command prompt and cd to the DTC folder. Run "dtc -c2"

### KryoFlux GUI does not run when “Start” is selected

1.  Open the command prompt and cd to the DTC folder
2.  Run “java -jar kryoflux-ui.jar”
3.  With the command window still open, use the GUI to select “Start”
    again to being imaging. The command window will provide more
    detailed output of what the GUI is doing, allowing you to further
    troubleshoot using any error messages in the output window

### KryoFlux Errors and Warnings

While the KryoFlux is operating, there may be exceptions that trigger
warnings or errors. Confusingly, in the KryoFlux GUI (graphical user
interface—i.e., not the command line) these are all called “errors.” So,
most of what appears to be an “error” is simply a warning. While
warnings are for informational purposes only, errors will have a direct
effect on the operation. Some common warnings and errors:

-   Sector number is not within the allowed range; the sector was NOT
    included in the image. Error.
-   Data checksum could not be verified (might be part of a protection,
    e.g. calculation based on some seed only accessible by the original
    loader); warning only.
-   Slip marks (sector end) found at different positions from their
    expected values; warning only.
-   Header extra data was found. Data is hidden in unused parts of the
    block header. Sector images can't hold such data; warning only. *It
    is likely that this will appear on the beginning tracks; this is
    normal and can be ignored.*
-   Format type/block ID is non-standard; warning only.
-   Sector length is non-standard. If considering it as a protection
    measure it is possible to decode the sector and saving it in the
    image; if not, you'll get another flag saying so; warning only.
-   Sector ignored, sector was found but sector image was not created.
    Reason could be sector having a different size set compared to what
    the image uses; error.
-   Special protection detected which will malform the sector on
    purpose, retry will be suppressed; warning only.
-   Side number found is different from what it should be; warning only.
    *If this warning is appearing for multiple disks, the side selection
    on the drive is broken and a new drive must be used.*
-   Track number found is different from what it should be; warning
    only.
-   Sector truncated. Sector data is incomplete, decoding stopped.
    Reason is another sync/mark was found in the data block. Almost
    certainly protection that a sector image can't deal with; sector is
    not included in the image; error.
-   Sector offset found is illegal. Sector is still decoded; warning
    only.
