# 1. Unlock the bootloader

A locked bootloader only starts software signed by Xiaomi. You must unlock
it to install anything else.

!!! danger "This erases everything"
    Unlocking deletes all data on the tablet. Back up first.

## Steps

1. Sign in to a Xiaomi account on the tablet.
2. Turn on **Developer options**: open **Settings → About tablet** and tap
   the **OS version** several times.
3. In **Developer options**, open **Mi Unlock status** and link your
   account.
4. Wait the waiting period Xiaomi gives you.
5. Start the tablet in [fastboot mode](index.md#start-fastboot-mode) and
   connect it to the computer.
6. Run Xiaomi's official unlock tool on the computer and follow it.
7. The tablet erases itself and restarts unlocked.

TODO: the exact unlock rules and waiting period for this model and region,
and the link to Xiaomi's unlock tool. Check every menu name above against
HyperOS 4 on piano.

## Check that it worked

```
fastboot getvar unlocked
```

It should say `unlocked: yes`.

!!! warning "Do not lock it again"
    Never run `fastboot flashing lock` or a stock "lock" script while a
    custom ROM or recovery is installed. A locked bootloader with
    unofficial software may not start at all.
