# 2. Flash a recovery

The recovery lets you install the ROM zip, unlock (decrypt) your data and
make backups. One source tree builds three recoveries. Pick one.

| Recovery | What it is |
| --- | --- |
| **TWRP 16** | The classic TWRP. A safe default. |
| **YARP** | TWRP 16 with a new look (GUI2). |
| **OrangeFox R12** | OrangeFox with a portrait theme. |

All of them use touch, decrypt your data with your PIN, install ROM and
firmware zips, and make backups.

TODO: link to the recovery download page.

!!! warning "Use a recovery made for your firmware"
    Use the newest recovery build. Decryption only works when the recovery
    matches the security patch level of what is installed. See
    [Decrypt issues](../troubleshooting/decrypt.md).

## Steps

1. Download the recovery image and save it as `recovery.img`.
2. Start [fastboot mode](index.md#start-fastboot-mode).
3. Check which slot is active, and write it down:

    ```
    fastboot getvar current-slot
    ```

4. Flash the recovery to **both** slots:

    ```
    fastboot flash recovery_a recovery.img
    fastboot flash recovery_b recovery.img
    ```

5. Start the recovery:

    ```
    fastboot reboot recovery
    ```

    If that does not work, hold **Volume up** and **Power** from power off.
    TODO: confirm the key combo on piano.

6. Make sure the recovery opens and you can touch the screen.

!!! danger "Make sure it starts before you rely on it"
    If a new recovery crashes, the tablet can get stuck in a loop. See
    [The misc fix](../troubleshooting/misc.md). Always check that the
    recovery opens once from fastboot before you use `adb reboot recovery`.

## First start tips

=== "TWRP"

    - TWRP starts on US Central time. Set your time zone once in
      **Settings → Time zone**.
    - Enter your PIN when asked so your data is unlocked.

=== "OrangeFox"

    - OrangeFox only sees the slot it started from. Install ROMs with the
      normal install screen, never by copying partitions by hand.
    - Enter your PIN when asked so your data is unlocked.

=== "YARP"

    - YARP is TWRP 16 with a new look, so TWRP tips apply.
    - **ADB sideload does not work in YARP yet.** Copy the zip with
      `adb push` instead (see [Install the ROM](rom.md)).
