# Install guide

Follow these pages **in order**. Read each page to the end before you do
the steps.

1. [Unlock the bootloader](unlock.md). Done once.
2. [Flash a recovery](recovery.md). Done once, and again after big updates.
3. [Install the ROM](rom.md).

After that:

- [Root with KernelSU](root.md) if you want root.
- [Updating](update.md) when a new build comes out.
- [Going back to stock](stock.md) if you want HyperOS again.

!!! danger "Back up first"
    These steps erase your data. Read [Risks and backups](../get-started/risks.md).

## Get to know the modes

You will use three special modes. Each one has its own tools.

| Mode | What it is | Tool on the computer |
| --- | --- | --- |
| **Fastboot** (bootloader) | Lowest level. Flashes partitions. | `fastboot` |
| **Recovery** | A small system for installing zips. | `adb` |
| **Android** | The normal system. | `adb` (with USB debugging on) |

### Start fastboot mode

1. Turn the tablet off.
2. Hold **Volume down** and **Power** together until the fastboot screen
   shows.

    **Volume down** and **Power** is the standard fastboot combo on Xiaomi
    devices ([Wikipedia: Fastboot](https://en.wikipedia.org/wiki/Fastboot),
    [guide for the Xiaomi Pad 7](https://www.hardreset.info/devices/xiaomi/xiaomi-pad-7/fastboot-mode/));
    no official Xiaomi page for piano was found.

Or, from Android with USB debugging on:

```
adb reboot bootloader
```

Check that the computer sees the tablet:

```
fastboot devices
```

!!! note "fastboot and fastbootd are different"
    `fastboot reboot fastboot` starts **fastbootd**, a different mode that
    runs from recovery. These guides use the normal bootloader fastboot
    unless they say otherwise.
