# Opencore Ventura EFI - i5-13500, RX6800, NZXT N5 Z690 Motherboard

This is built on the work of many others, too numerous to mention, thanks to all, and I am sharing this back with the community. It is triple-booting on a system shared with Windows 10, Linux (PopOS using BTRFS filesystem).

## Hardware tested

- Motherboard: [NZXT N5 Z690](https://nzxt.com/en-GB/product/n5-z690) (with Resize Bar/Above 4G Enabled)
- CPU: Intel i5-13500
- Graphics Card: MSI AMD RX 6800
- Wireless/Bluetooth: Intel Built-in 

Wifi not working, otherwise everything else is OK, including sleep.
 
## Notes

- `config.plist` is excluded, you need to copy the example `config-intel-nzxt-z690.plist` and replace the asterisks with generated valid ROM etc values
- Power monitoring app can be added with [Intel Power Gadget](https://www.intel.com/content/www/us/en/developer/articles/tool/power-gadget.html)

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

