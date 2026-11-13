# Updating

New builds install to the slot that is not running. Your current system
stays as it is until you restart. If the new build fails, you can go back.

## Do I need to wipe?

| Case | Wipe needed? |
| --- | --- |
| New build of the same ROM, same signing keys | No |
| Another ROM, or a build signed with other keys | Yes, **format data** |
| HyperOS to this ROM | Yes, **format data** |

## Update from Settings

1. Open **Settings → System → Updater**.
2. Download and install the update.
3. Restart when it asks.

!!! note "Coming soon"
    The updater app and its update server for each ROM.

## Update from recovery

1. Download the new ROM zip.
2. Start the recovery.
3. Install the zip the same way as in [Install the ROM](rom.md), step 5.
   **Do not format data.**
4. Reboot to system.

!!! warning "Update the recovery too"
    After an update with new firmware or a new security patch, use the
    newest recovery. An old recovery may not decrypt your data any more.
    See [Decrypt issues](../troubleshooting/decrypt.md).

## If the new build does not finish starting

Do not install another build on top of it. That fails while the first
update is still waiting. Go back to the build that worked first. See
[Boot loops](../troubleshooting/boot-loops.md#a-new-build-does-not-finish-starting).
