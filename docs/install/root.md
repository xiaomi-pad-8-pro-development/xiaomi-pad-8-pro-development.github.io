# Root with KernelSU

Root is optional. The normal kernel has no root. For root, use the
**KernelSU-Next** build of the alxp kernel. It also includes **SUSFS**,
which helps hide root from apps.

!!! warning
    Root gives apps full control over the tablet. Only give root to apps
    you trust. Some apps refuse to run on rooted devices even with hiding.

## Steps

1. Get the KernelSU build of the ROM or kernel.

    TODO: how users get the KSU build (a separate ROM zip or a kernel zip)
    and the download link.

2. Install it in recovery, the same way as the ROM. See
   [Install the ROM](rom.md).
3. Start Android.
4. Install the **KernelSU-Next** manager app.

    TODO: link to the manager app version that matches the kernel.

5. Open the manager. It should show that KernelSU is working.
6. Give root to an app from the manager when the app asks.

## Remove root

Install the normal (plain) build of the ROM or kernel again. Your data
stays.

See [Kernels](../kernels.md) for the difference between the builds.
