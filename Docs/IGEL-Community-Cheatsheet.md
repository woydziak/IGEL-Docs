# IGEL-Community-Cheatsheet

## [Linux-General](Cheatsheet-Linux-General.md)

| command                                                    | description                                |
|------------------------------------------------------------|--------------------------------------------|
| [cat](Cheatsheet-Linux-General.md#cat)                     | display the content of a file              |
| [cd](Cheatsheet-Linux-General.md#cd)                       | change folder                              |
| [chmod](Cheatsheet-Linux-General.md#chmod)                 | change file attributes                     |
| [compgen](Cheatsheet-Linux-General.md#compgen)             | list all the linux commands                |
| [cp](Cheatsheet-Linux-General.md#cp)                       | copy files and folders                     |
| [date](Cheatsheet-Linux-General.md#date)                   | date tool                                  |
| [echo](Cheatsheet-Linux-General.md#echo)                   | output strings                             |
| [grep](Cheatsheet-Linux-General.md#grep)                   | search for regular expression              |
| [kill](Cheatsheet-Linux-General.md#kill)                   | kill a running task by process id          |
| [killall](Cheatsheet-Linux-General.md#killall)             | kill a running task by name                |
| [lpc]                                                      | Printer control tool                       |
| [lpq]                                                      | Show current print jobs                    |
| [lpr]                                                      | Print a file                               |
| [lprm]                                                     | Delete a print job                         |
| [lpstat]                                                   | Show finished print jobs                   |
| [ls](Cheatsheet-Linux-General.md#ls)                       | show directory content                     |
| [mkdir](Cheatsheet-Linux-General.md#mkdir)                 | create a folder                            |
| [more](Cheatsheet-Linux-General.md#more)                   | display the content of a file page by page |
| [mount](Cheatsheet-Linux-General.md#mount)                 | mount a partition                          |
| [ps](Cheatsheet-Linux-General.md#ps)                       | show running tasks                         |
| [pwd](Cheatsheet-Linux-General.md#pwd)                     | print working directory                    |
| [rm](Cheatsheet-Linux-General.md#rm)                       | delete a file                              |
| [rmdir](Cheatsheet-Linux-General.md#rmdir)                 | delete a folder                            |
| [sleep](Cheatsheet-Linux-General.md#sleep)                 | wait                                       |
| [su](Cheatsheet-Linux-General.md#su)                       | change to root                             |
| [systemctl](Cheatsheet-Linux-General.md#systemctl)         | service handler                            |
| [top](Cheatsheet-Linux-General.md#top)                     | task monitor                               |
| [touch](Cheatsheet-Linux-General.md#touch)                 | create a file                              |
| [uname](Cheatsheet-Linux-General.md#uname)                 | show linux details                         |
| [user_reboot](Cheatsheet-Linux-General.md#user_reboot)     | reboot the system                          |
| [user_shutdown](Cheatsheet-Linux-General.md#user_shutdown) | shutdown the system                        |
| [vi](Cheatsheet-Linux-General.md#vi)                       | texteditor                                 |
| [watch](Cheatsheet-Linux-General.md#watch)                 | repeat periodic a command                  |
| [which](Cheatsheet-Linux-General.md#which)                 | locate command                             |

## [IGELOS-General](Cheatsheet-IGELOS-General.md)

| command         | description                              |
|-----------------|------------------------------------------|
| apparmor_status | Lists all services protected by apparmor |
| applauncher                                       | Starts the application launcher                             |                                                                                                                                                            |
| curl https://fqdn.of.website                | Command line tool to check for trusted certificate |
| df -h                                       | Shows Partition usage                              |
| florence                                    | OnScreen Keyboard                                  |
| getmyip                                           | cut -d. -f1-4                                               | show device IP only.                                                                                                                                       |
| gpicview                                          | Starts an Picture Viewer                                    |                                                                                                                                                            |
| icaconncenter                                     | ICA Connection Center                                       |                                                                                                                                                            |
| icg-config -s cloud-gateway.info -o 1234          | IGEL Cloud Gateway config; with url and mass deployment key |                                                                                                                                                            |
| icg-setup                                         | Start the ICG GUI Setup or with parameters the CLI          |                                                                                                                                                            |
| igel_buddy_update_server_scan                     | Search for Buddy Masters in network                         |                                                                                                                                                            |
| igel_display_switcher                             | Start the new Display Switcher                              |                                                                                                                                                            |
| igel_firstboot_wizard                             | Starts the First Boot Wizard                                |                                                                                                                                                            |
| igel_gamma                                        | TOCHECK Should influence the brightness                     |                                                                                                                                                            |
| journalctl -f                                     | Sys logs anzeigen und folgen.                               |                                                                                                                                                            |
| killwait_postsetupd                               | reset and applay setup changes set by "setparam"            |                                                                                                                                                            |
| [kinit](Cheatsheet-IGELOS-General.md#kinit) | Active Directory login                             |
| [klist](Cheatsheet-IGELOS-General.md#klist) | Display kerberos tickets                           |
| nmcli radio wifi off                              | Disables Wifi, On enables it                                |                                                                                                                                                            |
| notify-send-message                               | Display GUI Text Message                                    |                                                                                                                                                            |
| opensc-tool                                       | Lists opensc smartcard informations and tools               |                                                                                                                                                            |
| pkcs11getloginname                                | Shows extracted smart card login name                       |                                                                                                                                                            |
| setcryptparam                                     | Saves encrypted Data like Password to Igel Registry         |                                                                                                                                                            |
| setusercryptparam                                 | Saves User encrypted Data like Password to Igel Registry    |                                                                                                                                                            |
| start-wireless-manager                            | Starts the Wireless cafe menu (start as user)               |                                                                                                                                                            |
| systemd-resolve --flush-caches                    | Flush DNS cache                                             |                                                                                                                                                            |
| user_reboot                                       | Reboot as user                                              |                                                                                                                                                            |
| user_shutdown                                     | Shutdown as User                                            |                                                                                                                                                            |
| write_rmsettings                                  | Write local setup changes back to UMS.                      |                                                                                                                                                            |
| xfce4-display-settings                            | Start the old Display Switcher as binary                    |                                                                                                                                                            |
| xrandr                                            | Controls the Screens from command line                      |                                                                                                                                                            |
| zenity                                            | Dialog select item                                          | `zenity --list --text "Please select a Citrix  Server" --radiolist -column "Select" --column "Server" Storefront1 "Storefront1" Storefront2 "Storefront2"` |
| zenity                                            | Dialog with progress bar                                    | `zenity --progress --text="Trying to ping 4 times" --percentage="0" --auto-close & ping -c 4`                                                              |
| /config/bin/firmware-update | Start firmware update |
| custompart | Delete/Create a custom partition |
| ums_available  | Check available UMS Server       |
| rmregister     | Start tool to register @ UMS     |
| rmagent_cli    | UMS Agent commandline            |
| get_rmsettings | Get UMS config (reboot to apply) |
| setup             | Start IGEL Setup                 |                                                               |
| get               | Get Variable from registry       |                                                               |
| vget              | Get specification for a variable |                                                               |
| setparam          | Write variable to registry       | `setparam system.remotemanager.ums_structure_tag "Building1"` |
| setcryptparam     | Write a password to the registry |                                                               |
| list              | List a part of the registry      |                                                               |
| delinstance       | Delete a session or instance     |                                                               |
| newinstace        | Create a session or instance     |                                                               |
| numinstances      | Show next available instance nr. |                                                               |
| superclasses      | List all available superclasses  |                                                               |
| store_usbconfig   | Write config to USB Storage      |                                                               |
| load_usbconfig    | Load config from USB Storage     |                                                               |
| show_usbconfig    | List configs from USB Storage    |                                                               |
| reset_to_defaults | Factory reset                    |                                                               |
| get_unit_id       | Get the Unit ID                  | `get_unit_id -m` reset the original Unit-ID                   |

## [IGELOS-Networking](Cheatsheet-IGELOS-Networking.md)

| command                                                                                | description                                                                                             |
|----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| [ping](Cheatsheet-IGELOS-Networking.md#ping)                                           | test the reachability of a host                                                                         |
| [/etc/init.d/network-manager](Cheatsheet-IGELOS-Networking.md#etcinitdnetwork-manager) | manage network service                                                                                  |
| [ftp](Cheatsheet-IGELOS-Networking.md#ftp)                                             | start the FTP client                                                                                    |
| [netstat](Cheatsheet-IGELOS-Networking.md#netstat)                                     | display open connections                                                                                |
| [hostname](Cheatsheet-IGELOS-Networking.md#hostname)                                   | display current hostname                                                                                |
| [route](Cheatsheet-IGELOS-Networking.md#route)                                         | display/config network routes                                                                           |
| [iptables](Cheatsheet-IGELOS-Networking.md#iptables)                                   | firewall configuration                                                                                  |
| [probeport](Cheatsheet-IGELOS-Networking.md#probeport)                                 | test network port on a host                                                                             |
| [nmcli](Cheatsheet-IGELOS-Networking.md#nmcli)                                         | manage network connections via cli                                                                      |
| [ifconfig](Cheatsheet-IGELOS-Networking.md#ifconfig)                                   | show/manage ethernet configuration                                                                      |
| [ethtool](Cheatsheet-IGELOS-Networking.md#ethtool)                                     | tool for ethernet configuration                                                                         |
| [getmyhwaddr](Cheatsheet-IGELOS-Networking.md#getmyhwaddr)                             | show current MAC                                                                                        |
| [iwconfig](Cheatsheet-IGELOS-Networking.md#iwconfig)                                   | configure a wireless network interface                                                                  |
| [getmyip](Cheatsheet-IGELOS-Networking.md#getmyip)                                     | show current IP address                                                                                 |
| [iwgetid](Cheatsheet-IGELOS-Networking.md#iwgetid)                                     | report ESSID, NWID or AP/Cell Address of wireless network                                               |
| [iwlist](Cheatsheet-IGELOS-Networking.md#iwlist)                                       | display some additional information from a wireless network interface that is not displayed by iwconfig |
| [iwevent](Cheatsheet-IGELOS-Networking.md#iwevent)                                     | display wireless events                                                                                 |
| [iwspy](Cheatsheet-IGELOS-Networking.md#iwspy)                                         | get wireless statistics from specific nodes                                                             |

## [IGELOS-Hardware](Cheatsheet-IGELOS-Hardware.md)

| command                                              | description                         |
|------------------------------------------------------|-------------------------------------|
| [dmidecode](Cheatsheet-IGELOS-Hardware.md#dmidecode) | DMI (SMBIOS) table decoder          |
| [lsusb](Cheatsheet-IGELOS-Hardware.md#lsusb)         | list USB devices                    |
| lspci                                                | List PCI devices                    |
| rtcwake                                              | Automatic restart/supend            |
| speaker-test                                         | Speaker test                        |
| aplay                                                | Audio device tool                   |
| x11config                                            | Show display config                 |
| get-edid                                             | Display DDC details                 |
| saned                                                | SANE Daemon                         |
| hardinfo                                             | Display Hardware Info's             |
| setserial                                            | Setup/Diagnostic for RS232          |
| amixer                                               | Audio configuration tool            |
| free                                                 | Show memory details                 |
| pcsclistreaders                                      | List Smart Card readers             |
| /etc/init.d/pcscd                                    | Stop / Start Smart Card PCSC Daemon |
| opensc-explorer                                      | Show available  Smart Cardeaders    |
| opensc-tool                                          | Commandline  Smart Card Tool        |

## IGELOS-Folders

| folder                    | description                      |
|---------------------------|----------------------------------|
| /license/dsa/licenses     | device licenses                  |
| /media                    | Removable Storage                |
| /services                 | License related services         |
| /userhome/.ICAClient/logs | ICA Client logs                  |
| /usr/share/icons          | Contains Icons of Linux and Igel |
| /var/logs                 | Various log files                |
| /wfs                      | Configurations / Certs           |

## IGELOS-Files

| file                  | description                              |
|-----------------------|------------------------------------------|
| /config/sessions      | Generated sessions                       |
| /tmp/wpa_debug.all    | network debug log                        |
| /wfs/dhclient-*.lease | dhcp client lease; DHCP Option 224 + 226 |
| /wfs/group.ini        | Configuration from UMS                   |
| /wfs/server.crt       | UMS Server certificate                   |
| /wfs/setup.ini        | Local configuration                      |

## IGELOS-Keybindings

| keybinding   | description            |
|--------------|------------------------|
| ALT+CTRL+TAB | Switch active window   |
| TAB+TAB      | Show commands          |
| ALT+CTRL+Fx  | Switch between console |
| CTRL+ALT+F11 | terminal 1             |
| CTRL+ALT+F12 | terminal 2             |
| CTRL+ALT+F1  | IGELOS UI              |

## IGELOS-Registry

| Path                                             | description |
|--------------------------------------------------|-------------|
| network.interfaces.wirelesslan.device0.wpa.debug | wifi debug  |

## UMS-Files

| file                                                 | description                                                                                                                                                                          |
|------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| api.log                                              | IMI interface log                                                                                                                                                                    |
| catalina.log(.yyyy-mm-dd)                            | UMS log                                                                                                                                                                              |
| localhost.log(.yyyy-mm-dd)                           | Tomcat log                                                                                                                                                                           |
| communication.log                                    | communication between devices and UMS server / UMS console and UMS server log; empty / deactivated by default, has to be activated in log4j.properties; can be very huge when active |
| usgcommunication.log(.x)                             | communication between devices and ICG / UMS console and ICG log; empty / deactivated by default, has to be activated in log4j.properties; can be very huge when active               |
| license_deployment.log                               | ALD log                                                                                                                                                                              |
| stdout.log                                           | like catalina.log but only since last server start                                                                                                                                   |
| stderr.log                                           | JVM error output log; critical VM messages                                                                                                                                           |
| umsthreaddump                                        | UMS ThreadDump                                                                                                                                                                       |
| igel-ums-admin.log                                   | UMS Administrator log                                                                                                                                                                |
| install.log                                          | UMS installation log                                                                                                                                                                 |
| ERP_PROCESS.log                                      | support information                                                                                                                                                                  |
| ERP_PROCESS_INFOS.log                                | support information                                                                                                                                                                  |
| Environment.txt                                      | support information                                                                                                                                                                  |
| thread_dump_start.\*                                 | support information                                                                                                                                                                  |
| thread_dump_end.\*                                   | support information                                                                                                                                                                  |
| network.interfaces.ethernet.devices%.ieee8021x.debug | 802.1x debug                                                                                                                                                                         |