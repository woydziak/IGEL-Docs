# HOWTO Dynabook Setup

-----

## Product: TECRA A40-J (PMM10U) || Version: PMM10U-00101U

### Tested with [IGEL OS 11.06.210](https://www.igel.com/software-downloads/workspace-edition/)

-----

|  Type        | Description           |
|--------------|-----------------------|
| IGEL Type | Laptop |
| Use Case  | Cloud access, 4K Video Playback, Demanding Workloads |
| Chipset | 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz |
| CPU Cores | 4 |
| RAM | 8GB |
| Flash Storage | 256GB |
| Graphics - Chipset | Intel Iris Xe Graphics |
| Graphics - Ports | 1 x USB-C, 1 x HDMI |
| Graphics - Max Resolution | 14" HD (1366 x 768) or FHD (1920 x 1080), HDMI 4096 x 2304 @ 60Hz |
| Ethernet | 10/100/1000 Ethernet (RJ-45) |
| Wireless | Intel 802.11ax with Bluetooth 5.0 (AX201 family). Optional 3G/4G LTE Sierra EM7455 |
| Interfaces - USB Type C | 1 |
| Interfaces - USB | 2, 1 port 3G/4G LTE model |
| Interfaces - Serial | 0 |
| Interfaces - Audio | 3.5mm TRRS |
| Interfaces - Security Lock | Yes |
| Interfaces - Smartcard | Available (not tested on IGEL) |
| Fanless | No |
| Warranty | 1 Year |
| Vendor Link US | [Dynabook Tecra A40G - US](https://us.dynabook.com/computers-tablets/laptops/tecra/A40) |
| Vendor Link Europe | [Dynabook Tecra A40G - Europe](https://emea.dynabook.com/laptops/tecra/tecra-a40/) |

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
