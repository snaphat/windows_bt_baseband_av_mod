# windows_bt_baseband_av_mod

Description
-

[Baseband](https://www.bluetooth.com/specifications/assigned-numbers/baseband/) modification for Windows to switch the Major Device Class to Audio/Video.

This registry modification switches Windows 10 to present itself as an Audio/Video device. This can be useful for bluetooth audio transmitters that refuse to pair to anything but devices that identify their main function as Audio/Video to enable these devices to stream Audio to Windows 10 (Note: [Windows 10 version 2004](https://docs.microsoft.com/en-us/windows/whats-new/whats-new-windows-10-version-2004) or higher is required for [remote playback](https://docs.microsoft.com/en-us/windows/uwp/audio-video-camera/enable-remote-audio-playback)).

Installation
-
Download [audio_video_bt.reg](https://raw.githubusercontent.com/snaphat/windows_bt_baseband_av_mod/master/audio_video_bt.reg):
1. Right-click the link and Select *Save target as* or *Save link as*:
2. Then run the file to add the modifications to your Windows Registry.

Uninstallation
-
Download [audio_video_bt_del.reg](https://raw.githubusercontent.com/snaphat/windows_bt_baseband_av_mod/master/audio_video_bt_del.reg):
1. Right-click the link and Select *Save target as* or *Save link as*:
2. Then run the file to add the modifications to your Windows Registry.

Known Devices that Benefit
-
* HomeSpot Bluetooth 5.0 Audio Transmitter Adapter with USB C Connector

Additional Notes
-
The same type of baseband modification will work for Linux's bluetooth stack as well. But, I was unable to get the Linux A2DP sink role to work reliably during my testing with Linux.


