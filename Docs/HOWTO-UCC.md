# HOWTO UCC

## This document replaced by:

# [IGEL OS UCC Configuration Guide](http://files.igelcommunity.com/igelos_ucc_guide.pdf)

## Citrix with the Jabra Evolve 20 to enable the call button on the headset:

Setup call button on Jabra Evolve 20 with Native USB Redirection enabled via following device rule:

```
Rule=Connect, VID= 0B0E, PID=0300, extra config = split=1 intf=03
  ```
