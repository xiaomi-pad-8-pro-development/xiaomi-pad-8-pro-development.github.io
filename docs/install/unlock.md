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

## Xiaomi's unlock rules

These rules come from community reports, not an official Xiaomi page, and
Xiaomi changes them often. Check the current rules before you start.

- **Global, EEA and other non-China firmware:** you apply in the
  **Xiaomi Community** app (version 5.3.31 or newer, region set to Global,
  **Me → Unlock bootloader**). The Xiaomi account must be at least 30 days
  old, and since 1 January 2025 one account can unlock one device per
  year. Applications have a daily quota that resets at 00:00 China time.
  After approval, the usual HyperOS waiting time in the unlock tool is
  72 hours, but some users report 14 or 30 days.
  ([xiaomiui.net](https://xiaomiui.net/how-to-unlock-bootloader-on-xiaomi-official-steps-wait-times-and-hyperos-rules-74863/),
  [Xiaomi Community](https://new.c.mi.com/global/post/2251454))
- **China firmware:** official unlocking is very limited. Reports describe
  Community level 5, real-name verification, or no unlock option at all
  for some models.
  ([Bootloader Unlock Wall of Shame](https://github.com/zenfyrdev/bootloader-unlock-wall-of-shame/blob/main/brands/xiaomi/README.md),
  [Wikipedia](https://en.wikipedia.org/wiki/Bootloader_unlocking))

!!! warning "Sources conflict"
    Some guides say Global firmware also needs Community level 5
    ([xiaomiui.net](https://xiaomiui.net/how-to-unlock-bootloader-on-xiaomi-official-steps-wait-times-and-hyperos-rules-74863/)),
    while a Xiaomi Community FAQ says Global users can apply from level 1
    ([Xiaomi Community](https://new.c.mi.com/global/post/2251454)).

!!! note "Coming soon"
    Which menu names above were checked on HyperOS 4 on piano, and the
    link to the unlock tool the project recommends.

## Check that it worked

```
fastboot getvar unlocked
```

It should say `unlocked: yes`.

!!! warning "Do not lock it again"
    Never run `fastboot flashing lock` or a stock "lock" script while a
    custom ROM or recovery is installed. A locked bootloader with
    unofficial software may not start at all.
