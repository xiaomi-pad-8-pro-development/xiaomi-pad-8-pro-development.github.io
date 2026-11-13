# Risks and backups

Custom software is not made or supported by Xiaomi. Read this page before
you start.

## What can go wrong

!!! danger "You can lose all your data"
    Unlocking the bootloader **erases everything** on the tablet. The
    first install of a ROM also needs a **format of data**, which erases
    everything again.

!!! warning "The tablet may not start"
    A wrong file, a step done out of order, or flashing the wrong slot can
    stop the tablet from starting. Most of the time you can fix it from
    fastboot mode (see [Troubleshooting](../troubleshooting/index.md)),
    but there is no guarantee.

Other things to know:

- Your warranty may be affected. Check Xiaomi's rules for your region.
- Some banking, payment or game apps check for an unlocked bootloader and
  may refuse to run.
- This is community software. Some features may not work like stock.

## Back up before you start

1. Copy your photos, videos and files to a computer or cloud storage.
2. Back up chats in each chat app's own backup setting.
3. Write down your accounts and passwords, and make sure you can sign in
   to your Google and Xiaomi accounts from another device.
4. Note your apps so you can install them again.

!!! tip
    A HyperOS or Xiaomi cloud backup may not restore on an Android ROM.
    Copy your important files by hand as well.

## Keep a way back

Download the stock HyperOS **fastboot ROM** for this tablet before you
begin and keep it on your computer. With it you can always
[go back to stock](../install/stock.md).

TODO: link to where users can get the stock fastboot ROM for piano.

## Golden rules

1. Do one step at a time, in order.
2. Before you flash anything, check which slot is active (see
   [Slot recovery](../troubleshooting/slots.md)).
3. Never relock the bootloader while a custom ROM or recovery is
   installed.
4. If something goes wrong, stop and read
   [Troubleshooting](../troubleshooting/index.md) before you try random
   fixes.
