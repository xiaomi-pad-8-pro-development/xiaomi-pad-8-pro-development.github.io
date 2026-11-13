# Going back to stock

You can return to Xiaomi HyperOS with the stock **fastboot ROM**.

TODO: link to where users can get the stock fastboot ROM for piano, and
which version to use.

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
