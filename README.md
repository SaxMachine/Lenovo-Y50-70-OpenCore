# Catalina or lower installation with OpenCore 0.5.9 #

**Specs:**
  - Intel Core i7-4710HQ -- [Product Page](https://ark.intel.com/content/www/us/en/ark/products/78930/intel-core-i7-4710hq-processor-6m-cache-up-to-3-50-ghz.html)
  - Intel HD4600 iGPU
  - Nvidia GTX 860M 4GB (unsupported)
  - 16GB DDR3 Ram
  - Realtek RTL8723BE Wifi Card - Replaced with a Broadcom BCM43xx WiFi Card
  - Replacing the WiFi Card needs a modified BIOS due to Blacklisting non-OEM Cards



**What you need:**

- Lenovo Y50-70 (or Y70) with either 1080p or UHD/4K display
- macOS or OS X downloaded from the Mac App Store
- 8GB USB stick with EFI folder pre-installation on EFI Partition and MacOSX installation.
- Broadcom BCM94352Z for native WiFi (Lenovo FRU: 04X6020, Lenovo PN: 20-200480) or MacOS Broadcom compatible model with BIOS unlock.

**What works:**

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

**Not tested/not working:**

The following features have issues, or have not been tested:
- Nvidia GTX 860M 4GB
- card reader is not working


**BIOS settings:**

To start, set BIOS to Windows 8 defaults.

Then insure:
- UEFI boot is enabled
- secure boot is disabled
- enable Legacy Boot (but UEFI first) and you may experience less boot time glitches

**For the UHD model, the DVMT-prealloc BIOS setting must be changed to 128MB. One of two methods can be used:**
- use a EFI shell to change the DVMT-prealloc from the shell.
- use a patched BIOS which unlocks the advanced menu

**What you have to do:**
 
- Install MacOS with pre-installation EFI
- copy EFI post-installation folder on EFI partition of your HD.
- Modify SMBIOS data with your information:
  You have to import from your older configuration or generate a new one
  
  Data that you have to modify on Config.plist/Platforminfo/Generic with PlistEditorPro or other text editor.
  
  ![PliseditorPRO](https://raw.githubusercontent.com/SaxMachine/Lenovo-Y50-70-OpenCore/master/1.png)
Format: ![Alt Text](url)

  
 
  
  	


 
**Post installation commands to do**

- sudo pmset -a hibernatemode 0
- sudo rm /var/vm/sleepimage
- sudo mkdir /var/vm/sleepimage

**Credits:**

Rehabman
https://www.tonymacx86.com/threads/guide-lenovo-y50-uhd-or-1080p-using-clover-uefi.261723/


Xsiry
https://github.com/xsiry/Lenovo-Y50-Hackintosh-OC/blob/master/README.md
