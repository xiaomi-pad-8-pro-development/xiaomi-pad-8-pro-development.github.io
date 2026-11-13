# Going back to stock

You can return to Xiaomi HyperOS with the stock **fastboot ROM**.

Xiaomi does not publish a public ROM page for piano that we found. Stock
fastboot ROMs (`.tgz` files) for China, Global, EEA, Taiwan and Indonesia are
listed on mirrors such as
[xiaomirom.com](https://xiaomirom.com/en/rom/xiaomi-pad-8-pro-piano-china-fastboot-recovery-rom/)
and [miuidownloader.com](https://miuidownloader.com/hyperos/piano). These
link to Xiaomi's own download servers. The well-known
xiaomifirmwareupdater.com showed a "domain for sale" page when checked in
November 2026.

Use the region your tablet was sold in. The ROMs in this project are based
on China firmware `OS4.0.6.0.XPYCNXM`.

!!! note "Coming soon"
    Which stock version the project recommends for going back.

!!! danger "Choose the right script"
    The stock fastboot ROM has several scripts. Pick carefully.

    | Script | What it does |
    | --- | --- |
    | `flash_all_except_storage` | Installs stock and **keeps** user data |
    | `flash_all` | Installs stock and **erases everything** |
    | `flash_all_lock` | Installs stock, erases everything **and locks the bootloader** |

    Never use the **lock** script unless you are sure everything else is
    stock and you have tested that it starts. A locked bootloader with the
    wrong software may not start at all.

## Steps

1. Back up your files. Data from a custom ROM may not work on HyperOS, so
   you will likely need to erase it.
2. Unzip the fastboot ROM on your computer.
3. Start [fastboot mode](index.md#start-fastboot-mode) and connect the
   tablet.
4. Check that the computer sees it:

    ```
    fastboot devices
    ```

5. Run the script for your system, from inside the unzipped folder:

    === "Windows"

        ```
        flash_all.bat
        ```

    === "macOS and Linux"

        ```
        ./flash_all.sh
        ```

    Use `flash_all_except_storage` instead to try keeping your data.

6. Wait. The tablet restarts by itself when it is done.
7. If HyperOS does not start after keeping your data, run `flash_all`
   again to start clean.

!!! note
    Stock flashing does not clear the `misc` partition. If the tablet
    still loops, see [The misc fix](../troubleshooting/misc.md).
