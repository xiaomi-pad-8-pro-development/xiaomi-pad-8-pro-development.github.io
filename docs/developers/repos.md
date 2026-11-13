# Repository map

All code is in the GitHub organisation
[xiaomi-pad-8-pro-development](https://github.com/xiaomi-pad-8-pro-development),
one repository per tree.

Android trees use the branch `seventeen` (Android 17, HyperOS 4 China
`OS4.0.6.0.XPYCNXM` vendor). Kernel trees are named after the kernel.
Trees that are not Android use `main`.

## Needed for every build

| Repository | Path | Branch | Purpose |
| --- | --- | --- | --- |
| `android_device_xiaomi_piano` | `device/xiaomi/piano` | `seventeen` | Device tree |
| `android_device_xiaomi_piano-kernel` | `device/xiaomi/piano-kernel` | `6.6`, `6.6-ksu` | Kernel prebuilts |
| `android_vendor_xiaomi_piano` | `vendor/xiaomi/piano` | `seventeen` | Stock blobs and firmware (Git LFS) |
| `android_hardware_qcom_thermal` | `hardware/qcom-caf/thermal` | `seventeen` | Thermal HAL fork |
| `local_manifests` | `.repo/local_manifests` | `seventeen` | What to sync |

## Optional extras

| Repository | Path | Purpose |
| --- | --- | --- |
| `android_device_xiaomi_piano-xiaomi-parts` | `device/xiaomi/piano-xiaomi-parts` | Pen, keyboard, bypass charging, display |
| `android_device_xiaomi_piano-alxp-parts` | `device/xiaomi/piano-alxp-parts` | AirPods, iPhone and Mac features |
| `android_device_xiaomi_piano-patches` | `device/xiaomi/piano-patches` | Patches to the ROM source |
| `android_vendor_xiaomi_piano-xiaomi-camera` | `vendor/xiaomi/piano-xiaomi-camera` | Stock Xiaomi camera |
| `android_vendor_xiaomi_piano-xiaomi-notes` | `vendor/xiaomi/piano-xiaomi-notes` | Xiaomi Notes without an account |
| `android_device_xiaomi_piano-aosp-notes` | `device/xiaomi/piano-aosp-notes` | Offline notes app with pen ink |

All optional trees use the branch `seventeen`. The device tree includes
each one only when it is synced.

## Kernel

| Repository | Branch | Purpose |
| --- | --- | --- |
| `android_kernel_xiaomi_piano` | `6.6`, `6.12`, `6.12-source` | alxp kernel source |
| `auto` | `main` | Builds the kernel into the prebuilts |
| `android_device_xiaomi_piano-kernel-mainline` | `7.2` | Mainline Linux (experimental) |

## Other

| Repository | Branch | Purpose |
| --- | --- | --- |
| `android_device_xiaomi_piano-recovery` | `seventeen` | TWRP, YARP and OrangeFox |
| `android_device_xiaomi_piano-uefi` | `main` | UEFI and the Visor boot menu (experimental) |
| `android_device_xiaomi_piano-unixnu` | `main` | iPadOS port (experimental) |
| `xiaomi-pad-8-pro-development.github.io` | `main` | This website |

Android 16 is dropped. The old single-repo branches are kept as
`archive/*` tags in `android_device_xiaomi_piano`.
