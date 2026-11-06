<div align="center">

# PS4 Linux Internal Drive
### Baikal Edition · v1.0.0

**Run CachyOS from the PlayStation 4 internal HDD — no USB storage required.**

**EXPERIMENTAL · UNSTABLE · ONE-CONSOLE VALIDATION**

</div>

> [!CAUTION]
> This is an experimental PS4 Linux modification, **not a stable or universally compatible installer**. It worked on one PS4 Slim Baikal, but other consoles may fail to boot or suffer data loss. Back up your PS4 data and keep a known-good boot image. **Never select `RESET` when you want to preserve an existing Linux installation.**

## What works on the tested PS4

- Booting CachyOS LXQt from a **50 GiB ext4 image file** at `/ps4hdd/home/ps4linux.img` on the PS4's internal HDD, without a USB drive or replacing the PS4 system partition.
- Password recovery for the Linux account `user` via a confirmation-protected `PASSWD` option.
- AMD Liverpool hardware-accelerated OpenGL 4.5 (Mesa RadeonSI).
- RADV Vulkan 1.3 device detection and a successful rotating `vkcube` rendering test.

These results are observations, not compatibility or performance guarantees.

## Tested configuration

| Component | Details |
|---|---|
| Console | PlayStation 4 Slim, Baikal hardware revision |
| Reported firmware during testing | 13.52 |
| Kernel | `7.0.8-Strawberry-ThinLTO-Baikal-+` |
| Distribution | CachyOS x86_64, LXQt desktop; installed from a `ps4linux.tar.xz` archive |
| Linux root filesystem | 50 GiB ext4 loop image on internal PS4 HDD |
| GPU | AMD Liverpool, PCI ID `1002:9923` |
| Graphics | Mesa RadeonSI / RADV, OpenGL 4.5, Vulkan 1.3 |

## Files

### Documentation available

- [Installation Guide](docs/INSTALLATION.md)
- [Boot and Recovery](docs/BOOT_AND_RECOVERY.md)
- [Password Recovery](docs/RECOVERY.md)
- [Compatibility](docs/COMPATIBILITY.md)
- [Credits](docs/CREDITS.md)
- [Security](docs/SECURITY.md)
- [Contributing](CONTRIBUTING.md)

### Binary release status

**Experimental Baikal V8 prerelease:** [Download the tested-user-supplied boot files](https://github.com/Juniorleao06/ps4-linux-internal-drive/releases/tag/v1.0.0-baikal-v8).

Release assets: `bzImage`, `initramfs-baikal-v8-password-recovery.cpio.gz`,
`init-source`, `install-HDD-auto.sh`, and `SHA256SUMS`.
The initramfs filename is **not** `initramfs.cpio.gz` in the release. If your existing
PS4 loader specifically expects `initramfs.cpio.gz`, rename a *copy* to that
filename; do not overwrite your known-good backup. The correct location depends
on the loader and is not universal.

**Not included:** `ps4linux.tar.xz`, a PS4 exploit/payload, or console-specific
HDD keys. Do not use a standard CachyOS ISO in place of a PS4-compatible rootfs.

**Redistribution notice:** Publication does not mean that kernel corresponding
source, firmware rights, or bundled utility licenses have been fully audited.
See [Redistribution Audit](docs/REDISTRIBUTION_AUDIT.md) before mirroring binaries.

## Installation

Read **[Installation](docs/INSTALLATION.md)** completely before proceeding. The tested process requires an already-working PS4 Linux loader and matching kernel; this project does not provide the exploit or PS4-side payload. The first-time installation path is less thoroughly validated than booting an existing image.

## Boot an existing installation

1. Back up your known-good initramfs and the Linux image if possible.
2. Back up your current boot files. Use the release asset `initramfs-baikal-v8-password-recovery.cpio.gz`; if your loader requires `initramfs.cpio.gz`, rename a copy and place it at the path required by your existing loader.
3. Boot using the release asset `bzImage` and your existing compatible Linux loader.
4. When the screen says `Existing ps4linux.img detected`, press **Enter** to boot it.
5. **Do not type `RESET`** unless you intentionally want to destroy and reinstall the Linux image.

## Password recovery

At the existing-image prompt, type `PASSWD`, press Enter, then confirm with `YES-PASSWD`. Enter the new password twice, reboot, and boot the existing image normally. See [Recovery](docs/RECOVERY.md).

## GPU checks

```sh
glxinfo -B
vulkaninfo --summary
vkcube
```

`vkcube` worked on the tested system; this does not establish game compatibility.

## Stability, upstream licensing and redistribution

This is **unstable experimental software**. The initramfs bundles third-party programs and firmware, and the kernel is a third-party Linux build. Preserving existing copyright notices does **not** automatically satisfy all redistribution and corresponding-source obligations. **The binaries are already published as an experimental prerelease, but their complete origin, licenses, and corresponding-source obligations are not yet verified.** See [Credits](docs/CREDITS.md). No license is asserted over third-party components by this project.

## Credits

**Modified and tested by [Juniorleao06](https://github.com/Juniorleao06).** Original work and upstream components are credited in [CREDITS.md](docs/CREDITS.md). Credit does not imply upstream endorsement.

## Contributions

Issues and pull requests are welcome. Include hardware revision, kernel, boot logs, and steps to reproduce. **Never upload console keys, passwords, unique console identifiers, or private data.**

## Download References

### PS4 Linux Kernel

**Tested kernel:** `7.0.8-Strawberry-ThinLTO-Baikal-+`

Original project:
https://github.com/rmuxnet/ps4-linux-12xx

### CachyOS Light for PS4

**Root filesystem archive:** `ps4linux.tar.xz`

MediaFire:
https://www.mediafire.com/file/hvlz6qk3e36rlk1/ps4linux.tar.xz/file

Original download page:
https://dionkill.github.io/ps4-linux-tutorial/files.html

**Important:** These are upstream download references.
The exact downloaded binaries have not yet been
verified by matching SHA-256 checksums.

### Internal HDD Modifications

Modified and tested by **Juniorleao06**.

The tested setup uses a 50 GiB ext4 loopback image
stored on the PS4 internal HDD.

The modified initramfs and installer are available in the
[experimental V8 prerelease](https://github.com/Juniorleao06/ps4-linux-internal-drive/releases/tag/v1.0.0-baikal-v8).
Their redistribution audit is still incomplete.

