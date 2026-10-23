# Experimental API-32 diagnostic recovery

Stock kernel/DTB/DTBO are unchanged. Userspace is TWRP 12.1, NOT Android 15.
No proprietary vendor product, stock VINTF HAL declarations or decryption libraries.
All block-device entries are omitted from recovery.fstab and twrp.flags.
The fstab intentionally has no mount entries; init mounts /tmp (RAM). No flashimg, storage, or persistent mount entries.
Default legacy USB init is excluded. An explicitly copied init.recovery.usb.rc
activates configfs and the stock 11201000.usb0 controller; generic TWRP init
provides FunctionFS setup and ADB binding. MTP is excluded.
These restrictions do not make root ADB or recovery code incapable of writing.
Do not install, wipe, switch slots, or enter fastbootd during diagnosis.
No post_process_props validator is bypassed. No stock partition is modified by building.
This is not a repair, an ABI compatibility claim, or authorization to flash.
Before temporary boot: inspect image header, ramdisk, USB init and stock boot layout.
Even temporary recovery boot is not guaranteed write-free.
