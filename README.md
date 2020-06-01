# windows_bt_baseband_av_mod

Description
-

[Baseband](https://www.bluetooth.com/specifications/assigned-numbers/baseband/) modification for Windows to switch the Major Device Class to Audio/Video.

This [registry modification](https://docs.microsoft.com/en-us/windows-hardware/drivers/bluetooth/bluetooth-registry-entries) switches Windows 10 to present itself as an Audio/Video device. This can be useful for bluetooth audio transmitters that refuse to pair to anything but devices that identify their main function as Audio/Video to enable these devices to stream Audio to Windows 10 (Note: [Windows 10 version 2004](https://docs.microsoft.com/en-us/windows/whats-new/whats-new-windows-10-version-2004) or higher is required for [remote playback](https://docs.microsoft.com/en-us/windows/uwp/audio-video-camera/enable-remote-audio-playback)).

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
* The *COD Major* and *COD Type* registry entries don't appear to behave exactly as documented by Microsoft. I surmise that these entries have rarely been utilized as of this writing since they appear to be buggy.
  * COD Major entry appears to be ignored if COD Type entry exists.
  * COD Type will actually result in bits 8 and bit 9 of the baseband (part of the Major Device Class) being set if the registry entry is a value above 7F (hex) and below 100 (hex). COD Type is suppose to only set the Minor Device Class according to the documentaiton.
  * COD Type values higher than FF (hex) (an invalid number) will result in COD minor class being set to 0, not 1 (COD_COMPUTER_MINOR_DESKTOP) as MS indicates in the documentation. 
* Android applications that display COD can be used to aid in debugging which type is returned for which value.
* The same type of baseband modification will work for Linux's bluetooth stack as well. But, I was unable to get the Linux A2DP sink role to work reliably during my testing with Linux.


