# Binary Redistribution and Provenance Audit

**Status: OPEN — not a completed license audit.**

This project has published an experimental binary prerelease. Publication and
attribution do not by themselves establish redistribution compliance.

## Known references

- Kernel upstream project: https://github.com/rmuxnet/ps4-linux-12xx
- PS4 root filesystem reference: https://dionkill.github.io/ps4-linux-tutorial/files.html
- CachyOS rootfs reference: https://www.mediafire.com/file/hvlz6qk3e36rlk1/ps4linux.tar.xz/file
- `initramfs` archive contains notices attributed to Piotr Karbowski and feeRnt.
- Modifications and testing: Juniorleao06.

## Outstanding checks

- [ ] Identify the exact kernel binary's upstream commit, config, patches, and build provenance.
- [ ] Provide or link to the complete corresponding source required by the kernel license,
      including applicable modifications and build scripts/instructions.
- [ ] Inventory programs and libraries inside the initramfs and retain their required notices.
- [ ] Determine source obligations for GPL-licensed initramfs components (including BusyBox).
- [ ] Verify redistribution rights and attribution requirements for included firmware blobs.
- [ ] Confirm rootfs provenance and terms; the rootfs is linked externally, not bundled.
- [ ] Confirm license of original initramfs modifications and permission to redistribute them.
- [ ] Check that release assets and SHA256SUMS are consistent after any future updates.

**Do not mark these complete without primary-source evidence.**
