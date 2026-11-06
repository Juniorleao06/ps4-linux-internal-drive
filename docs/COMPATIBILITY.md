# Compatibility — PS4 Linux Internal Drive

**Experimental: tested on one console only.**

| Component | Observed configuration |
|---|---|
| Console | PlayStation 4 Slim — Baikal |
| PS4 firmware | 13.52 |
| Distribution | CachyOS LXQt |
| Linux kernel | `7.0.8-Strawberry-ThinLTO-Baikal-+` |
| Storage | Internal HDD; 50 GiB ext4 loop image |
| GPU | AMD Liverpool (`1002:9923`) |
| OpenGL | RadeonSI, OpenGL 4.5 |
| Vulkan | RADV, Vulkan 1.3.335; `vkcube` rendered |

Observed: Linux boot, LXQt, GPU acceleration, and V8 password recovery.

Not verified: other consoles, other firmware versions, Wi-Fi, Bluetooth, audio,
suspend, long-term stability, and game performance.

Modified and tested by Juniorleao06.
