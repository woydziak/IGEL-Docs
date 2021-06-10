# HOWTO Collect Hardware Information for a Device

-----

## Steps to collect the data

- Format a USB thumb drive on your PC (FAT or NTFS)
- Copy the collection script (see below) to USB thumb drive
- Enable Storage Hotplug (Devices > Storage Devices > Storage Hotplug)
- Plug USB thumb drive in IGEL OS device (auto mounted in /media folder)
- Open terminal window (as Root)
- Run collection script
- Safely remove USB thumb drive (Start > System > Safely Remove Hardware)
- Send zip file to your contact

-----

## Collection Script

Collection script (collect_data.sh) to copy onto thumb drive

```
#!/bin/bash

mkdir data_dump
cd data_dump

lshw > lshw_ouptut.txt
lsusb > lsusb_output.txt
lspci > lspci_output.txt
dmesg > dmesg_output.txt
alsa-info --no-upload --output alsa-infor_output.txt
rfkill list all > rfkill_list_all.txt
journalctl > journalctl_output.txt
cp /var/log/Xorg.0.log Xorg.0.log
cp /etc/os-release etc-os-release.txt
cp /wfs/group.ini wfs-group.ini
tar cvjf var-log.tar.bz2 /var/log

cd ..

zip -r data_dump.zip data_dump
   ```

-----

## Enable Storage Hotplug (Devices > Storage Devices > Storage Hotplug)

![image01](Images/HOWTO-Collect-Hardware-Information-for-Device-01.png)

-----

## Run Collection Script (Open Terminal Window)

```
login as "user" or "root": root
 # df -H | grep media
 /dev/sda1    17G   44M     17G   1%  /media/B2B0AB93
 # cd /media/B2B0AB93
 # ls
 collect_data.sh
 # /bin/bash collect_data.sh
 # ls
 collect_data.sh
 data_dump
 data_dump.zip
 # exit
  ```

-----

## Safely remove USB thumb drive (Start > System > Safely Remove Hardware)

![image02](Images/HOWTO-Collect-Hardware-Information-for-Device-02.png)


-----

## Tips for prepping PC for IGEL OS install

- Make sure BIOS is at latest version. Check [Linux Vendor Firmware Service (LVFS)](https://fwupd.org/lvfs/docs/users). Until IGEL OS supports LVFS, BIOS can be updated from Ubuntu 18.04. If the PC is not in LVFS, check for latest BIOS from vendor web site.
- Make sure BIOS is set back to default settings.
- Check for and apply BIOS settings for Ubuntu 18.04.

-----

## Video driver and booting (blacklist framebuffer driver)

Framebuffer drivers are generally buggy and poorly-supported, and cause suspend failures, kernel panics and general mayhem.  For this reason we never load them automatically.

If PC firmware has a Legacy Boot option, it might interfere with the kernel’s ability to use the framebuffer during boot.

The kernel may hang on framebuffer driver. As first step in debugging, blacklist the framebuffer driver in file /etc/modprobe.d/blacklist-framebuffer.conf

 For example, add the following entry to the System/Firmware Customization/Custom Commands/Base Initialization section of IGEL Setup:

echo “blacklist efifb” >> /etc/modprobe.d/blacklist-framebuffer.conf

Save the change and reboot without the “Force VESA driver” option being set.

![image03](Images/HOWTO-Collect-Hardware-Information-for-Device-03.jpg)

-----

## Access terminal console or terminal log screen

- Access to terminal console: \<Ctl>\<Alt>\<F12>
- Switch back to GUI: \<Ctl>\<Alt>\<F1>
- Access terminal log screen: \<Ctl>\<Alt>\<F10>

-----

## Steps to update firmware from USB drive

- [Download OS11 -> Firmware Updates -> lxos_[VERSION]_public.zip](https://www.igel.com/software-downloads/workspace-edition/)
- Format USB Drive on PC (FAT)
- Unzip lxos_[VERSION]_public.zip to USB drive
- Configure IGEL OS to take new firmware from USB drive
- Run update

```
1. Configure at least one hotplug USB device:
   setparam devices.hotplug.usb-storage.numdevices 1
2. Apply your changes:
   kill_postsetupd
3. Connect the USB storage device to the device.
4. Wait for the USB storage device to be mounted automatically.
5. Determine the mount point:
   ls /media/
6. Configure the update parameters:
   setparam update.protocol file
   setparam update.file.path /media/<name of USB storage device>
7. Start the update process in the / directory using the command update
   update
   ```
