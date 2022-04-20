# HOWTO Microsoft Teams Optimization

# [IGEL OS UCC Configuration Guide](http://files.igelcommunity.com/igelos_ucc_guide.pdf)
-----

## How to Check communication to the Microsoft API URLs and IPs?

If Microsoft Teams is not running in optimized mode, then check that the IGEL endpoint can communicate with the Microsoft API URLs and IPs?

Run the following script in a local terminal window on IGEL endpoint:

```bash
#!/bin/bash

nc -u -v -z 13.107.64.21 3478-3481
nc -u -v -z 52.112.0.31 3478-3481
nc -u -v -z 52.120.0.41 3478-3481
nc -v -z teams.microsoft.com 80
nc -v -z teams.microsoft.com 443
nc -v -z compass-ssl.microsoft.com 443
nc -v -z mlccdnprod.azureedge.net 443
nc -v -z aka.ms 443
  ```
