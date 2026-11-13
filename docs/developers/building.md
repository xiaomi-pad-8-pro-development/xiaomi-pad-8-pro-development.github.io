# Building

You need a Linux machine with enough disk space and memory for an Android
build, and **Git LFS** (the vendor tree stores firmware in LFS).

## 1. Get the source

1. Start from your ROM's own instructions, for example LineageOS:

    ```
    repo init -u https://github.com/LineageOS/android.git -b lineage-24.0 --git-lfs
    ```

2. Add the local manifests:

    ```
    git clone https://github.com/xiaomi-pad-8-pro-development/local_manifests -b seventeen .repo/local_manifests
    ```

3. Sync:

    ```
    repo sync
    ```

`piano.xml` brings the trees every build needs: the device tree, the
kernel prebuilts (branch `6.6`), the vendor blobs, `hardware/xiaomi` and
the thermal HAL.

## 2. Add extras (optional)

Copy files from `.repo/local_manifests/optional/` next to `piano.xml`, then
run `repo sync` again. The device tree builds without any of them.

| File | Adds |
| --- | --- |
| `piano-xiaomi-parts.xml` | Pen, keyboard, display settings |
| `piano-alxp-parts.xml` | AirPods, iPhone and Mac features |
| `piano-xiaomi-camera.xml` | Xiaomi camera |
| `piano-xiaomi-notes.xml` | Xiaomi Notes |
| `piano-aosp-notes.xml` | AOSP Notes |
| `piano-patches.xml` | ROM source patches |

For the root kernel, set the `android_device_xiaomi_piano-kernel`
revision to `6.6-ksu`.

## 3. Build

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

!!! danger "Keep a backup of your release keys"
    If you lose them, users must wipe their data to move to builds signed
    with new keys.

## Recovery

GitHub Actions in the recovery repository (**Build recovery**) build TWRP,
YARP and OrangeFox. To build locally, in a `twrp-16.0` source:

```
git clone https://github.com/xiaomi-pad-8-pro-development/android_device_xiaomi_piano-recovery -b seventeen device/xiaomi/piano
source build/envsetup.sh
export ALLOW_MISSING_DEPENDENCIES=true
export PIANO_YARP=1   # YARP only
lunch twrp_piano-bp2a-eng
m recoveryimage
```

## Kernel

See [Kernel branches](kernel-branches.md).
