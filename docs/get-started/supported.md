# Is my device supported?

## Supported model

Only the **Xiaomi Pad 8 Pro**, code name **piano**.

!!! danger "Other models"
    Do not install these files on any other tablet or phone, not even the
    Xiaomi Pad 8. Files for another model can stop the device from
    starting.

### How to check your code name

1. Install any device info app from the store, or connect the tablet to
   a computer with USB debugging on.
2. On the computer, run:

    ```
    adb shell getprop ro.product.device
    ```

3. The answer must be `piano`.

TODO: which regions (China, Global) have been tested, and whether the
tablet must be on a certain HyperOS version first.

## What you need

1. A computer (Windows, macOS or Linux).
2. Google's [Android platform tools](https://developer.android.com/tools/releases/platform-tools),
   which give you `adb` and `fastboot`.
3. A good USB-C cable.
4. The tablet charged to at least 50%.
5. A backup of everything you care about. See [Risks and backups](risks.md).

## Device specs

These values come from the source code of this project (device tree,
kernel devicetree and overlays). Anything not found there is marked TODO.

| | |
| --- | --- |
| Chip | Qualcomm Snapdragon 8 Elite (SM8750, platform `sun`) |
| CPU | Qualcomm Oryon, 64-bit only |
| GPU | Adreno 830 |
| Display | LCD, 3200 × 2136 pixels, 90, 120 and 144 Hz modes, density 440 |
| Display area | 238.7 × 163.2 mm (from the panel devicetree) |
| Speakers | Four, with FourSemi amplifiers, Dolby audio |
| Cameras | One rear camera with autofocus and flash, one front camera. TODO: sensor names and megapixels |
| Battery | 9200 mAh (from the power profile). TODO: confirm with Xiaomi's rated value |
| Charging | Fast charging with the Xiaomi charger. About 18 W on other USB PD chargers. TODO: maximum watts |
| Sensors | Accelerometer, gyroscope, compass, light, proximity, step counter |
| Connectivity | Wi-Fi (Aware, Direct, Passpoint), Bluetooth LE, USB host, NFC, IR blaster |
| Accessories | Xiaomi Focus Pen, keyboard cover with touchpad |
| Storage | UFS. TODO: RAM and storage options |
| Partitions | A/B slots with Virtual A/B |
| Stock software | HyperOS 4 (China firmware `OS4.0.6.0.XPYCNXM` is used by the ROM) |

TODO: screen size in inches, weight and size of the tablet.
