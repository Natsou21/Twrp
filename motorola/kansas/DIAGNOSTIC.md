# Experimental API-32 diagnostic recovery

Stock kernel/DTB/DTBO are unchanged. Userspace is TWRP 12.1, NOT Android 15.
No proprietary vendor product, stock VINTF HAL declarations or decryption libraries.
Userdata/metadata entries are omitted; default TWRP USB init is enabled for ADB.
No post_process_props validator is bypassed. No stock partition is modified by building.
This is not a repair, an ABI compatibility claim, or authorization to flash.
Before temporary boot: inspect image header, ramdisk, USB init and stock boot layout.
Even temporary recovery boot is not guaranteed write-free.
