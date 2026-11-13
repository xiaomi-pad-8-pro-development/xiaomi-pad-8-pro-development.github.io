# Boot loops

A boot loop is when the tablet starts, fails and starts again, over and
over.

## Loops in every mode except fastboot

If it loops at the logo even when you try to open recovery, and only
fastboot mode works, see [The misc fix](misc.md). Do that **first**.

## A new build does not finish starting

You installed a new build, and it never gets to the lock screen. It hangs
on the boot animation, or goes back to recovery.

!!! warning "Do not install another build on top"
    While the failed update is still waiting to finish, installing another
    zip fails and writes nothing. Go back to the old slot first.

1. Hold **Power** and **Volume down** to restart into fastboot mode. Use
   the normal bootloader fastboot, **not** fastbootd.
2. See which slot is running now:

    ```
    fastboot getvar current-slot
    ```

3. Switch to the **other** slot, which still has the build that worked.
   If it says `a`, run:

    ```
    fastboot set_active b
    ```

    If it says `b`, run:

    ```
    fastboot set_active a
    ```

4. Restart:

    ```
    fastboot reboot
    ```

5. The old build starts. The failed update is thrown away.
6. Now you can install a build again, if you want to.

## Fastboot reboot goes back to fastboot

After several failed starts, both slots can be marked as "unbootable".
Then `fastboot reboot` always lands in fastboot again.

1. Check the flags:

    ```
    fastboot getvar slot-unbootable:a
    fastboot getvar slot-unbootable:b
    ```

2. Set the slot you want to start. This clears its flag:

    ```
    fastboot set_active a
    ```

    (Use `b` if that is the slot with your working system.)

3. Restart:

    ```
    fastboot reboot
    ```

## Loops at the logo after switching slots

!!! warning "Do not switch slots to compare builds"
    Each slot keeps the build it was given. Your data belongs to the newer
    build. Starting an older build in the other slot on purpose can loop
    at the logo.

To fix it:

1. Open the recovery.
2. Install the last build that worked, as in [Install the ROM](../install/rom.md),
   **without** formatting data.
3. Reboot to system.

## Still looping

Go back to stock with `flash_all_except_storage` first. See
[Going back to stock](../install/stock.md).
