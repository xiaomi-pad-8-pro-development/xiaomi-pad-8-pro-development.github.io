# Recovery problems

## YARP: ADB sideload does not start

In YARP, **Advanced → ADB Sideload** never starts sideload mode. The
computer still sees the tablet as `recovery`. This is a known bug.

Use this instead:

1. Copy the zip to the tablet:

    ```
    adb push rom.zip /sdcard/Download/
    ```

2. In YARP, tap **Install**, open `Download`, pick the zip and swipe.

## The time is wrong in TWRP

TWRP starts on US Central time. Set your time zone once in
**Settings → Time zone**. It is kept after a restart.

## OrangeFox cannot see the other slot

OrangeFox only sees the system partitions of the slot it started from.
This is normal. Install zips with the normal install screen.

## The recovery crashes or loops

See [The misc fix](misc.md).

## The battery level shows 100% all the time

Older recovery builds could not read the battery. Use the newest build.
