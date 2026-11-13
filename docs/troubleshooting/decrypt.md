# Decrypt issues

Your files are encrypted. The recovery must unlock them with your PIN or
password before it can see them.

## What you see

- The recovery does not ask for your PIN.
- Or it accepts the PIN, but files in internal storage have random names.
- Or the recovery cannot find the zip you copied to the tablet.

## Why it happens

The tablet ties the encryption keys to the **security patch level** of
the installed system. The recovery must match it. After an update with a
new security patch, an older recovery can no longer unlock the data.

## Fix

1. Get the **newest** recovery build, one made after your ROM update.
2. Flash it to both slots, as in [Flash a recovery](../install/recovery.md).
3. Start the recovery and enter your PIN.

!!! tip "Rule of thumb"
    Update the recovery every time you update the ROM or firmware.

## If you only need to install a zip

You do not need decryption to install a ROM. Copy the zip to a place the
recovery can read:

=== "TWRP"

    Use ADB sideload: **Advanced → ADB Sideload**, then
    `adb sideload rom.zip` on the computer.

=== "OrangeFox"

    Use ADB sideload from the OrangeFox menu, then `adb sideload rom.zip`
    on the computer.

=== "YARP"

    YARP cannot sideload yet. Use a newer recovery that decrypts, or
    TWRP for this one install.

!!! danger "Format data only as a last step"
    **Format data** fixes decryption, but erases everything. Try a newer
    recovery first.
