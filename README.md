**Make sure to rename your EFI folder of choice to just 'EFI'! Otherwise it will not boot!**

Contains various EFI folders needed to boot macOS versions Ventura and Sonoma on your Thinkpad T440p. 

There are two EFI folders for Sonoma, with the only difference between them being airportitlwm.kext. You can find these under the 'EFIs - Sonoma' folder. This is because the airportitlwm kext for 14.0 to 14.3.1 will not work on 14.4 and above. iServices like iMessage won't work. YMMV, but using itlwm instead may fix these issues.

The SMBIOS you generate will depend on the version you choose to install. My tool of choice is [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS). If you are using Sonoma, generate an SMBIOS for MacBookPro16,1. If you are using Ventura, generate an SMBIOS for MacBookPro14,1. This is because the USB maps are for different SMBIOSes. If you want to use a different SMBIOS, you can modify the info.plist in USBMap.kext. You will also need to edit the PlatformInfo -> Generic -> ROM section in the config.plist file with your MAC address (without the dashes). 

Airportitlwm hasn't been released for macOS Sequoia yet, so there is no Sequoia EFI (yet).

The SD card reader will not work as I haven't found a compatible kext

Use [OCPL](https://github.com/dortania/OpenCore-Legacy-Patcher) to make your experience usable, as Sonoma and Ventura don't support Haswell igpus

ACPI patches by [valnoxy](https://github.com/valnoxy)

Opencore version: 1.0.4
