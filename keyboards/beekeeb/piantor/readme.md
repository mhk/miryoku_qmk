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

## Split Keyboard Handedness

This keyboard uses `SPLIT_USB_DETECT` by default (enabled automatically on RP2040). This means whichever half has an active USB connection becomes the master automatically. Simply plug the USB cable into the half you want to be the master.

If you want to force a specific half to always be the master regardless of which side has USB connected, you can use one of these methods in your keymap's `config.h`:

* `#define MASTER_RIGHT` - Forces right half to always be master
* `#define MASTER_LEFT` - Forces left half to always be master  
* `#define EE_HANDS` - Programs each half's handedness into EEPROM (see [QMK documentation](https://docs.qmk.fm/#/feature_split_keyboard?id=handedness-by-eeprom))

For most users, the default auto-detection works best. See the [QMK Split Keyboard documentation](https://docs.qmk.fm/#/feature_split_keyboard) for more details.

## Bootloader

Enter the bootloader in 2 ways:

* **Physical reset button**: Hold the `BOOTSEL` button on the PCB while plugin in the usb cable.
* **Keycode in layout**: Press the key mapped to `QK_BOOT` if it is available
