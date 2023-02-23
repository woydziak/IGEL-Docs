# HOWTO UCC

## This document replaced by:

# [IGEL OS UCC Configuration Guide](http://files.igelcommunity.com/igelos_ucc_guide.pdf)

-----

## Citrix with the Jabra Evolve 20 to enable the call button on the headset:

Setup call button on Jabra Evolve 20 with Native USB Redirection enabled via following device rule:

```
Rule=Connect, VID= 0B0E, PID=0300, extra config = split=1 intf=03
  ```

-----

## Cisco Webex Meetings VDI Optimization

There have been some changes with Webex Meetings VDI, and now instead of using a separate installer for Webex Meetings, they are now bundled.

In short, if you are using Webex VDI (Teams), and Webex Meetings VDI, and want both to be optimized, make sure to use the bundle installer from here.

https://www.webex.com/downloads/teams-vdi.html

This is the latest version of the documentation:

https://www.cisco.com/c/en/us/td/docs/voice_ip_comm/cloudCollaboration/wbxt/vdi/wbx-teams-vdi-deployment-guide/wbx-teams-vdi-deployment_chapter_010.html#id_127338

### Auto-upgrade disabled:

VDI client in a persistent VDI setting with autoupgrade disabled

`msiexec /i c:\users\[username]\Downloads\WebexBundle.msi ALLUSERS=1 ENABLEVDI=2 AUTOUPGRADEENABLED=0 FORCELOCKDOWN=NeverUpdate`

VDI client in a non-persistent VDI setting with autoupgrade disabled

`msiexec /i c:\users\[username]\Downloads\WebexBundle.msi ALLUSERS=1 ENABLEVDI=2 AUTOUPGRADEENABLED=0 ROAMINGENABLED=1 FORCELOCKDOWN=NeverUpdate`

-----

## Cisco Webex Meetings VDI & Cisco Webex App VDI Compatibility Lists

Compatibility lists for Cisco Webex Meetings VDI & Cisco Webex App VDI:

https://help.webex.com/en-us/article/glj57y/Webex-Meetings-Virtual-Desktop-Infrastructure-release-notes#Cisco_Reference.dita_fcb4e1d7-dbef-4bab-8842-9b1a8f84a9e5

https://help.webex.com/en-us/article/ntp1us7/Webex-App-%7C-VDI-release-notes#Cisco_Reference.dita_13d9aace-b6f9-41dc-a6e0-9f7a48834060

### Steps to automatically update
 
 **Must** keep up the race to stay on latest version of IGEL OS so as to not fall out of sync with backend releases as noted in links above.

 For example, when the latest version was 43.5, then [IGEL OS 11.08.248](https://github.com/IGEL-Community/IGEL-Docs/blob/main/Docs/ReleaseNotes/01-OS11/readme11.08.248.txt) is needed since it includes the plugin for Cisco Webex Meetings VDI plugin 42.10.

-----

## [Citrix HDX Webcam redirection for 64-bit applications. HowTo guide!](https://virtualbrat.com/2023/02/23/citrix-hdx-webcam-redirection-for-64-bit-applications-how-to-guide/)

-----