# Recovery

One tree,
[android_device_xiaomi_piano-recovery](https://github.com/xiaomi-pad-8-pro-development/android_device_xiaomi_piano-recovery),
builds three recoveries:

| Recovery | What it is |
| --- | --- |
| TWRP 16 | Classic TWRP |
| YARP | TWRP 16 with the new GUI2 |
| OrangeFox R12 | OrangeFox, portrait theme centred on the screen |

All of them can decrypt your data, use touch, install ROM and firmware
zips, charge the battery, and make backups.

## Install

```
fastboot flash recovery_a recovery.img
fastboot flash recovery_b recovery.img
```

## Tips

- **Update the recovery after every firmware update.** Decryption needs
  the recovery to match the security patch level of the installed ROM.
- TWRP starts on US Central time. Set your time zone once in
  **Settings → Time zone**.
- YARP cannot sideload. Use `adb push` and **Install**.
- OrangeFox only sees its own slot. Install to the other slot from the
  normal install flow, not by copying partitions by hand.

## Downloads

Images are built by GitHub Actions (**Build recovery**) in the recovery
repository. TODO: link the release page.
