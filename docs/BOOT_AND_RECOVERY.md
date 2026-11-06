# Boot and Recovery — Baikal V8

**Tested:** one PS4 Slim Baikal, firmware 13.52; CachyOS LXQt in a 50 GiB
ext4 image at `/ps4hdd/home/ps4linux.img`.

## Boot an existing image

1. Back up your current kernel and initramfs.
2. Use the V8 release kernel and initramfs with your already-working compatible
   PS4 Linux loader; required paths and names vary by loader.
3. When the existing Linux image is detected, follow the normal boot prompt.
4. Confirm the LXQt desktop starts.

## Recover the Linux account password

1. At the tested initramfs menu, enter `PASSWD`.
2. Confirm with `YES-PASSWD`.
3. Set the password for the Linux account `user` as prompted.
4. Reboot and sign in with the new password.

**Never choose `RESET` for password recovery.** It can delete the existing
Linux image. Never format the entire PS4 internal HDD.

## Troubleshooting

Verify the correct hardware kernel, initramfs, HDD mount, and image path.
Preserve the existing image before attempting any repair or reinstallation.

Modified and tested by Juniorleao06.
