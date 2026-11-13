# Install guide

Read the whole page before you start. You need a computer with
`adb` and `fastboot` ([Android platform tools](https://developer.android.com/tools/releases/platform-tools)) and a USB cable.

## 1. Unlock the bootloader

The tablet must have an unlocked bootloader. Xiaomi requires its own
unlock tool and a waiting period.

TODO: exact unlock steps and current Xiaomi rules for this model.

!!! warning
    Unlocking erases everything on the tablet.

## 2. Flash a recovery

Download a recovery image (see [Recovery](recovery.md)). Start the tablet
in fastboot mode (TODO: confirm key combo, usually Power + Volume down),
then flash it to both slots:

```
fastboot flash recovery_a recovery.img
fastboot flash recovery_b recovery.img
fastboot reboot recovery
```

## 3. Install the ROM

1. In recovery, choose **Wipe → Format data** for a first install
   (or when you come from HyperOS or another ROM).
2. Copy the ROM zip to the tablet and choose **Install**, or use
   `adb sideload rom.zip` (not on YARP, see below).
3. Reboot.

On **YARP**, sideload does not work. Push the zip instead and install it
from the file list:

```
adb push rom.zip /sdcard/
```

TODO: whether the ROM zip already includes the firmware, or if a
firmware zip must be flashed first.

## 4. Updates (OTA)

New builds install to the other slot, so your current system stays
untouched until the reboot. Install updates from **Settings → System →
Updater**, or install the new zip in recovery the same way as above.
You do not need to wipe data between builds signed with the same keys.

TODO: confirm the updater app and its server for each ROM.

## 5. Roll back

If a new build does not boot, go back to the previous slot. In fastboot
mode:

```
fastboot getvar current-slot
fastboot set_active a      # or b: the slot that worked before
fastboot reboot
```

!!! tip
    Always check `fastboot getvar current-slot` before you flash anything,
    so you know which slot you are changing.

If the tablet boots into a loop in every mode except fastboot, a stuck
recovery command is the usual cause. Clear it with:

```
fastboot erase misc
```
