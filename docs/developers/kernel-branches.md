# Kernel branches

## Source

[android_kernel_xiaomi_piano](https://github.com/xiaomi-pad-8-pro-development/android_kernel_xiaomi_piano)
holds the alxp kernel: the Xiaomi Pad 8 history replayed on piano.

| Branch | What |
| --- | --- |
| `6.6` | Daily kernel, `android15-6.6` base, Xiaomi source drivers |
| `6.12` | Testing, Qualcomm `android16-6.12` base, as a patch stack |
| `6.12-source` | Testing, the same 6.12 kernel as a full tree |

The plain build uses `piano_defconfig`. The root build adds the
`piano_ksu.config` fragment (KernelSU-Next and SUSFS). Never enable
KernelSU in `piano_defconfig`.

## Prebuilts

[android_device_xiaomi_piano-kernel](https://github.com/xiaomi-pad-8-pro-development/android_device_xiaomi_piano-kernel)
goes to `device/xiaomi/piano-kernel`.

| Branch | Kernel |
| --- | --- |
| `6.6` | Plain |
| `6.6-ksu` | KernelSU-Next + SUSFS |

Each branch is one commit, replaced on every release. Only
[auto](https://github.com/xiaomi-pad-8-pro-development/auto) makes them.
Do not commit to them by hand.

## Building with auto

```
ROM_DIR=~/android/<rom> ./build.sh          # plain, branch 6.6
ROM_DIR=~/android/<rom> KSU=1 ./build.sh    # KernelSU-Next + SUSFS, branch 6.6-ksu
```

It needs clang `r510928` and a ROM checkout. `COMMIT=1` commits to the
prebuilt repository.

| Output | What |
| --- | --- |
| `Image` | Kernel |
| `dtb/`, `dtbo.img` | Devicetrees with techpack overlays merged |
| `modules/` | vendor_boot, vendor_dlkm, system_dlkm |
| `kernel-headers/` | UAPI headers |

## Mainline

[android_device_xiaomi_piano-kernel-mainline](https://github.com/xiaomi-pad-8-pro-development/android_device_xiaomi_piano-kernel-mainline)
(branch `7.2`) is an experimental mainline Linux port.
