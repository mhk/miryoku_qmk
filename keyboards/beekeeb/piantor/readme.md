# Piantor

![Piantor](https://i.imgur.com/xIF754Qh.jpg)

Piantor is a Cantor fork with Raspberry Pi Pico, hybrid hotswap socket and soldered-in switches support, and a breakable column.

* Keyboard Maintainer: [beekeeb](https://github.com/beekeeb)
* Hardware Supported: RP2040
* Hardware Availability: https://shop.beekeeb.com

Make example for this keyboard (after setting up your build environment):

    make beekeeb/piantor:default

Flashing example for this keyboard:

    make beekeeb/piantor:default:flash

See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

## Split Keyboard Configuration

This keyboard is configured with the **right half as the master**. This means the USB cable should always be connected to the right half of the keyboard. If you prefer to use the left half as master instead, you can modify `keyboards/beekeeb/piantor/config.h` and change `MASTER_RIGHT` to `MASTER_LEFT`, or remove the definition entirely (as left is the default).

For more information about split keyboard configuration, see the [QMK Split Keyboard documentation](https://docs.qmk.fm/#/feature_split_keyboard).

## Bootloader

Enter the bootloader in 2 ways:

* **Physical reset button**: Hold the `BOOTSEL` button on the PCB while plugin in the usb cable.
* **Keycode in layout**: Press the key mapped to `QK_BOOT` if it is available
