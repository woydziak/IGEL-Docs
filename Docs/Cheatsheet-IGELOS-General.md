# Cheatsheet IGELOS General

## apparmor_status

Lists all services protected by apparmor

```bash
apparmor_status
```

```bash
apparmor module is loaded.
18 profiles are loaded.
18 profiles are in enforce mode.
   /sbin/dhclient
...
   /{dev/.mnt-system/ro/,dev/.mnt-system/ro/sys/,}usr/sbin/tcpdump
0 profiles are in complain mode.
8 processes have profiles defined.
7 processes are in enforce mode.
   /sbin/dhclient (12496)
...
   /{dev/.mnt-system/ro/,dev/.mnt-system/ro/sys/,dev/.mnt-system/rw/,dev/.mnt-system/rw/sys/,}services/fbrw/firefox/{,*[^s][^h]} (14061)
0 processes are in complain mode.
1 processes are unconfined but have a profile defined.
   /usr/sbin/haveged (366)
```

## kinit

Active Directory login

```bash

```

```bash

```

## klist

Display kerberos tickets

```bash

```

```bash

```

## getmyip

show device IP

```bash
getmyip && echo
```

```bash
192.168.1.2
```

## get

Read variable from registry

**Read variable system.remotemanager.ums_structure_tag:**

```bash
get system.remotemanager.ums_structure_tag
```

```bash
Building1
```

## setparam

Write variable to registry

**Write variable system.remotemanager.ums_structure_tag with Value Building1:**

```bash
setparam system.remotemanager.ums_structure_tag "Building1"
```

## get_unit_id

Get the Unit ID

**get the Unit-ID:**

```bash
get_unit_id && echo
```

```bash
85641000F615234423
```

**reset the original Unit-ID:**

```bash
get_unit_id -m
```

```bash
Manually set new Unit ID

    0 abort setting Unit ID
    1 UD Pocket Unit ID 85641000F615234423
    2 eth0: Unit ID 002326FC34DE, connected via PCI, wired, has no license
    3 wlan0: Unit ID 002314200E4, connected via PCI, wireless, has no license

Choose number to abort or set new Unit ID:
```

## chromium-browser

Start Chromium browser in App Mode for Citrix Storefront and similar pages - to use with Custom App function

```bash
chromium-browser --app=https://storefront-url.domain.org --start-maximized
  ```

## curl

Check for trusted certificate or download files

**Download script from Github and save it:**

```bash
curl -O https://raw.githubusercontent.com/IGEL-Community/IGEL-Custom-Partitions/master/CP_Source
/Unified_Communications/Zoom/build-zoom-cp.sh
```

```bash
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   982  100   982    0     0   3494      0 --:--:-- --:--:-- --:--:--  3494
```

## icg-config

IGEL Cloud Gateway config; with url and mass deployment key

```bash

```

```bash

```

## vdm_client0

After creating a VMware Horizon session, you can get it to run fully as User from command line with the following command.

```bash
su -c "XDG_RUNTIME_DIR=/run/user/777 /config/sessions/vdm_client0" user &
  ```
