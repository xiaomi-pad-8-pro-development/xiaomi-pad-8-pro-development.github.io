# Kernels

The kernel is the core of the system. It talks to the hardware. This
project has its own kernel, called **alxp**.

## Which kernel should I use?

Use the **6.6** kernel. It is in every ROM build.

| | 6.6 | 6.12 |
| --- | --- | --- |
| Status | Daily use, in every ROM build | Testing only |
| Base | Xiaomi Pad 8 kernel source, replayed on piano (`android15-6.6`) | Qualcomm kernel platform (`android16-6.12`) |
| Xiaomi drivers | Xiaomi's own source | Ported from 6.6; some rewritten |

The 6.12 kernel is still in testing. Some Xiaomi features are missing,
such as reading mode. If you are not testing, stay on 6.6.

TODO: which 6.12 builds are public, and its current known issues.

## Plain or root build

Each kernel comes in two builds.

| Build | What it is |
| --- | --- |
| **Plain** | No root. Used in the official ROM builds. |
| **KernelSU** | Root with **KernelSU-Next**, and **SUSFS** to hide root. |

To install the root build, see [Root with KernelSU](install/root.md).

## Where it comes from

- Source: [android_kernel_xiaomi_piano](https://github.com/xiaomi-pad-8-pro-development/android_kernel_xiaomi_piano)
- Built by: [auto](https://github.com/xiaomi-pad-8-pro-development/auto)
- Ready-made files used by the ROM:
  [android_device_xiaomi_piano-kernel](https://github.com/xiaomi-pad-8-pro-development/android_device_xiaomi_piano-kernel)

Every kernel module is built from source. Developers, see
[Kernel branches](developers/kernel-branches.md).
