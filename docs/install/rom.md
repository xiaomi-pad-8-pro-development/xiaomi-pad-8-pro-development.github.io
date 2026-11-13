# 3. Install the ROM

You need an unlocked bootloader and a working recovery.

TODO: link to the ROM download page.

The ROM zip already includes the HyperOS 4 firmware (`OS4.0.6.0.XPYCNXM`).
You do not need a separate firmware zip.

!!! danger "The first install erases your data"
    Coming from HyperOS, from another ROM, or from a build signed with
    different keys, you must **format data**. This deletes everything,
    including your internal storage. Copy your files off the tablet first.

## Steps

1. Download the ROM zip to your computer.
2. Start the recovery (see [Flash a recovery](recovery.md)).
3. **Format data** (first install only):

    === "TWRP"

        1. Tap **Wipe**, then **Format Data**.
        2. Type `yes` and confirm.

    === "OrangeFox"

        1. Open the **Wipe** menu and choose **Format Data**.
        2. Type `yes` and confirm.

    === "YARP"

        1. Open **Wipe**, then **Format Data**.
        2. Type `yes` and confirm.

    TODO: check the menu names in OrangeFox and YARP on piano.

4. Go back to the main screen and restart into recovery once
   (**Reboot → Recovery**), so the fresh data partition is mounted.
5. Copy the zip and install it:

    === "TWRP"

        **Option A: sideload.**

        1. Tap **Advanced → ADB Sideload** and swipe to start.
        2. On the computer, run:

            ```
            adb sideload rom.zip
            ```

        **Option B: copy, then install.**

        1. On the computer, run:

            ```
            adb push rom.zip /sdcard/Download/
            ```

        2. Tap **Install**, open `Download`, pick `rom.zip` and swipe to
           confirm.

    === "OrangeFox"

        1. On the computer, run:

            ```
            adb push rom.zip /sdcard/Download/
            ```

        2. Open the file list, go to `Download`, tap `rom.zip` and swipe
           to install.

        You can also use ADB sideload from the OrangeFox menu.

    === "YARP"

        ADB sideload does **not** work in YARP yet. Copy the file instead.

        1. On the computer, run:

            ```
            adb push rom.zip /sdcard/Download/
            ```

        2. Tap **Install**, open `Download`, pick `rom.zip` and swipe to
           confirm.

6. Wait until it says it is done. Do not unplug the cable while it works.
7. Tap **Reboot → System**.
8. The first start takes a few minutes. That is normal.

!!! tip "The ROM installs to the other slot"
    The tablet has two copies of the system, slot A and slot B. The ROM is
    written to the slot that is **not** running, and the tablet switches
    to it on the next start. See the [Glossary](../glossary.md#slot).

## If it does not start

- It goes back to recovery or loops: see [Boot loops](../troubleshooting/boot-loops.md).
- Your data does not decrypt in recovery: see [Decrypt issues](../troubleshooting/decrypt.md).
