# Baikal V8 — experimental prerelease

**Published release:** [v1.0.0-baikal-v8](https://github.com/Juniorleao06/ps4-linux-internal-drive/releases/tag/v1.0.0-baikal-v8)

- User-supplied PS4 Slim Baikal Strawberry 7.0.8 kernel (`bzImage`).
- User-supplied V8 password-recovery initramfs.
- Extracted `init` and `install-HDD-auto.sh` for inspection.
- SHA-256 checksums for the uploaded artifacts.
- Documentation for internal HDD loopback installation and recovery.

**Tested console:** one PS4 Slim Baikal, reported firmware 13.52.
**Root filesystem:** CachyOS LXQt, 50 GiB ext4 loopback image at `/ps4hdd/home/ps4linux.img`.
**Not included:** the PS4 CachyOS `ps4linux.tar.xz` archive or a PS4 exploit.

**Warning:** Experimental, not universally compatible. Never use `RESET` for password
recovery; it can erase the existing Linux image. Use `PASSWD` then `YES-PASSWD`.

**Open obligations:** Source provenance, license notices, corresponding kernel source,
firmware redistribution rights, and other bundled program licenses require review.
See `docs/REDISTRIBUTION_AUDIT.md`.
