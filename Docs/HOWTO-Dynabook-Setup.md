# HOWTO Dynabook Setup

-----

## Product: TECRA A40-J (PMM10U) || Version: PMM10U-00101U

### Tested with [IGEL OS 11.06.210](https://www.igel.com/software-downloads/workspace-edition/)
-----

#### BIOS settings:

1. Power up the device while pressing the [F2] button repeatedly in rapid succession.
2. If a password prompt is shown, enter the BIOS password.
3. Select Setup Utility.
4. Select Security tab.
5. Set Secure Boot to \<Disabled>.
6. Select Boot tab.
7. Set Boot Option \# 1 to \<USB Memory>.
8. Set Boot Option \# 2 to \<HDD/SSD>.
9. Save the settings and exit [F10].
10. Connect the IGEL OSC USB stick to the device.
11. Reboot the device.
12. You can continue with the IGEL OS installation procedure.

-----

#### Use iNet Wireless Daemon (iwd) for Wi-Fi backend:

1. Open up IGEL Setup.
2. Select System > Registry.
3. Select network.interfaces.wirelesslan.wireless_backend.
4. Wi-Fi backend set to \<iNet Wireless Daemon (iwd)>.
5. Select Ok.
6. Reboot the device.

-----

#### Set action for display lid closing:

1. Open up IGEL Setup.
2. Select System > Registry.
3. Select system.actions.lid.ac.
4. Select lid close action while plugged in set to \<Turn off display>.
5. Select system.actions.lid.battery.
4. lid close action while not plugged in set to \<Suspend>.

-----

#### (Optional) To disable touch pad and use external mouse:

1. Open up IGEL Setup.
2. User Interface > Input > Touchpad > Uncheck \<Enable Touchpad>.
