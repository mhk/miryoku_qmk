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

### For Miryoku Users

If you're using the Miryoku layout and want to specify which side will be connected to USB at build time, you can use the `MIRYOKU_HANDEDNESS` option:

```bash
make beekeeb/piantor:manna-harbour_miryoku \
  MIRYOKU_NAV=INVERTEDT \
  MIRYOKU_ALPHAS=COLEMAKDHK \
  MIRYOKU_HANDEDNESS=MASTER_RIGHT
```

Or with Docker:

```bash
docker run --rm -v $(pwd):/qmk_firmware qmkfm/qmk_cli:1.2.0_fixed \
  make beekeeb/piantor:manna-harbour_miryoku \
  MIRYOKU_NAV=INVERTEDT \
  MIRYOKU_ALPHAS=COLEMAKDHK \
  MIRYOKU_HANDEDNESS=MASTER_RIGHT
```

Valid values for `MIRYOKU_HANDEDNESS` are:
* `MASTER_RIGHT` - Forces right half to always be master
* `MASTER_LEFT` - Forces left half to always be master
* `EE_HANDS` - Programs handedness into EEPROM (requires additional flashing steps)

### For Other Keymaps

If you're not using Miryoku, you can add one of these to your keymap's `config.h`:

* `#define MASTER_RIGHT` - Forces right half to always be master
* `#define MASTER_LEFT` - Forces left half to always be master
* `#define EE_HANDS` - Programs each half's handedness into EEPROM (see [QMK documentation](https://docs.qmk.fm/#/feature_split_keyboard?id=handedness-by-eeprom))

For most users, the default auto-detection works best. See the [QMK Split Keyboard documentation](https://docs.qmk.fm/#/feature_split_keyboard) for more details.

## Bootloader

Enter the bootloader in 2 ways:

* **Physical reset button**: Hold the `BOOTSEL` button on the PCB while plugging in the usb cable.
* **Keycode in layout**: Press the key mapped to `QK_BOOT` if it is available
