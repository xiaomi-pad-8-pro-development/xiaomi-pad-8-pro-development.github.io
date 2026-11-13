# FAQ

??? question "Which tablets does this work on?"
    Only the Xiaomi Pad 8 Pro, code name `piano`. See
    [Is my device supported?](get-started/supported.md)

??? question "Do I need to wipe data to update?"
    No, as long as the new build is the same ROM and is signed with the
    same keys. Moving to another ROM, or from HyperOS, needs a format.
    See [Updating](install/update.md).

??? question "Do I need to flash firmware first?"
    No. The ROM zip includes the HyperOS 4 firmware it needs.

??? question "Which recovery should I pick?"
    TWRP 16 is a safe default. YARP is TWRP with a new look, but it cannot
    sideload yet. OrangeFox is also available. See
    [Flash a recovery](install/recovery.md).

??? question "My data will not decrypt in recovery."
    Use the newest recovery. It must match the security patch level of
    your ROM. See [Decrypt issues](troubleshooting/decrypt.md).

??? question "The tablet loops in every mode except fastboot."
    Run `fastboot erase misc`. See [The misc fix](troubleshooting/misc.md).

??? question "A new build does not start."
    Switch back to the slot that worked with `fastboot set_active`. See
    [Boot loops](troubleshooting/boot-loops.md#a-new-build-does-not-finish-starting).

??? question "Why does it charge slowly with my charger?"
    Other brands' chargers get about 18 W. Fast charging needs the Xiaomi
    charger. See [Charging](troubleshooting/charging.md).

??? question "Can I get root?"
    Yes, with the KernelSU-Next kernel build. See
    [Root with KernelSU](install/root.md).

??? question "Is Google Play included?"
    TODO: depends on the ROM build. List which builds include Google apps.

??? question "Does the Xiaomi camera work?"
    The stock Xiaomi camera is an optional extra. Builds that include it
    have it as the camera app. TODO: list which builds include it.

??? question "Should I use the 6.6 or the 6.12 kernel?"
    Use 6.6. The 6.12 kernel is for testing only. See [Kernels](kernels.md).

??? question "Can I go back to HyperOS?"
    Yes. See [Going back to stock](install/stock.md).

## Known issues

- Charging with non-Xiaomi USB PD chargers is limited to about 18 W.
- YARP recovery cannot use ADB sideload. Push the zip and install it.
- The 6.12 kernel is in testing. Some Xiaomi features, such as reading
  mode, are missing.
- TODO: current list of known issues for the latest release.
