# Opencore Ventura EFI - i5-13600K, RX6800, NZXT N5 Z690 Motherboard

This is built on the work of many others, too numerous to mention, thanks to all, and I am sharing this back with the community. It is triple-booting on a system shared with Windows 10, Linux (PopOS using BTRFS filesystem).

## Hardware tested

- Motherboard: [NZXT N5 Z690](https://nzxt.com/en-GB/product/n5-z690) (with Resize Bar/Above 4G Enabled)
- CPU: Intel i5-13600K
- Graphics Card: AMD RX 6800 XT
- Wireless/Bluetooth: Intel Built-in CNVIO AX210(?)

Everything is OK, except sleep.

## Notes

- `config.plist` is excluded, you need to copy the example `config-intel-nzxt-z690.plist` and replace the asterisks with generated valid ROM etc values from an SMBIOS for MacPro7,1
- Using P-Cores and E-Cores you'll need to change the boot-args  from "-ctrsmt 6c20t" (6-cores 20-threadsd) if you've a different CPUs.  Basically this ensures that performance is maximised, or all P-cores will be downclocked to E-core speed.
- Power monitoring app can be added with [Intel Power Gadget](https://www.intel.com/content/www/us/en/developer/articles/tool/power-gadget.html) although this has expired and you'll need to use their newer tool.
- Long-overdue update (Jul 2024) was for OpenCore 1.0

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
