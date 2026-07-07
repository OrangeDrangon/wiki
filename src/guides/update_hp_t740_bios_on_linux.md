# Update Lenovo BIOS on Linux

This guide was written from the perspective of a Linux user with an HP T740 on 07-07-2026.

## Steps

1. Download the BIOS archive from your product support site under the BIOS section:
   - [Support Page](https://support.hp.com/ie-en/drivers/hp-t740-thin-client/29378717)
1. Extract it to a directory: `7z x <file> <directory>`.
1. Create an MSDOS parition table on the USB stick.
1. Create a new 4GB FAT32 partition called HP_TOOLS.
1. Copy `<extracted>/ToolLess/HP` to the root of the new partition.
1. Create a `Previous` directory in `HP/BIOS`. It should be a sibling of `Current` and `Future`.
1. Plug into the HP T740 and enter the BIOS with F10.
1. Select Update Bios utility and pick the from USB option.
