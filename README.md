# Opencore Ventura EFI - i5-13600K, RX6800, NZXT N5 Z690 Motherboard

This is built on the work of many others, too numerous to mention, thanks to all, and I am sharing this back with the community. It is triple-booting on a system shared with Windows 10, Linux (PopOS using BTRFS filesystem).

## Hardware tested

- Motherboard: [NZXT N5 Z690](https://nzxt.com/en-GB/product/n5-z690) (with Resize Bar/Above 4G Enabled)
- CPU: Intel i5-13600K
- Graphics Card: AMD RX 6800 XT
- Wireless/Bluetooth: Intel Built-in CNVIO AX211

Everything is OK, except sleep.

## Notes

- `config.plist` is excluded, you need to copy the example `config-intel-nzxt-z690.plist` and replace the asterisks with generated valid ROM etc values from an SMBIOS for MacPro7,1
- Using P-Cores and E-Cores you'll need to change the boot-args  from "-ctrsmt 6c20t" (6-cores 20-threadsd) if you've a different CPUs.  Basically this ensures that performance is maximised, or all P-cores will be downclocked to E-core speed.

## Help

Don't create issues asking, but do send patches and pull requests for improvements! For self-help. refer to:

- [OpenCore Configurator ](]https://mackie100projects.altervista.org/)
- [Dortania Guide](https://dortania.github.io/OpenCore-Install-Guide/)

## Scripts

### Setting your computer/hostname

Run

```
scripts/hostname.sh COMPUTERNAME
```

### Constant iCloud/AppStore Popups

If you run into problems with being asked constantly about your iCloud information, try deleting network interfaces and then restarting after typing the following in a terminal:

```
scripts/clear-network-interfaces.sh
```

# Kexts Used

## [Acidanthera (OpenCore Project)](https://github.com/acidanthera)

- [Lilu](https://github.com/acidanthera/Lilu) (Mandatory)
- [VirtualSMC](https://github.com/acidanthera/VirtualSMC) (Required emulate Apple SMC)
- [WhateverGreen](https://github.com/acidanthera/WhateverGreen) (Required for the GPU except if using a non-Intel AMD APU)
- [RestrictEvents](https://github.com/acidanthera/RestrictEvents) - block unwanted processes causing compatibility issues
- [AppleALC](https://github.com/acidanthera/AppleALC) - for in-built audio
- [NVMEFix](https://github.com/acidanthera/NVMeFix) - (optional for fixing NVME issues)
- [CPUFriend](https://github.com/acidanthera/CPUFriend) - dynamic power management data injection
  
  ## Wireless/Networking
- [Intel Bluetooth IntelBTPatcher.kext and IntelBluetoothFirmware.kext](https://github.com/OpenIntelWireless/IntelBluetoothFirmware) with BlueToolFixup.kext from [acidanthera/BrcmPatchRAM](https://github.com/acidanthera/BrcmPatchRAM) - after IntelBTPatcher.kext and before IntelBluetoothFirmware.kext
- [AirportItwlm (use in-built WiFi) or itwlm](https://github.com/OpenIntelWireless/itlwm) with [https://github.com/OpenIntelWireless/HeliPort](HeliPort App) (more stable) 
- [LucyRTL8125Ethernet](https://github.com/Mieze/LucyRTL8125Ethernet) - RealTek 8125 2.5 Gb Ethernet 
  
  ## Other
- [RTCMemoryFixup](https://github.com/acidanthera/RTCMemoryFixup) - CMOS emulation
- [HibernationFixUp](https://github.com/acidanthera/HibernationFixup) - RTC variables sync with NVRAM
- [ECEnabler](https://github.com/1Revenger1/ECEnabler) - Embedded Controller for battery status
- [USBToolBox](https://github.com/USBToolBox/kext) - for mapping USB ports using [USBToolBox/tool](https://github.com/USBToolBox/tool)
- [BrightnessKeys](https://github.com/acidanthera/BrightnessKeys) - Brightness Keys
- [CpuTopologyRebuild](https://github.com/b00t0x/CpuTopologyRebuild) and CPUFriendDataProvider.kext - needed for correct P-Core/E-Core speeds
