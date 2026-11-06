# Search and discovery: PS4 Linux Baikal / internal HDD

This page helps people find the **experimental** PS4 Linux Internal Drive
project and explains the scope of the documented tests.

## Common search intents

- Install Linux on PS4 Baikal / PS4 Slim Baikal
- Install Linux on the PS4 internal hard drive / internal HDD
- PS4 Linux without USB drive (internal ext4 loopback image)
- CachyOS LXQt PS4 Linux installation, boot and recovery
- Instalar Linux no PS4 Baikal / Balkai / HD interno do PS4
- Instalar Linux en PS4 Baikal / disco duro interno
- Installer Linux sur PS4 Baikal / disque dur interne
- Linux auf PS4 Baikal installieren / interne Festplatte

## Verified scope and limits

- **Verified on one device only:** PS4 Slim Baikal, firmware 13.52.
- **Tested Linux kernel:** `7.0.8-Strawberry-ThinLTO-Baikal-+`.
- **Tested storage:** 50 GiB ext4 loopback file at `/ps4hdd/home/ps4linux.img`.
- **Tested graphics:** RadeonSI OpenGL 4.5; RADV Vulkan 1.3; `vkcube` rendered.
- **Not verified:** other PS4 models, other firmware, universal installation
  success, performance guarantees or game compatibility.
- **Not provided:** a PS4 exploit, payload, or complete PS4-compatible rootfs
  in the GitHub release.

## Useful links

- [README](../README.md)
- [Installation](INSTALLATION.md)
- [Boot and recovery](BOOT_AND_RECOVERY.md)
- [Compatibility](COMPATIBILITY.md)
- [Experimental V8 release](https://github.com/Juniorleao06/ps4-linux-internal-drive/releases/tag/v1.0.0-baikal-v8)
- [Contributions](../CONTRIBUTING.md)
- [Redistribution audit](REDISTRIBUTION_AUDIT.md)

## Help us translate and test

Community translations, search terminology corrections and documented tests on
additional PS4 hardware are welcome via GitHub Issues and Pull Requests.

**Upstream:** [rmuxnet PS4 Linux kernel](https://github.com/rmuxnet/ps4-linux-12xx),
[DionKill PS4 Linux downloads](https://dionkill.github.io/ps4-linux-tutorial/files.html).
Modified and tested by Juniorleao06. Third-party redistribution audit remains open.
