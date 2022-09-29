# HOWTO Run VMware Fusion Virtual Machines on MacOS Monterey

-----

## MacOS Monterey broke VirtualBox bridged Networking

The current VirtualBox, 6.1.32, [does not support bridged networking on MacOS Monterey](https://forums.virtualbox.org/viewtopic.php?f=8&t=105174&p=513054&hilit=bridged#p513054).

VMware Fusion supports bridged networking.

-----

## Steps to setup IGEL OS VM using VMware Fusion version 12.2.1

- Create new Virtual Machine (select IGEL ISO image > OSC11.06.221.iso)
- Choose Operating System (Other > Other 64-bit)
- Choose Firmware Type (Legacy BIOS)
- Change memory from 256 MB to 4096 MB
- Change Network Adapter to Bridged Networking > Autodetect
