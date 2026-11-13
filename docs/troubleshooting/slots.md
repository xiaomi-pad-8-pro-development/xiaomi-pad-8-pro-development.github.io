# Slot recovery

The tablet has two copies of the system: **slot A** and **slot B**. Only
one runs at a time. Updates go to the other one. See the
[Glossary](../glossary.md#slot).

## Always check the slot first

!!! danger "Never guess the slot"
    Before you flash anything, check which slot is active. Flashing a boot
    image to the wrong slot, or "restoring" it to the wrong one, can leave
    a slot that will not start.

1. Start fastboot mode.
2. Run:

    ```
    fastboot getvar current-slot
    ```

3. Use that letter in every command, for example `boot_a` or `boot_b`.

!!! tip "Keep backups per slot"
    A backup image only fits the slot **and** the build it came from. Do
    not put a backup from slot A onto slot B.

## One slot will not start

If the other slot still has a working build:

1. In fastboot, switch to it:

    ```
    fastboot set_active a
    ```

    (or `b`).

2. Restart:

    ```
    fastboot reboot
    ```

3. Once it starts, install the ROM again from recovery. That writes a
   fresh copy to the broken slot.

## Avoid fastbootd for system partitions

!!! warning
    Flashing system partitions in **fastbootd** (`fastboot reboot fastboot`)
    once removed the other slot's system completely. Install ROMs from
    recovery with the zip instead.

## Recovery only sees its own slot

OrangeFox, and recoveries in general, only open the system partitions of
the slot they started from. Do not try to copy partitions to the other
slot by hand. Install a zip instead.

## Both slots are broken

1. Use the stock fastboot ROM with `flash_all_except_storage` to keep your
   data. See [Going back to stock](../install/stock.md).
2. If that does not start, use `flash_all`. This erases your data.
3. Never use the lock script.
