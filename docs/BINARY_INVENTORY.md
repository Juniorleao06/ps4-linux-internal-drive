# Baikal V8: Binary Inventory and Redistribution Audit

> **Status: OPEN — not a completed license or source-code compliance audit.**

Generated from GitHub Release `v1.0.0-baikal-v8` using a read-only CPIO parser.
The script did not execute or extract the archive contents.

## Verified release binary hashes

| File | SHA-256 |
|---|---|
| `bzImage` | `81518a8ebc1bbe2f0f8b8112d06ce81f4e1e39f5004d8af47dc09b6ccf04f1b9` |
| `initramfs-baikal-v8-password-recovery.cpio.gz` | `13e45b3899682b9045af4b6d9b80f7bc385794f1f5ea0fe192f77144e005a03e` |

Hashes verify **file identity and integrity only**, not authorship, license compliance or compatibility.

## Initramfs inventory

- CPIO entries inspected: **66**
- Potential bundled binary/firmware/library paths: **44**

### License and author notice filenames found

- `LICENCE.Marvell`
- `AUTHORS`
- `LICENSE`

### Potential third-party component paths (sample)

- `lib/ld-linux-x86-64.so.2`
- `lib/libe2p.so.2`
- `lib/libcom_err.so.2`
- `lib/firmware`
- `lib/firmware/mrvl`
- `lib/firmware/mrvl/sd8897_uapsta.bin`
- `lib/firmware/mrvl/sd8797_uapsta.bin`
- `lib/libuuid.so.1`
- `lib/libc.so.6`
- `lib/libsmartcols.so.1`
- `lib/libext2fs.so.2`
- `lib/libblkid.so.1`
- `lib/libtinfo.so.6`
- `lib/x86_64-linux-gnu`
- `lib/x86_64-linux-gnu/libc.so.6`
- `bin/resume-boot`
- `bin/.keep`
- `bin/install-arch.sh`
- `bin/truncate`
- `bin/install-HDD-auto.sh`
- `bin/dumpe2fs`
- `bin/dbclient`
- `bin/mdadm`
- `bin/dropbearmulti`
- `bin/lvm`
- `bin/askpass`
- `bin/mke2fs`
- `bin/resume`
- `bin/binit-udhcpc-script`
- `bin/busybox`
- `bin/e2fsck`
- `bin/losetup_arch_2.41`
- `bin/binit-zcip-script`
- `bin/start-arch.sh`
- `bin/cryptsetup`
- `bin/unlock-luks`
- `bin/dropbearkey`
- `bin/dropbear`
- `bin/vconfig`
- `bin/install-HDD.sh`
- `bin/sh`
- `bin/tune2fs`
- `bin/resize2fs`
- `sbin/telinit`

## Unresolved compliance checklist

- [ ] Identify exact kernel source commit, patches, configuration, toolchain and corresponding source distribution.
- [ ] Identify licenses and complete corresponding source for BusyBox and any other GPL binaries.
- [ ] Review all bundled executable/library/firmware files and their required copyright notices.
- [ ] Verify firmware redistribution permissions.
- [ ] Verify the initramfs original project license and modification provenance.
- [ ] Verify CachyOS PS4 rootfs provenance and redistribution terms (external link only).
- [ ] Document reliable primary-source links for each checked component.

Kernel upstream reference: https://github.com/rmuxnet/ps4-linux-12xx
PS4 rootfs reference: https://dionkill.github.io/ps4-linux-tutorial/files.html

**Do not check any item off until it is supported by evidence.**
