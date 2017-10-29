### script to extract ramdisks from galaxysmtd zImage

`
./zImgunlz /path/to/boot.img
`

Pre-nougat kernels ramdisks are built in the kernel initramfs.  
The stage1 `init` detects and loads android ramdisk or recovery ramdisk. 
If you want to use custom kernel on older roms you'll need to get their ramdisk.  

The script will extract `ramdisk.stage1.cpio` .  
Then you need to extract it to find the ramdisks inside `stage1` directory.  

`ramdisk.cpio` `ramdisk-recovery.cpio`

There is no way to repack this ramdisks back into zImage.
You'll have to rebuild the kernel with the newly made ramdisks.

### Kernels from Nougat 7.1
Starting from 7.1 nougat have ramdisks in MTD partitions.  
```
/ramdisk  
/ramdisk-recovery
```

Note that ramdisk-recovery is `/datadata,` so you might need to delete it from initrc scripts if you plan to use it on older android versions.

Thanks:  
@xc-racer99 and @Coldwindofnowhere.
