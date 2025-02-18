# HOWTO Remove IGEL Device License

-----

## Summary of steps to remove IGEL device License

- Remove the License from the IGEL License Portal
- Remove the Device License from UMS
- Remove the License Pack from the IGEL Device
- Reset IGEL Device to Factory Defaults

**Note:** [IGEL Knowledge Base: Removing an IGEL License Completely](https://kb.igel.com/licensesmore-igelos11/en/removing-an-igel-license-completely-24391359.html)

-----

## IGEL Licensing Overview

Removing a license from the IGEL license portal, and UMS does not remove it from the device. Below is a comprehensive guide to remove the license from the License Portal, sync that to UMS, and then remove the license from the IGEL device.

**Note I:** This will eventually sync with UMS and update the information, but you can also force a sync from the UMS license page. If you need to remove the license from the device, you must make sure the license pack in UMS reflects that the device is gone before removing it from the device.

**Note II:** If you have unrestricted auto license deployment enabled, the device may re-license itself!!

-----

## Remove the license from the IGEL license Portal

- Identify the Unit ID or MAC Address of the device you wish to remove
- In your browser navigate to <https://activation.igel.com> and log in with your account
- Click Search Hardware in left navigation bar and enter the MAC or Unit ID
  - This will bring up a list of license packs the device is associated with
  - **Hint:** you can copy this from UMS by highlighting the number, and pressing Ctrl+C
- Double-click the license pack you want to remove the device from
- On the manage license page, click the Remove Hardware button
- Finally, check the box next to the Unit ID of the device, agree that you have read the T&C and click OK

-----

## Removing the device from UMS

Now that the portal reflects the change, and UMS has synced, we will need to remove the device license from UMS, so it does not re-issue the license back to the device. To do this follow the steps below:

- In UMS open UMS Administration in the navigation menu
- Navigate to **Global Configuration -> Licenses -> Device Licenses**
- Click the Select Filter button and enter the Unit ID of the device and click OK to locate the device you want to remove
- **Note:** You can also use the three dots “…” button to navigate to the device
- Select the license pack you wish to release and then click the minus button in the top right

-----

## Remove the license pack from the IGEL device

Now that we have removed the license from the license portal, and UMS, we can move forward with removing the IGEL device’s local copy of the license. This will be done via an SSH/Secure Terminal session to the device, so make sure you have one of those enabled.

- Open an SSH or Secure Terminal session to the device you want to remove the license
- Make sure you are logged in as the root account
- Run one of the following commands to remove a specific license type, or all licenses

### Remove all licenses

```bash
mount -o remount,rw /license
rm -rf /license/dsa/licenses/*.lic
mount -o remount,ro /license
reboot
```

### Remove Enterprise Management pack licenses  

```bash
mount -o remount,rw /license
find /license/dsa/licenses/ | xargs grep -l "Enterprise Management Pack" | awk '{print "rm "$1}' > /tmp/removelic.sh
chmod +x /tmp/removelic.sh
/tmp/removelic.sh
mount -o remount,ro /license
reboot
```

### Remove Workspace edition licenses

```bash
mount -o remount,rw /license
find /license/dsa/licenses/ | xargs grep -l "Workspace Edition" | awk '{print "rm "$1}' > /tmp/removelic.sh
chmod +x /tmp/removelic.sh
/tmp/removelic.sh
mount -o remount,ro /license
reboot
```

-----

## How to remove the starter license from the IGEL device:

The starter license is not a file on the IGEL OS. Here is the command to remove starter license:

```bash
bootreg set /dev/igfdisk installation_date INVALID && bootreg set /dev/igfdisk installation_meta INVALID
```

-----

## Reset IGEL Device to Factory Defaults

To reset IGEL device to factory defaults.

- Make sure you are logged in as the root account
- Run the following command to reset device to factory defaults

```bash
/bin/reset_to_defaults
```

-----

## (OPTIONAL) Reset Unit ID to match the physical NIC MAC address

To reset unit ID to match the physical NIC MAC address:

```bash
/bin/get_unit_id -i -r -f
   ```
Where:

-i "information" lists the used MAC ID
-r "reset" reset the MAC ID to the current hardware
-f "force" forces the action
