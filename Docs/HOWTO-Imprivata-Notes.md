# HOWTO Imprivata Notes

## Collect Imprivata Log Files

-----

### Where are the log files?

The the log files for Imprivata ProveID Embedded agent are located in:

```
/.imprivata_data_runtime/log
   ```

**NOTE: Need to be root to access**  

-----

### Steps to collect the log files (as root)

 ```
#!/bin/bash
# Need to be run as root

/services/imprivata/bin/fetch_support_info /tmp/imprivata_logs_$(date +%y%m%d%H%M).zip
   ```

-----

## Change Imprivata ReadTimeout and WriteTimeout

-----

### Steps to change ReadTimeout and WriteTimeout

Edit Imprivata.conf file to reduce the Failovertime from 8 minutes to one minute.

Create a profile and add the following command to custom commands - Desktop - Before desktop starts:

```bash
sed '/\[agent\]/i [mainloader.SSL]\nReadTimeout=15\nWriteTimeout=15\n ' /usr/lib/imprivata/runtime/etc/Imprivata.conf
   ```

**Note:** A reboot is required after applying profile
