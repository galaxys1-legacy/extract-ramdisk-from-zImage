### script to extract ramdisks from galaxysmtd zImage


`
./zImgunlz /path/to/boot.img
`

Pre-nougat kernels ramdisk are built in the stage1 initrd.
If you want to use latest kernel on older roms you'll need to get their ramdisk.

`ramdisk.cpio  ramdisk-recovery.cpio`

Newer kernels have ramdisks in MTD partitions.
/ramdisk
/ramdisk-recovery

Note that ramdisk-recovery is /datadata, so you might need to delete it from initrc scripts.

Thanks:
xc-racer99 and Coldwindofnowhere.