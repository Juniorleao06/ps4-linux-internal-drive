# Password Recovery — Baikal V8

This recovery method was tested for Linux account `user` on one PS4 Slim Baikal.

1. Boot the compatible V8 initramfs.
2. At its menu, type `PASSWD` and press Enter.
3. Confirm with `YES-PASSWD`.
4. Enter the new password as prompted and wait for confirmation.
5. Reboot, boot the existing Linux image, and sign in.

**Do not choose `RESET`.** That option can delete the Linux image. Password
recovery does not require formatting the internal HDD.

Modified and tested by Juniorleao06.
