# HOWTO CUPs Printing

## [IGEL KB - CUPs Printing](https://kb.igel.com/igelos-11.08.200/en/cups-69178109.html)
## [IGEL Community GitHub - Work from home with network printer](https://github.com/IGEL-Community/IGEL-Custom-Partitions/tree/master/CP_Source/Tools_Drivers/WFH-Add-Network-Printers)
## [IGEL Community GitHub - Work from office with network printer](https://github.com/IGEL-Community/IGEL-Custom-Partitions/tree/master/CP_Source/Tools_Drivers/WFO-Add-Assigned-Printers)

-----

## USB attached printers - Use PPD file

If printer is not network attached, then follow IGEL note on setting up CUPs printer with USB connection with PPD file.

### [Installing a Custom CUPS Driver](https://kb.igel.com/igelos-11.08.200/en/installing-a-custom-cups-driver-69177139.html)

-----

### Methods to obtain PPD file for printer

- Download PPD from vendor web site and edit PPD file to remove / comment out the **\*cupsFilter:** line by adding "%" after the "*"

```
*%cupsFilter:
  ```

- Connect printer to the network and create PPD file from IGEL OS.  

```bash
driverless ipp://IP-address-of-printer/ipp/print | sed -e '/IP-address-of-printer/d' -e 's/drvless/printer-name/' > /tmp/printer-name.PPD
```

-----

## USB always on (Printer, Scanner, etc.)

System > Firmware Customization > Custom Commands > Desktop

```bash
echo on | tee /sys/bus/usb/devices/*/power/level > /dev/null
```

-----

## Add USB attached Printer

```bash
#!/bin/bash

USBDEVICE=$(/usr/lib/cups/backend/usb 2>/dev/null | cut -d " " -f 2)

lpadmin -p USBPRINTER -E -v "${USBDEVICE}" -m /wfs/USBPRINTER.ppd
```
