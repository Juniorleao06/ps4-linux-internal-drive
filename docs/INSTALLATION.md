
Installation Guide — PS4 Linux Internal Drive (Baikal Edition)

«Experimental and unstable. This installation method was tested on one PS4 Slim Baikal console. Compatibility with other PS4 models is not guaranteed.»

Tested Configuration

- Console: PlayStation 4 Slim (Baikal)
- PS4 firmware: 13.52
- Linux distribution: CachyOS with LXQt desktop
- Kernel: "7.0.8-Strawberry-ThinLTO-Baikal-+"
- Storage: PS4 internal HDD
- Linux filesystem: 50 GiB ext4 loopback image
- Linux image path: "/ps4hdd/home/ps4linux.img"
- Root filesystem archive: "/ps4hdd/system/boot/ps4linux.tar.xz"

Requirements

- A compatible jailbroken PS4 with a working Linux boot environment
- A compatible PS4 Linux kernel and initramfs
- A compatible Linux root filesystem archive
- Sufficient free space on the PS4 internal HDD
- A backup of important data

Installation Overview

1. Back up important PS4 data before making any storage changes.
2. Place the compatible root filesystem archive at "/user/system/boot/ps4linux.tar.xz" using the PS4 FTP environment.
3. Confirm that the archive is accessible as "/ps4hdd/system/boot/ps4linux.tar.xz" from the Linux initramfs.
4. Use the compatible internal-HDD installation environment to create and populate the 50 GiB ext4 loopback image.
5. Boot the installed Linux system using the compatible PS4 Linux boot environment.
6. Verify the desktop, graphics drivers and storage mounts.

Important: This document describes the tested setup, not a universal one-click installer. Exact installation commands and binary provenance must be verified before a public installation procedure is released.

Safety Warnings

- Never format the entire PS4 internal HDD.
- Do not use the "RESET" option on an existing installation unless you deliberately intend to erase it.
- Do not assume that kernels or initramfs files from another PS4 model will work.
- Do not redistribute third-party binaries without reviewing their origins and licenses.

Credits

Modified and tested by Juniorleao06.

Thanks to the PS4 Linux community and contributors to better-initramfs, Linux, CachyOS, Mesa and BusyBox. Specific binary provenance remains under review.
