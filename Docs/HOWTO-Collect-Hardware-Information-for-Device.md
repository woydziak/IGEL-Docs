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

![image01](Images/HOWTO-Collect-Hardware-Information-for-Device-02.png)
