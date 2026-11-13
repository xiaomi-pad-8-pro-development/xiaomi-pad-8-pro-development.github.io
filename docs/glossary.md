# Glossary

Short meanings of the words used on this site.

## ADB

Android Debug Bridge. A computer tool that talks to the tablet in Android
or in recovery. It can copy files (`adb push`) and install zips
(`adb sideload`).

## Bootloader

The first program that runs when the tablet starts. It chooses what to
start next. It must be **unlocked** to install custom software.

## Fastboot

A mode of the bootloader, and the computer tool with the same name. Used
to flash partitions, switch slots and unlock the bootloader. Start it with
**Volume down + Power**, or `adb reboot bootloader`.

**fastbootd** is a different mode that runs from recovery. Most guides
here use the bootloader fastboot.

## Firmware

Low-level software for the chip, modem, camera and other parts. It comes
from Xiaomi. These ROMs include the HyperOS 4 China firmware
`OS4.0.6.0.XPYCNXM`.

## Format data

Erases the data partition, including internal storage, and removes its
encryption. Needed for a first install. Different from a normal wipe.

## GKI

Generic Kernel Image. Google's shared core kernel for Android. Phone makers
add their drivers as separate **modules**. The alxp kernel follows this
model, on the `android15-6.6` and `android16-6.12` bases.

## KSU

KernelSU, a way to get root that lives inside the kernel. This project
uses **KernelSU-Next**, with **SUSFS** to hide root from apps. See
[Root with KernelSU](install/root.md).

## misc

A small partition that holds the "what to start next" note. If it gets
stuck, the tablet can loop. See [The misc fix](troubleshooting/misc.md).

## OTA

Over-the-air update. A new build installed from Settings, or from a zip in
recovery. On this tablet it installs to the other slot.

## Recovery

A small separate system for installing zips, making backups and wiping.
This project has TWRP, YARP and OrangeFox.

## ROM

A full Android system you install on the tablet, such as LineageOS or
Evolution X.

## Security patch level

The date of the Android security fixes in a build. The encryption keys
are tied to it, so the recovery must match it to decrypt your data.

## Sideload

Installing a zip straight from the computer with `adb sideload`, without
copying it to the tablet first.

## Slot

The tablet keeps two copies of the system, **slot A** and **slot B**. One
runs while updates go to the other. If an update fails, you can switch
back. Check the active slot with `fastboot getvar current-slot`.

## Virtual A/B

The way this tablet stores the two slots. The update is kept as a
snapshot until the new build starts fine, then it is merged.
