Boot and Recovery Guide

Overview

This guide documents the experimental boot and recovery process tested on a PS4 Slim Baikal running Linux from an internal HDD loopback image.

Modified and tested by Juniorleao06.

Tested Environment

- PS4 Slim Baikal
- PS4 firmware 13.52
- CachyOS Linux with LXQt
- Kernel: "7.0.8-Strawberry-ThinLTO-Baikal-+"
- Linux image: "/ps4hdd/home/ps4linux.img"
- Root filesystem: 50 GiB ext4 loopback image

Normal Boot

1. Start the compatible PS4 Linux boot environment.
2. Load the kernel and initramfs intended for the tested Baikal configuration.
3. Allow the initramfs to locate the existing Linux image on the internal HDD.
4. Continue into the installed Linux system.
5. Log in to the LXQt desktop.

Exact bootloader steps depend on the PS4 exploit and boot environment and are not yet documented as a universal procedure.

Password Recovery

If the Linux account password is forgotten:

1. Open the tested V8 initramfs boot menu.
2. Enter "PASSWD".
3. Confirm with "YES-PASSWD".
4. Set a new password when prompted.
5. Wait for "passwd updated successfully".
6. Reboot and log in with the new password.

Important Warning

Do not select "RESET" to recover a password. That option may erase the Linux installation.

Never format the entire PS4 internal HDD.

Troubleshooting

If Linux fails to boot:

- Confirm that the kernel and initramfs match the console hardware.
- Confirm that the Linux image still exists at the expected path.
- Check boot messages for missing devices or mount errors.
- Preserve the existing image before attempting repairs.
- Do not recreate or overwrite the image without a backup.

Compatibility Notice

This procedure has only been tested on one PS4 Slim Baikal console. Compatibility with other models or firmware versions is unknown.
