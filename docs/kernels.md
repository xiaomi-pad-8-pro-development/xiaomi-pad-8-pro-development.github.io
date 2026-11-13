# Kernels

The kernel is called **alxp**. Its source is in
[android_kernel_xiaomi_piano](https://github.com/xiaomi-pad-8-pro-development/android_kernel_xiaomi_piano),
built by [auto](https://github.com/xiaomi-pad-8-pro-development/auto) into
[ready-made files](https://github.com/xiaomi-pad-8-pro-development/android_device_xiaomi_piano-kernel)
that the ROM uses.

## 6.6 or 6.12

| | 6.6 | 6.12 |
| --- | --- | --- |
| Status | Daily kernel, in every ROM build | Testing |
| Base | Xiaomi Pad 8 source, replayed on piano (android15-6.6) | Qualcomm KERNEL.PLATFORM 5.0 (android16-6.12) |
| Xiaomi drivers | Xiaomi's own source | Ported from 6.6; some rewritten |
| Source branch | `6.6` | `6.12` (patches) and `6.12-source` (full tree) |

On 6.12 the display, GPU, sound, Wi-Fi, Bluetooth, USB, touch, pen,
cameras, battery and charging work in testing. Some Xiaomi modules
without source are still missing. If you are not testing, use 6.6.

TODO: which 6.12 builds are public, and its current known issues.

## KernelSU variant

Each kernel also comes in a root build with
**KernelSU-Next** and **SUSFS** (to hide root).

| Prebuilt branch | Kernel |
| --- | --- |
| `6.6` | Plain |
| `6.6-ksu` | KernelSU-Next + SUSFS |

Install the KernelSU-Next manager app to use root.

TODO: how users pick the KSU build (separate ROM zip or kernel zip).
