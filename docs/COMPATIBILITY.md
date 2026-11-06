Compatibility — PS4 Linux Internal Drive

«Experimental project. Compatibility has only been verified on one console.»

Tested Hardware

Component| Tested configuration
Console| PlayStation 4 Slim — Baikal
PS4 firmware| 13.52
Linux distribution| CachyOS with LXQt
Linux kernel| "7.0.8-Strawberry-ThinLTO-Baikal-+"
Storage| PS4 internal HDD
Linux filesystem| 50 GiB ext4 loopback image
GPU| AMD Liverpool ("1002:9923")
OpenGL| Mesa RadeonSI — OpenGL 4.5
Vulkan| RADV — Vulkan 1.3.335

Confirmed Functionality

- Linux boots from an image stored on the internal HDD.
- LXQt graphical desktop starts.
- OpenGL acceleration is detected.
- Vulkan is detected, and "vkcube" renders successfully.
- Password recovery works through the tested V8 initramfs menu.

Not Yet Verified

- Other PS4 models and hardware revisions
- Other PS4 firmware versions
- Wi-Fi and Bluetooth compatibility
- Audio and suspend behavior
- Long-term stability
- Performance across different games and applications

Important

These results describe one tested installation. They do not guarantee compatibility with other consoles.

Modified and tested by Juniorleao06.
