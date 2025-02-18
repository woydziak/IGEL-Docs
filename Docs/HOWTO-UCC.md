# HOWTO UCC

# [IGEL OS UCC Configuration Guide](http://files.igelcommunity.com/igelos_ucc_guide.pdf)

-----

# Addendum to UCC Guide

-----

## UCC Hardware Requirements

| UCC Type | Hardware Limits | Link to Vendor |
|----------|-----------------|----------------|
| Zoom VDI - ANY (Citrix / Horizon / AVD) | Dual Core `<` 2GHz base clock = LIMITED to 9 video streams <br /> Dual Core AMD chips with `2x` in name = LIMITED to 6 video streams <br /> Dual Core `>=` 2GHz clock (or Intel i5/i7 `<` 2GHz) = 25 video streams <br /> Quad Core or higher (any clock speed) = 25 video streams | [Zoom VDI Client Hardware Requirements](https://support.zoom.us/hc/en-us/articles/4404773645069-Calculating-video-streams-for-VDI-clients) |
| MS Teams VDI (Citrix) | Dual Core `>=` 1.8GHz base clock speed for 720p 1:1 call <br /> Dual or Quad Core `>=` 1.8GHz with 2.9GHz boost for many:many call | [Teams VDI for Citrix Client Hardware Requirements](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html#:~:text=Citrix%20Workspace%20app%20requires%20at,2.) |
| MS Teams VDI (Horizon) | Dual Core `>=` 2.4GHz base clock speed | [Teams VDI for Horizon Client Hardware Requirements](https://docs.vmware.com/en/VMware-Horizon/2212/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html) |
| MS Teams VDI (AVD) | Dual Core `>=` 1.6GHz base clock speed <br /> 4GB of Available memory | [Teams VDI for AVD Client Hardware Requirements](https://learn.microsoft.com/en-us/microsoftteams/hardware-requirements-for-the-teams-app#hardware-requirements-for-teams-on-linux) |
| Webex VDI - ANY (Citrix / Horizon / AVD not yet available) | Any 64-bit x86 + 2GB RAM | [Webex VDI Client Hardware Requirements](https://www.cisco.com/c/en/us/td/docs/voice_ip_comm/cloudCollaboration/wbxt/vdi/wbx-vdi-deployment-guide/wbx-teams-vdi-deployment_chapter_01.html#Cisco_Reference.dita_02ec38ca-aa77-4ae5-967f-03af2d3f22ef) |

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