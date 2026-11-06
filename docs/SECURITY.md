# Security and Safety

This is experimental software tested on one PS4 Slim Baikal. Back up all
important data, your known-good boot files, and the Linux image.

- Never format the entire PS4 internal HDD.
- Never use `RESET` to recover a password; it may delete `ps4linux.img`.
- Password recovery uses `PASSWD` followed by `YES-PASSWD`.
- Check `/ps4hdd` is mounted and verify the intended target path before installing.
- Never publish passwords, private keys, console identifiers, or personal files.
- Check downloads against SHA-256 checksums; checksums alone are not proof of trust.
- Review scripts and source provenance before executing them with root privileges.
- Report issues with model, firmware, kernel version, and redacted logs.

There is no guarantee of compatibility or data preservation.
Modified and tested by Juniorleao06.
