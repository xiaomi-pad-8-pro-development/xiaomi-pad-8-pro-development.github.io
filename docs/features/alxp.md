# ALXP features

**ALXP Features** is a set of extras for people who also use Apple
devices. It has its own entry in **Settings → ALXP Features**, next to
Xiaomi features. Each feature is one switch.

| Feature | What it does |
| --- | --- |
| **AirPods automatic switching** | AirPods move between the Pad, your iPhone and your Mac, like on Apple devices |
| **iPhone notifications** | Shows iPhone notifications on the Pad, the way a smartwatch gets them |
| **Mac shared clipboard** | Copy text and images on one, paste on the other |
| **Mac second display** | Use the Pad as an extra Mac screen, like Sidecar |

## AirPods automatic switching

1. Open **Settings → ALXP Features**.
2. Turn on **Automatic switching**. Bluetooth restarts.
3. Pair your AirPods with the Pad.
4. Play something on the Pad, or take a call. The AirPods move to the Pad.
5. Play something on your iPhone or Mac. They move back.

If the AirPods dropped the Pad, it connects them again first.

Turning it off restarts Bluetooth and stops switching.

Tested with AirPods Max between the Pad and a Mac.

## Mac features

The clipboard and second display need the **ALXP for Mac** menu bar app.

1. Get ALXP for Mac.

    TODO: download link for a ready-made ALXP for Mac app (today it is
    built from source).

2. Open it. It finds the Pad on the same Wi-Fi. If your network blocks
   that, it can use a USB cable with `adb` instead.
3. The first time, the Mac shows a six-digit code. Confirm the same code
   on the Pad.
4. For the second display, give the Mac app **Screen Recording** and
   **Accessibility** permission in macOS settings.
5. Turn on **Open at Login** in its menu if you want it to start with
   the Mac.

## iPhone notifications

TODO: setup steps for iPhone notifications (pairing the iPhone with the
Pad over Bluetooth).
