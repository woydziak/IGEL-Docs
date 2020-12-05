# HOWTO Using Webcams in Remote Sessions with IGEL Endpoints

## Enable Webcam in the virtual session (Windows 10)

To open up the webcam or camera, select the **Start button**, and then select **Camera** in the list of apps.

If you want to use the camera within other apps, select the **Start** button, select **Settings > Privacy > Camera**, and then turn on **Let apps use my camera**.

From there, turn on each of the listed apps where you want to use the camera.

## RDP

* USB Redirection
   * [Sessions > RDP > RDP Global > Native USB Redirection](https://kb.igel.com/igelos-11.04/en/native-usb-redirection-32870945.html)
   * [Use Device Rules, instead of just Class Rules](https://kb.igel.com/igelos-11.04/en/issues-with-usb-ids-in-usb-devices-rules-32870642.html)

* Fabulatech USB redirection
   * [Sessions > RDP > RDP Global > Fabulatech USB Redirection](https://kb.igel.com/igelos-11.04/en/fabulatech-usb-redirection-32870946.html)
   * [Use Device Rules, instead of just Class Rules](https://kb.igel.com/igelos-11.04/en/issues-with-usb-ids-in-usb-devices-rules-32870642.html)

* For Microphone (e.g. Headset)
   * Activate = Sessions > RDP > RDP Global > Mapping > Audio > "Audio recording"

## Citrix

* Best choice (less bandwidth) is to make sure Backend is configure to use this channel:
   * [Sessions > Citrix > Citrix Global > Unified Communications](https://kb.igel.com/igelos-11.04/en/unified-communications-32870911.html)

* Second choice configure [HDX](https://kb.igel.com/igelos-11.04/en/hdx-multimedia-32870909.html) for all purposes:
   * Active > Sessions > Citrix > Citrix Global > HDX Mutimedia > "Multimedia Redirection"
   * Active > Sessions > Citrix > Citrix Global > HDX Mutimedia > "HDX RealTime Webcam redirection"
   * Unmark > Sessions > Citrix > Citrix Global > HDX Multimedia > "HDX RealTime Media Engine", if you DO NOT use Lync/Skype with RTME in your Backend.
   * If you use “HDX RealTime Media Engine” for Lync/Skype, unmark > Sessions > Citrix > Citrix Global > HDX Multimedia > “HDX RealTime Webcam redirection”

* Third choice
   * USB Redirection [How to Configure Citrix Native USB Redirection](https://kb.igel.com/igelos-11.04/en/how-to-configure-citrix-native-usb-redirection-32869720.html)
   * Fabulatech USB Redirection [Sessions > Citrix > Citrix Global > Fabulatech USB Redirection](https://kb.igel.com/igelos-11.04/en/fabulatech-usb-redirection-32870907.html)
   * [Issues with USB IDs in USB Device Rules](https://kb.igel.com/igelos-11.04/en/issues-with-usb-ids-in-usb-devices-rules-32870642.html)

## VMware Horizon

   * USB Redirection [Sessions > Horizon Client > Horizon Client Global > USB Redirection](https://kb.igel.com/igelos-11.04/en/usb-redirection-32870983.html)
   * Fabulatech USB Redirection [Sessions > Horizon Client > Horizon Client Global > Fabulatech USB Redirection](https://kb.igel.com/igelos-11.04/en/fabulatech-usb-redirection-32870984.html)
   * [Issues with USB IDs in USB Device Rules](https://kb.igel.com/igelos-11.04/en/issues-with-usb-ids-in-usb-devices-rules-32870642.html)


***Use ONLY ONE at a time for each device. For example, if you use Native USB redirection, do not use HDX for the same device.***

## Use Native Applications

Use Custom Partitions (CP) to install native Microsoft Teams or Zoom applications that can be called from remote sessions. Using native applications may reduce backend resources (CPU, RAM, network, etc.).

IGEL Community provides the needed content to build Custom Partitions:

   * [IGEL Community Custom Partition Store](https://www.igelcommunity.com/igel-custom-partitions-store)
   * [IGEL Community Custom Partition GitHub](https://github.com/IGEL-Community/IGEL-Custom-Partitions)

Another option is to create an IGEL Support ticket and ask for the Custom Partition for native application.

## Webcams

We have seen good experience with Logitech (such as C930e) and Microsoft webcams, even though most webcams will work with IGEL OS.

## Training Videos

* [Master your USB devices with Remote Desktops (english)](https://www.youtube.com/watch?v=PYCU1AEfS-g&feature=youtu.be)
* [Bringen Sie Ihre USB Geräte unter Kontrolle (deutsch)](https://youtu.be/caNhFib5cuA)
