# Update Lenovo Bios on Linux

If [fwupd](https://github.com/fwupd/fwupd) does not work with the device or install, it is still possible to update the firmware using Linux.

This guide was written from the perspective an Arch Linux user with a T14s Gen 1 on 2024-26-12.

## Steps

1. Download iso from your product support site under the BIOS/UEFI section:
   - [Product Search](https://pcsupport.lenovo.com/us/en)
   - [Example](https://pcsupport.lenovo.com/us/en/products/laptops-and-netbooks/thinkpad-t-series-laptops/thinkpad-t14s-type-20uh-20uj/20uh/20uhcto1ww/pf2dxjj4/downloads/driver-list/)
1. Convert it to a bootable image: `geteltorito.pl -o bios.img <iso path>`.
   - [AUR Package](https://aur.archlinux.org/packages/geteltorito)
   - [Ubuntu Package](https://launchpad.net/ubuntu/focal/+package/genisoimage): The command may not have the `.pl` suffix.
   - A container can be used if your platform does not have access to this package. Make sure to mount a directory containing the ISO into the container using `-v`.
1. Copy the `bios.img` file to your USB device:
   - [Ventoy](https://www.ventoy.net/en/index.html) for this step.
   - Untested: `dd if=bios.img of=<block device path> bs=8MB status=progress && sync -f <block device path>`.
1. Boot from the USB device and let the BIOS update proceed.
