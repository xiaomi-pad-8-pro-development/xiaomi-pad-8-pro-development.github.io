# Build from source

You need a Linux machine with enough disk space and memory for an Android
build, and Git LFS (the vendor tree stores firmware in LFS).

## 1. Get the source

Start from your ROM's own instructions (for example LineageOS 24.0), then
add our local manifests:

```
repo init -u https://github.com/LineageOS/android.git -b lineage-24.0 --git-lfs
git clone https://github.com/xiaomi-pad-8-pro-development/local_manifests -b seventeen .repo/local_manifests
repo sync
```

`piano.xml` brings the trees every build needs: the device tree, the
kernel prebuilts (branch `6.6`), the vendor blobs, `hardware/xiaomi` and
our thermal HAL.

For extras, copy files from `.repo/local_manifests/optional/` next to
`piano.xml` and sync again:

| File | Adds |
| --- | --- |
| `piano-xiaomi-parts.xml` | Pen, keyboard, display settings |
| `piano-alxp-parts.xml` | AirPods, iPhone and Mac features |
| `piano-xiaomi-camera.xml` | Xiaomi camera |
| `piano-xiaomi-notes.xml` | Xiaomi Notes |
| `piano-aosp-notes.xml` | AOSP Notes |
| `piano-patches.xml` | ROM patches |

For the root kernel, change the `android_device_xiaomi_piano-kernel`
revision to `6.6-ksu`.

## 2. Build

```
source build/envsetup.sh
lunch lineage_piano-cp2a-userdebug
m bacon
```

The same `lunch` target is used for LineageOS and Evolution X.

## Signing

Without extra settings the build uses the public AOSP test keys. That is
fine for your own use.

Release builds are signed with private release keys, and set
`PIANO_AVB_KEY_PATH` to the private AVB key. These keys are never in any
repository.

!!! warning
    Keep a backup of your release keys. If you lose them, users must wipe
    their data to move to builds signed with new keys.

## Kernel

To build the kernel yourself, see
[auto](https://github.com/xiaomi-pad-8-pro-development/auto):

```
ROM_DIR=~/android/<rom> ./build.sh          # plain, branch 6.6
ROM_DIR=~/android/<rom> KSU=1 ./build.sh    # KernelSU-Next + SUSFS, branch 6.6-ksu
```

It needs clang `r510928` and a ROM checkout.
