# Installation — PS4 Linux Internal Drive (Baikal V8)

> [!CAUTION]
> Experimental; tested on one PS4 Slim Baikal (firmware 13.52).
> Back up the PS4 and your existing Linux image before changing boot files.
> Never format the whole PS4 internal disk. Never choose `RESET` to recover a password.

## Tested environment

- Kernel: `7.0.8-Strawberry-ThinLTO-Baikal-+`.
- CachyOS LXQt root filesystem: PS4-compatible `ps4linux.tar.xz` (not included).
- Rootfs archive copied over FTP to `/user/system/boot/ps4linux.tar.xz`,
  accessible inside the initramfs as `/ps4hdd/system/boot/ps4linux.tar.xz`.
- Target Linux image: `/ps4hdd/home/ps4linux.img`, 50 GiB ext4 loopback.

## Downloads

- [Experimental V8 release](https://github.com/Juniorleao06/ps4-linux-internal-drive/releases/tag/v1.0.0-baikal-v8): `bzImage`,
  `initramfs-baikal-v8-password-recovery.cpio.gz`, scripts and checksums.
- [PS4 rootfs download reference](https://dionkill.github.io/ps4-linux-tutorial/files.html).

## Before proceeding

1. Confirm that you have a **working PS4 Linux loader** compatible with Baikal.
   This project does not supply a PS4 exploit, payload, or universal loader.
2. Preserve your existing kernel, initramfs, and any existing `ps4linux.img`.
3. Check the release asset hashes against the `SHA256SUMS` file. A matching hash
   detects corruption but does not independently authenticate upstream provenance.
4. Verify sufficient internal HDD free space for a 50 GiB image and working files.
5. Ensure the PS4-compatible rootfs archive is the intended file, not a generic ISO.

## Installation overview (not a universal command recipe)

1. Copy the PS4 rootfs archive over FTP to `/user/system/boot/ps4linux.tar.xz`.
2. Boot the matching kernel and V8 initramfs through your **existing** compatible loader.
3. Verify that the initramfs can access `/ps4hdd/system/boot/ps4linux.tar.xz`.
4. Follow the initramfs install prompts only after verifying the correct internal
   HDD mount and target image path. Do not use destructive options on an existing image.
5. After installation, boot the image and verify LXQt, `glxinfo -B`,
   `vulkaninfo --summary`, and optionally `vkcube`.

The release asset is named `initramfs-baikal-v8-password-recovery.cpio.gz`.
Some loaders expect the name `initramfs.cpio.gz`; rename a **copy** only if your
loader requires it. The destination path depends on your loader and is not universal.

## Existing installation and password recovery

For a previously installed image, use the existing-image boot option. To recover
its Linux password, choose `PASSWD` and confirm with `YES-PASSWD`.
**Do not use `RESET`: it may delete the existing Linux image.**
See [Recovery](RECOVERY.md) and [Boot and Recovery](BOOT_AND_RECOVERY.md).

## Limitations

No verified universal exploit/payload steps, automated partition procedure,
or compatibility guarantee are provided. Review the installer scripts before use.
The corresponding-source and redistribution audit remains open.
