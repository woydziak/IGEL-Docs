# HOWTO CUPs Printing

## [IGEL KB - CUPs Printing](https://kb.igel.com/igelos-11.07/en/cups-57335074.html)
## [IGEL Community GitHub - Work from home with network printer](https://github.com/IGEL-Community/IGEL-Custom-Partitions/tree/master/CP_Source/Tools_Drivers/WFH-Add-Network-Printers)
## [IGEL Community GitHub - Work from office with network printer](https://github.com/IGEL-Community/IGEL-Custom-Partitions/tree/master/CP_Source/Tools_Drivers/WFO-Add-Assigned-Printers)

-----

## USB attached printers - Use PPD file

If printer is not network attached, then follow IGEL note on setting up CUPs printer with USB connection with PPD file.

### [Installing a Custom CUPS Driver](https://kb.igel.com/igelos-11.07/en/installing-a-custom-cups-driver-57334154.html)

-----

### Methods to obtain PPD file for printer

- Download PPD from vendor web site and edit PPD file to remove / comment out the **\*cupsFilter:** line by adding "%" after the "*"

```
*%cupsFilter:
  ```

- Connect printer to the network and create PPD file from IGEL OS.  

```bash
driverless ipp://IP-address-of-printer/ipp/print | sed '/IP-address-of-printer/d' > /tmp/printer-name.PPD
