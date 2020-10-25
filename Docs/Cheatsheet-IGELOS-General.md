# IGELOS General

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

**:**

```bash
cut -d. -f1-4
```

```bash

```

## zenity

dialogue

**Dialog select item:**

```bash
zenity --list --text "Please select a Citrix  Server" --radiolist -column "Select" --column "Server" Storefront1 "Storefront1" Storefront2 "Storefront2"
```

```bash

```

**Dialog with progress bar:**

```bash
zenity --progress --text="Trying to ping 4 times" --percentage="0" --auto-close & ping -c 4
```

```bash

```

## setparam

Write variable to registry

**:**

```bash
setparam system.remotemanager.ums_structure_tag "Building1"
```

```bash

```

## get_unit_id

Get the Unit ID

**reset the original Unit-ID:**

```bash
get_unit_id -m
```

```bash

```

## curl

Command line tool to check for trusted certificate

**:**

```bash
curl https://fqdn.of.website
```

```bash

```

## icg-config

IGEL Cloud Gateway config; with url and mass deployment key

**:**

```bash
icg-config -s cloud-gateway.info -o 1234 
```

```bash

```

