# HP-840-G1-BigSur-Clover-EFI
EFI folder for booting BigSur On HP 840 G1

OpencCore-HP-840-G1-Haswell
This HP Elitebook 840 G1 EFI configuration is based on, Dortania's OpenCore Install Guide, and RehabMan's HP guide. This is also really useful.

Hardware:
CPU: Intel(R) i5-4300U (Haswell)
SSD: Samsung SSD 860 EVO 500GB
RAM: 8GB DDR3
DISPLAY: 1600x900 (Touchscreen)
GPU: Integrated, Intel HD Graphics 4400
AUDIO CODEC: IDT92HD91BXX
ETHERNET: Intel I218-LM
WIFI: Intel Dual Band Wireless-N 7260NB 802.11 a/b/g/n (2 x2 ) WiFi // It's not compatible
AR9285 works great .

BIOS Settings:
Spam the F10 key
Disable

Fast Boot
Secure Boot
Serial/COM Port
Disable wake on USB
Parallel Port
VT-d (can be enabled if you set DisableIoMapper to YES)
CSM
Thunderbolt(For initial install, as Thunderbolt can cause issues if not setup correctly)
Intel SGX
Intel Platform Trust
CFG Lock (This must be off, otherwise your hack will not boot with CFG-Lock enabled) if you can't find the option then enable AppleXcpmCfgLock under:
      Kernel -> Quirks -> AppleXcpmCfgLock=True
Enable

VT-x
Above 4G decoding
Hyper-Threading
Execute Disable Bit
EHCI/XHCI Hand-off
OS type: Windows 8.1/10 UEFI Mode
DVMT Pre-Allocated(iGPU Memory): 64MB
SATA Mode: AHCI
Note: Most of these options may not be present in your firmware, we recommend matching up as closely as possible but don't be too concerned if many of these options are not available in your BIOS.

Save and reboot in UEFI.

What Works:
UEFI booting via OpenCore
Dual Boot with Windows/Linux
Built-in keyboard (with special function keys)
Built-in trackpad (Multi-Gestures)
Native WiFi & Bluetooth via Broadcom DW1560 BCM4352
HDMI Audio/Video with hot-plug
Native USB3 with AppleUSBXHCI using USBMap (USB2 works also)
Native audio, including headphone
Built-in mic
Built-in camera
Native power management
Battery status
Backlight controls with smooth transitions
Accelerated graphics Intel HD Graphics 4400
Wired Ethernet
App Store
iMessage & Facetime
Notes:
For Wifi and Bluetooth you have to replace your Wifi half mini PCI card to something that is supported by Apple. The HP-840-G1 doesn't have a Wifi whitelist, so in theory every card should work, but it has to be compatible with MacOS. I replaced it with a Broadcom DW1560 BCM4352 and worked Out of the Box, probably with the already installed kexts.

In order to use iMessage and Facetime you need to change your SMBIOS, with GenSMBIOS. https://github.com/corpnewt/GenSMBIOS

Credit:
Apple for MacOS
vit9696 for OpenCore
Dortania's Guide for OpenCore Install
InsanelyMac's OpenCore forums for finding issues with hardware and their work arounds
RehabMan for DSDT-Patches
blint01 for Clover configuration guide
hackintosh-forum.de for their updates with HP 840 G1  at https://www.hackintosh-forum.de/forum/thread/46626-hp-elitebook-840-g1-opencore-catalina-big-sur/?pageNo=1
insanelymac for https://www.insanelymac.com/forum/files/file/1008-io80211family-modif/ and https://www.insanelymac.com/forum/topic/346111-openccore-hp-840-g1-haswell-big-sur-success/

