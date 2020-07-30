# High Sierra and Catalina installation with OpenCore 0.5.9
## Resources for creating a Hackintosh Installation for Lenovo Y50-70
**Specs:**
  - Intel Core i7-4710HQ -- [Product Page](https://ark.intel.com/content/www/us/en/ark/products/78930/intel-core-i7-4710hq-processor-6m-cache-up-to-3-50-ghz.html)
  - Intel HD4600 iGPU
  - Nvidia GTX 860M 4GB (Mojave and higher unsupported)
  - 16GB DDR3 Ram
  - Realtek RTL8723BE Wifi Card - Replaced with a Broadcom BCM43xx WiFi Card
  - Replacing the WiFi Card needs a modified BIOS due to Blacklisting non-OEM Cards



What you need

- Lenovo Y50-70 (or Y70) with either 1080p or UHD/4K display
- macOS or OS X downloaded from the Mac App Store
- 8GB USB stick with EFI folder pre-installation on EFI Partition and MacOSX installation.
- Broadcom BCM94352Z for native WiFi (Lenovo FRU: 04X6020, Lenovo PN: 20-200480) or MacOS Broadcom compatible model with BIOS unlock.

What works

Expect to work:
- built-in keyboard (with brightness keys)
- built-in trackpad (multi gestures)
- HDMI video/audio with hotplug
- AirPlay mirroring to AppleTV
- native WiFi via BCM94352Z
- Bluetooth (with handoff) using BCM94352Z
- native USB3
- native audio with AppleHDA
- built-in mic
- built-in camera
- native power management
- battery status
- backlight controls with smooth transitions, save/restore across restart
- accelerated graphics for HD4600 including OpenCL
- wired Ethernet
- retina scaling (in the case of UHD screen)

Not tested/not working

The following features have issues, or have not been tested:
- Nvidia GTX 860M 4GB
- card reader is not working


BIOS settings

To start, set BIOS to Windows 8 defaults.

Then insure:
- UEFI boot is enabled
- secure boot is disabled
- enable Legacy Boot (but UEFI first) and you may experience less boot time glitches
 
Install MacOS with pre-installation EFI and then copy EFI post-installation folder on EFI partition of your HD, unzip Resources folder into the same folder.
 
Post installation commands to do

- sudo pmset -a hibernatemode 0
- sudo rm /var/vm/sleepimage
- sudo mkdir /var/vm/sleepimage

Credits:

Rehabman
https://www.tonymacx86.com/threads/guide-lenovo-y50-uhd-or-1080p-using-clover-uefi.261723/


Xsiry
https://github.com/xsiry/Lenovo-Y50-Hackintosh-OC/blob/master/README.md
