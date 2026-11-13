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

!!! note "Coming soon"
    Which regions (China, Global) have been tested, and whether the
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
kernel devicetree and overlays), checked against Xiaomi's [spec page](https://www.mi.com/uk/product/xiaomi-pad-8-pro/specs/) and
[GSMArena](https://www.gsmarena.com/xiaomi_pad_8_pro-14183.php).

| | |
| --- | --- |
| Chip | Qualcomm Snapdragon 8 Elite (SM8750, platform `sun`) |
| CPU | Qualcomm Oryon, 64-bit only |
| GPU | Adreno 830 |
| Display | LCD, 3200 × 2136 pixels, 90, 120 and 144 Hz modes, density 440 |
| Display area | 238.7 × 163.2 mm (from the panel devicetree) |
| Speakers | Four, with FourSemi amplifiers, Dolby audio |
| Cameras | One rear camera with autofocus and flash, one front camera. Rear 50 MP (1/2.76", f/1.8), front 32 MP ([Xiaomi](https://www.mi.com/uk/product/xiaomi-pad-8-pro/specs/)) |
| Battery | 9200 mAh, matching Xiaomi's rated (typical) value ([Xiaomi](https://www.mi.com/uk/product/xiaomi-pad-8-pro/specs/)) |
| Charging | Fast charging with the Xiaomi charger. About 18 W on other USB PD chargers. Up to 67 W HyperCharge; no charger in the box ([Xiaomi](https://www.mi.com/uk/product/xiaomi-pad-8-pro/specs/)) |
| Sensors | Accelerometer, gyroscope, compass, light, proximity, step counter |
| Connectivity | Wi-Fi (Aware, Direct, Passpoint), Bluetooth LE, USB host, NFC, IR blaster |
| Accessories | Xiaomi Focus Pen, keyboard cover with touchpad |
| Memory and storage | 8/128, 8/256, 12/256, 12/512 and 16/512 GB; the 128 GB model uses UFS 3.1, the others UFS 4.1 ([GSMArena](https://www.gsmarena.com/xiaomi_pad_8_pro-14183.php)). Global sale lists only 8/128, 8/256 and 12/512 ([Digital Trends](https://www.digitaltrends.com/tablets/xiaomi-pad-8-pro-review/)) |
| Partitions | A/B slots with Virtual A/B |
| Stock software | HyperOS 4 (China firmware `OS4.0.6.0.XPYCNXM` is used by the ROM) |
| Screen size | 11.2 inches ([GSMArena](https://www.gsmarena.com/xiaomi_pad_8_pro-14183.php)) |
| Size | 251.22 × 173.42 × 5.75 mm; 5.8 mm for the matte glass version ([Xiaomi](https://www.mi.com/uk/product/xiaomi-pad-8-pro/specs/)) |
| Weight | 485 g; 494 g for the matte glass version ([Xiaomi](https://www.mi.com/uk/product/xiaomi-pad-8-pro/specs/)) |

!!! warning "Sources conflict"
    RAM type: some listings say LPDDR5X for all models, while
    [Digital Trends](https://www.digitaltrends.com/tablets/xiaomi-pad-8-pro-review/)
    lists 12 GB as LPDDR5T. One retailer lists UFS 4.0 instead of 4.1.
