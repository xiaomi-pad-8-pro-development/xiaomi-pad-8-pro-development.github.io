# The misc fix

## What you see

- The tablet shows the logo, then a black or white screen, then the logo
  again, forever.
- It happens in **every** mode except fastboot, even when you choose
  normal start.
- Flashing stock images does not help.

## Why it happens

When you ask for recovery (for example with `adb reboot recovery`), a note
is saved in a small partition called **misc**. It says "start recovery
next time". Recovery clears that note when it starts.

If that recovery crashes, the note is never cleared. So every start goes
back to the broken recovery. Stock flashing does not touch `misc`, so
the loop stays. It looks like a hardware fault, but it is not.

## Fix

!!! note "This is safe"
    Erasing `misc` does not delete your apps, photos or files.

1. Start [fastboot mode](../install/index.md#start-fastboot-mode).
2. Clear the stuck note:

    ```
    fastboot erase misc
    ```

3. Check which slot is active:

    ```
    fastboot getvar current-slot
    ```

4. Put a recovery that you know works on that slot. If it said `a`:

    ```
    fastboot flash recovery_a recovery.img
    ```

    If it said `b`, use `recovery_b`.

5. Restart:

    ```
    fastboot reboot
    ```

## Prevent it

- Before you use `adb reboot recovery`, make sure the recovery has opened
  once from **that** slot.
- If you change the recovery, flash the same image to both slots.
