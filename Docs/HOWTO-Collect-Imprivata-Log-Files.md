# HOWTO Collect Imprivata Log Files

-----

## Where are the log files?

The the log files for Imprivata ProveID Embedded agent are located in:

```
/.imprivata_data_runtime/log
   ```

**NOTE: Need to be root to access**  

-----

## Steps to collect the log files (as root)

 ```
#!/bin/bash
# Need to be run as root

/services/imprivata/bin/fetch_support_info /tmp/imprivata_logs_$(date +%y%m%d%H%M).zip
   ```
