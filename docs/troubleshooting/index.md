# Troubleshooting

Find what you see, then follow that page.

!!! danger "Stop before you wipe or flash"
    Most problems can be fixed **without** erasing anything. Do not format
    data or flash random images first. Read the right page below.

| What you see | Go to |
| --- | --- |
| Logo, black screen, logo again, in every mode except fastboot | [The misc fix](misc.md) |
| A new build does not finish starting | [Boot loops](boot-loops.md#a-new-build-does-not-finish-starting) |
| `fastboot reboot` always goes back to fastboot | [Boot loops](boot-loops.md#fastboot-reboot-goes-back-to-fastboot) |
| You flashed the wrong slot, or one slot will not start | [Slot recovery](slots.md) |
| Recovery asks for no PIN, or your files look like random names | [Decrypt issues](decrypt.md) |
| ADB sideload does not start in YARP | [Recovery problems](recovery.md) |
| Charging is slow | [Charging](charging.md) |

## Useful commands

Check which slot is running, in fastboot mode:

```
fastboot getvar current-slot
```

Check that the computer sees the tablet:

=== "In fastboot"

    ```
    fastboot devices
    ```

=== "In recovery or Android"

    ```
    adb devices
    ```

## Ask for help

When you ask for help, say:

1. Which ROM build and kernel you use.
2. Which recovery and version.
3. What you did, step by step, and what you see now.
4. The output of `fastboot getvar current-slot`.

TODO: link to the support group and bug tracker.
