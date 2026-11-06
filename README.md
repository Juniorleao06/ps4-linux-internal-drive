<div align="center">

# PS4 Linux Internal Drive
### Baikal Edition · v1.0.0

**Run CachyOS from the PlayStation 4 internal HDD — no USB storage required.**

**EXPERIMENTAL · UNSTABLE · ONE-CONSOLE VALIDATION · CONTRIBUTIONS WELCOME**

</div>

> [!CAUTION]
> This is an experimental PS4 Linux modification, **not a stable or universally compatible installer**. It worked on one PS4 Slim Baikal, but other consoles may fail to boot or suffer data loss. Back up your PS4 data and keep a known-good boot image. **Never select `RESET` when you want to preserve an existing Linux installation.**

<!-- DISCOVERY-START -->
## Find this project — PS4 Linux Baikal / Internal HDD

**PS4 Linux Baikal installation and internal hard drive boot** — an experimental
community project for running **CachyOS Linux LXQt on a PlayStation 4 Slim
(Baikal)** from a **50 GiB ext4 loopback image on the PS4 internal HDD**.
This project documents the tested boot process, installation considerations,
recovery, AMD RadeonSI graphics, and Vulkan RADV checks. It does **not** provide
a PS4 exploit or a universal installer. Compatibility has only been confirmed
on **one PS4 Slim Baikal (firmware 13.52)**.

**Start here:** [Installation guide](docs/INSTALLATION.md) ·
[Boot and recovery](docs/BOOT_AND_RECOVERY.md) ·
[Compatibility](docs/COMPATIBILITY.md) ·
[Experimental Baikal V8 downloads](https://github.com/Juniorleao06/ps4-linux-internal-drive/releases/tag/v1.0.0-baikal-v8) ·
[Contribute](CONTRIBUTING.md).

### Search in your language / Encontre o projeto no seu idioma

| Language | What this project covers |
|---|---|
| 🇧🇷 Português | **Como instalar Linux no PS4 Baikal / Balkai**, iniciar CachyOS no HD interno do PS4 Slim, sem pendrive, com guia de instalação e recuperação de senha. Projeto experimental testado em um único console. |
| 🇺🇸 English | **How to install Linux on PS4 Baikal**, boot CachyOS from the PS4 internal hard drive (HDD), PS4 Slim Linux setup, installation and recovery guides. Experimental, single-console validation. |
| 🇪🇸 Español | **Cómo instalar Linux en PS4 Baikal**, arrancar CachyOS desde el disco duro interno de PS4 Slim, guía de instalación y recuperación. Experimental, probado en una consola. |
| 🇫🇷 Français | **Installer Linux sur PS4 Baikal**, démarrer CachyOS depuis le disque dur interne de la PS4 Slim, guide d'installation et de récupération. Projet expérimental. |
| 🇩🇪 Deutsch | **Linux auf PS4 Baikal installieren**, CachyOS von der internen PS4-Slim-Festplatte starten, Installations- und Wiederherstellungsanleitung. Experimentell. |
| 🇮🇹 Italiano | **Installare Linux su PS4 Baikal**, avviare CachyOS dal disco rigido interno di PS4 Slim, guida all'installazione e al recupero. Sperimentale. |
| 🇯🇵 日本語 | **PS4 BaikalにLinuxをインストール**、PS4 Slimの内蔵HDDからCachyOSを起動する実験的なプロジェクト。導入と復旧のガイドがあります。 |
| 🇨🇳 简体中文 | **在PS4 Baikal上安装Linux**，从PS4 Slim内部硬盘启动CachyOS，提供安装与恢复说明。仅在一台主机上验证。 |
| 🇷🇺 Русский | **Установка Linux на PS4 Baikal**, запуск CachyOS с внутреннего жесткого диска PS4 Slim, руководство по установке и восстановлению. Экспериментальный проект. |
| 🇸🇦 العربية | **تثبيت لينكس على PS4 Baikal** وتشغيل CachyOS من القرص الصلب الداخلي لجهاز PS4 Slim، مع إرشادات التثبيت والاستعادة. مشروع تجريبي. |

The guides are primarily in English. Translations and additional hardware
compatibility reports are welcome via [Issues](https://github.com/Juniorleao06/ps4-linux-internal-drive/issues)
and [Pull Requests](https://github.com/Juniorleao06/ps4-linux-internal-drive/pulls).

> **Safety and licensing:** Do not format the entire PS4 HDD. Never use `RESET`
> for password recovery; use `PASSWD` / `YES-PASSWD` as documented. Third-party
> binary/source and firmware redistribution review is still open:
> [audit](docs/REDISTRIBUTION_AUDIT.md).
<!-- DISCOVERY-END -->

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

## Community Contributions — Everyone Is Welcome!

**This is a public experimental community project.** Everyone is welcome to
fork the repository, test it, improve scripts and documentation, report bugs,
and propose changes through Pull Requests. You do not need direct write access.
The maintainer reviews proposed changes before merging them into `main`.

- **Report problems or suggest features:** [Open an Issue](https://github.com/Juniorleao06/ps4-linux-internal-drive/issues/new)
- **Propose a change:** [Open a Pull Request](https://github.com/Juniorleao06/ps4-linux-internal-drive/pulls)
- **Contribution guide:** [CONTRIBUTING.md](CONTRIBUTING.md)
- **Experimental Baikal V8 release:** [v1.0.0-baikal-v8](https://github.com/Juniorleao06/ps4-linux-internal-drive/releases/tag/v1.0.0-baikal-v8)

### Help Wanted

- Test additional PS4 models and hardware revisions, reporting verified results.
- Improve installation, recovery, boot and troubleshooting guides.
- Review installer safety and avoid destructive HDD operations.
- Investigate RadeonSI, RADV, Vulkan, Mesa and desktop compatibility.
- Trace exact upstream source revisions, corresponding source, licenses and
  firmware permissions for the [redistribution audit](docs/REDISTRIBUTION_AUDIT.md).
- Translate documentation and make it easier for beginners to follow.

### How to Contribute

1. Open an Issue for a bug, feature request or substantial proposal.
2. Fork this repository, make changes in your own branch, and open a Pull Request.
3. Describe the changes and provide your PS4 model, kernel and test results.
4. Never include PS4 HDD keys, passwords, private console identifiers or
   third-party binaries without confirmed redistribution permission.

**Critical safety note:** Never format the entire PS4 HDD. Do not use `RESET`
to recover a password: it may destroy the existing Linux image. Use the
`PASSWD` option followed by `YES-PASSWD` as described in [Recovery](docs/RECOVERY.md).

### Licensing and Attribution

The project is open for community contributions, but **public access is not
an unlimited license to redistribute or relicense third-party software**.
Kernel, initramfs, firmware and bundled utilities retain their own applicable
licenses. Source and redistribution compliance is still being reviewed;
contributors are welcome to help document and resolve outstanding items.

**Modified and tested by [Juniorleao06](https://github.com/Juniorleao06)**
on one PS4 Slim Baikal, firmware 13.52. Original authors and download sources
are credited below and in [CREDITS.md](docs/CREDITS.md).

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

