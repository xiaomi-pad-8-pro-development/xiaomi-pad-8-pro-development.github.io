# Known issues and FAQ

## Known issues

- Fast charging with third-party USB PD (PPS) chargers is limited to
  about 18 W. The Xiaomi charger is needed for faster charging.
- YARP recovery cannot use `adb sideload`. Push the zip and install it.
- The 6.12 kernel is still in testing. Some Xiaomi features are missing.
- TODO: current list of known issues for the latest release.

## FAQ

**My data will not decrypt in recovery.**
Update to the newest recovery. After a firmware update the recovery must
match the new security patch level.

**The tablet loops in every mode except fastboot.**
Run `fastboot erase misc`, then boot again.

**A new build does not boot.**
Switch back to the slot that worked: `fastboot set_active a` (or `b`).
See [Install → Roll back](install.md#5-roll-back).

**Do I need to wipe data to update?**
No, as long as the new build is signed with the same keys. Moving
between ROMs or to builds with different keys needs a format.

**Is Google Play included?**
TODO: depends on the ROM build.

**Can I get root?**
Yes, use the KernelSU build. See [Kernels](kernels.md).
